Communications and Control Engineering

Frank L. Lewis • Hongwei Zhang
Kristian Hengster-Movric • Abhijit Das
Cooperative Control
of Multi-Agent Systems
Optimal and Adaptive Design Approaches
1 3

Frank L. Lewis Kristian Hengster-Movric
UTA Research Institute UTA Research Institute
University of Texas at Arlington University of Texas at Arlington
Fort Worth Fort Worth
USA USA
Hongwei Zhang Abhijit Das
School of Electrical Engineering Advanced Systems Engineering
Southwest Jiaotong University Danfoss Power Solutions (US) Company
Chengdu Ames
China, People’s Republic USA
ISBN 978-1-4471-5573-7 ISBN 978-1-4471-5574-4 (eBook)
DOI 10.1007/978-1-4471-5574-4
Springer Dordrecht Heidelberg London New York
Library of Congress Control Number: 2013950494
© Springer-Verlag London 2014
This work is subject to copyright. All rights are reserved by the Publisher, whether the whole or part of
the material is concerned, specifically the rights of translation, reprinting, reuse of illustrations, recita-
tion, broadcasting, reproduction on microfilms or in any other physical way, and transmission or infor-
mation storage and retrieval, electronic adaptation, computer software, or by similar or dissimilar meth-
odology now known or hereafter developed. Exempted from this legal reservation are brief excerpts in
connection with reviews or scholarly analysis or material supplied specifically for the purpose of being
entered and executed on a computer system, for exclusive use by the purchaser of the work. Duplica-
tion of this publication or parts thereof is permitted only under the provisions of the Copyright Law of
the Publisher’s location, in its current version, and permission for use must always be obtained from
Springer. Permissions for use may be obtained through RightsLink at the Copyright Clearance Center.
Violations are liable to prosecution under the respective Copyright Law.
The use of general descriptive names, registered names, trademarks, service marks, etc. in this publica-
tion does not imply, even in the absence of a specific statement, that such names are exempt from the
relevant protective laws and regulations and therefore free for general use.
While the advice and information in this book are believed to be true and accurate at the date of publica-
tion, neither the authors nor the editors nor the publisher can accept any legal responsibility for any errors
or omissions that may be made. The publisher makes no warranty, express or implied, with respect to
the material contained herein.
Printed on acid-free paper
Springer is part of Springer Science+Business Media (www.springer.com)

To Galina, for her beauty and her wonderful
frame of mind
Frank Lewis
To Lin and my parents, for their uncondi-
tional love
Hongwei Zhang
To my family, for all the support, love and
kindness
Kristian Hengster-Movric
To my mother, because of whom I evaded
the dark side of me
Abhijit Das

Preface
This book studies cooperative control of multi-agent dynamical systems intercon-
nected by a communication network topology. In cooperative control, each system
is endowed with its own state variable and dynamics. A fundamental problem in
multi-agent dynamical systems on networks is the design of distributed protocols
that guarantee consensus or synchronization in the sense that the states of all the
systems reach the same value. The states could represent vehicle headings or posi-
tions, estimates of sensor readings in a sensor network, oscillation frequencies, trust
opinions of each agent, and so on. In multi-agent systems, all systems should agree
on the values of these quantities to achieve synchronized behavior.
Of fundamental concern for networked cooperative dynamical systems is the
study of their interactions and collective behaviors under the influence of the infor-
mation flow allowed in the communication network. This communication network
can be modeled as a graph with directed edges or links corresponding to the allowed
flow of information between the systems. The systems are modeled as the nodes in
the graph and are sometimes called agents. Information in communication networks
only travels directly between immediate neighbors in a graph. Nevertheless, if a
graph is connected, then this locally transmitted information travels ultimately to
every agent in the graph.
In cooperative control systems on graphs, there are intriguing interactions be-
tween the individual agent dynamics and the topology of the communication graph.
The graph topology may severely limit the possible performance of any control
laws used by the agents. Specifically, in cooperative control on graphs, all the con-
trol protocols must be distributed in the sense that the control law of each agent is
only allowed to depend on information from its immediate neighbors in the graph
topology. If enough care is not taken while designing the local agent control laws,
the individual agent dynamics may be stable, but the networked systems on the
graph may exhibit undesirable behaviors. Since the communication restrictions im-
posed by graph topologies can severely complicate the design of synchronization
controllers, complex and intriguing behaviors are observed in multi-agent systems
on graphs that do not occur in single-agent, centralized, or decentralized feedback
control systems.
vii

viii Preface
The study of networks of coupled dynamical systems arises in many fields of
research. Charles Darwin showed that the interactions between coupled biological
species over long time scales are responsible for natural selection. Adam Smith
showed that the dynamical relationships between geopolitical entities are respon-
sible for the balances in international finance and the wealth of nations. Distrib-
uted networks of coupled dynamical systems have received much attention over the
years because they occur in many different fields including biological and social
systems, physics and chemistry, and computer science. Various terms are used in
literature for phenomena related to the collective behavior on networks of systems,
such as flocking, consensus, synchronization, frequency matching, formation, ren-
dezvous, and so on. Collective synchronization phenomena occur in biology, soci-
ology, physics, chemistry, and human engineered systems. The nature of synchro-
nization in different groups depends on the manner in which information is allowed
to flow between the individuals of the group.
The collective motions of animal social groups are among the most beautiful
sights in nature. Each individual has its own inclinations and motions, yet the ag-
gregate motion makes the group appear to be a single entity with its own laws
of motion, psychology, and responses to external events. Flocks of birds, herds of
animals, and schools of fish are aggregate entities that take on an existence of their
own due to the collective motion instincts of their individual members. Collective
motions allow the group to achieve what the individual cannot. Collective synchro-
nized motion is a product not of planned scripts, but of instantaneous decisions and
responses by individual members.
Analysis of groups based on social behaviors is complex, yet the individuals
in collectives appear to follow simple rules. In many biological and sociological
groups such as schools of fish, bird flocks, mammal herds on the move, and hu-
man panic behavior in emergency building evacuation, evidence supports the idea
that the decisions made by all the individuals follow simple local protocols based
on their nearest neighbors. The collective motion of large groups can be captured
by using a few simple rules governing the behavior of the individuals. These rules
depend on the awareness of each individual of its neighbors.
Mechanisms of information transfer in groups involve questions such as how in-
formation about required motion directions, originally held by only a few informed
individuals, can propagate through an entire group by simple mechanisms that are
the same for every individual. The information flow between members of a social
group is instrumental in determining the characteristics of the combined motion of
the overall group.
The engineering study of multi-agent cooperative control systems uses princi-
ples observed in sociology, chemistry, and physics to obtain synchronized behavior
of all systems by using simple local distributed control protocols that are the same
for each agent and only depend on that agent’s neighbors in the group. Applications
have been to oscillator synchronization, aircraft formations, mobile sensor area cov-
erage, spacecraft attitude alignment, vehicle routing in traffic systems, containment
control of moving bodies, and biological cell sorting.

Preface ix
Optimal feedback control design has been responsible for much of the success-
ful performance of engineered systems in aerospace, manufacturing, industrial pro-
cesses, vehicles, ships, robotics, and elsewhere since the 1960s. Optimal control
designs generally require complete information of the system dynamics and rely
on off-line solutions of matrix design equations. Adaptive control is a powerful
method for the design of dynamic controllers that are tuned online in real time to
learn stabilizing feedback controllers for systems with unknown dynamics. Many
successful applications have been made in manufacturing and aerospace systems,
and elsewhere.
In this book, we use distributed cooperative control principles to design optimal
control systems and adaptive control systems for multi-agent dynamics on graphs.
These designs are complicated by the fact that all control protocols and parameter-
tuning protocols must be distributed in the sense that they depend only on immedi-
ate neighbors in the graph. Optimal control for cooperative multi-agent systems is
discussed in Part I of the book. Cooperative adaptive control is discussed in Part II.
Chapter 1 of this book presents an overview of synchronization behavior in na-
ture and social systems. It is seen that distributed decisions made by each agent in
a group based only on the information locally available to it can result in collective
synchronized motion of the overall group. The idea of a communication graph that
models the information flows in a multi-agent group is introduced. Synchronization
and collective behavior phenomena are discussed in biological systems, physics and
chemistry, and engineered systems. Various different graph topologies are presented
including random graphs, small world networks, scale-free networks, and distance
formation graphs. The early work in cooperative control systems on graphs is out-
lined.
Chapter 2 introduces cooperative synchronization control of multi-agent dynam-
ical systems interconnected by a fixed communication graph topology. Each agent
or node is mathematically modeled by a dynamical linear time-invariant system. A
review is given of graph basics and algebraic graph theory, which studies certain
matrices associated with the graph. Dynamical systems on graphs are introduced.
The idea of distributed control and the consensus problem are introduced. We be-
gin our study with first-order integrator dynamics for continuous-time systems and
discrete-time systems. Then, results are given for second-order position-velocity
systems which include motion control in formations. We present some key matrix
analysis methods for systems on graphs that are important for the analysis and de-
sign of cooperative controllers.
In Part I of the book, which contains Chaps. 3–6, we study local and global
optimal control for cooperative multi-agent systems linked to each other by a com-
munication graph. In cooperative control systems on graphs it turns out that local
optimality for each agent and global optimality for all the agents are not the same.
The relations between stability and optimality are well understood for single-agent
systems. However, there are more intriguing relations between stability and op-
timality in cooperative control than which appear in the single-agent case, since
local stability and global team stability are not the same, and local agent optimality
and global team optimality are not the same. New phenomena appear that are not

x Preface
present for single-agent systems. Moreover, throughout everything the synchroniza-
tion of the states of all agents must be guaranteed.
In Chap. 3, we study optimal control for continuous-time systems, and we shall
see that local optimal design at each agent guarantees global synchronization of all
agents to the same state values on any suitably connected digraph. Chapter 4 consid-
ers discrete-time systems and shows that an extra condition relating the local agent
dynamics and the graph topology must be satisfied to guarantee global synchroniza-
tion using local optimal design. Global optimization of collective group motions is
more difficult than local optimization of the motion of each agent. A common prob-
lem in optimal decentralized control is that global optimization problems generally
require global information from all the agents, which is not available to distributed
controllers which can only use information from nearest neighbors. In Chap. 5, we
shall see that globally optimal controls of distributed form may not exist on a given
graph. To obtain globally optimal performance using distributed protocols that only
depend on local agent information in the graph, the global performance index must
be selected to depend on the graph properties in a certain way, specifically, through
the graph Laplacian matrix. In Chap. 6, we define a different sort of global optimali-
ty for which distributed control solutions always exist on suitably connected graphs.
There, we study multi-agent graphical games and show that if each agent optimizes
its own local performance index, a Nash equilibrium is obtained.
In Part II of the book, which contains Chaps. 7–10, we show how to design co-
operative adaptive controllers for multi-agent systems on graphs. These controllers
allow synchronization of nonlinear systems where the agents have different dynam-
ics. The dynamics do not need to be known and may have unknown disturbances.
In adaptive controllers that are admissible for a prescribed communication graph
topology, only distributed control protocols and distributed adaptive tuning laws are
permitted. It is not straightforward to develop distributed adaptive tuning laws for
cooperative agents on graphs that only require information from each agent and its
neighbors. We show that the key to this is selecting special Lyapunov functions for
adaptive control design that depend in specific ways on the graph topology. Such
Lyapunov functions can be constructed using the concept of graph Laplacian poten-
tial, which depends on the communication graph topology.
In Chap. 7, we show that for networked multi-agent systems, there is an energy-
like function, called the graph Laplacian potential, that depends on the commu-
nication graph topology. The Laplacian potential captures the notion of a virtual
potential energy stored in the graph. The Laplacian potential is further used to con-
struct Lyapunov functions that are suitable for the stability analysis of cooperative
control systems on graphs. These Lyapunov functions depend on the graph topol-
ogy, and based on them a Lyapunov analysis technique is introduced for coopera-
tive multi-agent systems on graphs. Control protocols coming from such Lyapunov
functions are distributed in form, depending only on information about the agent
and its neighbors.
Chapter 8 covers cooperative adaptive control for systems with first-order non-
linear dynamics. The dynamics of the agents can be different, and they may be af-
fected by disturbances. The dynamics may be unknown. A special Lyapunov func-

Preface xi
tion that depends on the graph topology is used to construct cooperative adaptive
controllers wherein both the control protocols and the parameter tuning laws are
distributed in the sense that they depend only on information available locally from
the neighbors of each agent. Chapter 9 shows how to design adaptive controllers
for nonlinear second-order multi-agent systems with position-velocity dynamics.
Chapter 10 designs cooperative adaptive controllers for higher-order nonlinear
systems with unknown dynamics and disturbances. The challenge of ensuring that
both the control protocols and parameter tuning laws are distributed on the graph is
confronted by using a Lyapunov function that involves two terms, one depending
on the system dynamics and one depending on the communication graph topology.

Acknowledgements
This work has been supported over the years by the U.S. National Science Founda-
tion, the U.S. Army Research Office and TARDEC, the U.S. Air Force Office of
Scientific Research, and the Nanjing University of Science & Technology Visiting
Scholar Program. Recent support has been given by the National Natural Science
Foundation of China (through the Academy of Mathematics and Systems Sciences,
Chinese Academy of Sciences) and China Education Ministry Project 111 (through
Northeastern University, Shenyang), the National Natural Science Foundation
of China under grant 61304166, the Research Fund for the Doctoral Program of
Higher Education under grant 20130184120013, and the China Fundamental Re-
search Funds for the Central Universities under grants 2682013CX016 and SWJ-
TU11ZT06.
Frank Lewis, Arlington, Texas
Hongwei Zhang, Chengdu, China
Kristian Hengster-Movric, Arlington, Texas
Abhijit Das, Ames, Iowa
xiii

Contents
1 Introduction to Synchronization in Nature and Physics
and Cooperative Control for Multi-Agent Systems on Graphs ........... 1
1.1 Synchronization in Nature and Social Systems ............................... 1
1.1.1 Animal Motion in Collective Groups .................................. 3
1.1.2 Communication Graphs and Implementing
Reynolds’ Rules ................................................................... 4
1.1.3 Leadership in Animal Groups on the Move ......................... 8
1.2 Networks of Coupled Dynamical Systems in Nature and Science .. 10
1.2.1 Collective Motion in Biological and Social Systems,
Physics and Chemistry, and Engineered Systems ................ 10
1.2.2 Graph Topologies and Structured Information Flow
in Collective Groups ............................................................ 12
1.3 Cooperative Control of Multi-Agent Systems
on Communication Graphs .............................................................. 19
References ................................................................................................. 19
2 Algebraic Graph Theory and Cooperative Control Consensus ........... 23
2.1 Algebraic Graph Theory ................................................................... 24
2.1.1 Graph Theory Basics ........................................................... 25
2.1.2 Graph Matrices .................................................................... 26
2.1.3 Eigenstructure of Graph Laplacian Matrix .......................... 28
2.1.4 T he Fiedler Eigenvalue ........................................................ 33
2.2 Systems on Communication Graphs and Consensus ....................... 34
2.3 Consensus with Single-Integrator Dynamics ................................... 35
2.3.1 Distributed Control Protocols for Consensus ...................... 35
2.3.2 Consensus Value for Balanced Graphs—Average
Consensus ............................................................................ 41
2.3.3 Consensus Leaders ............................................................... 43
2.3.4 Non-Scalar Node States ....................................................... 44
2.4 Motion Invariants for First-Order Consensus .................................. 45
2.4.1 Graph Motion Invariant and ‘Internal Forces’ ..................... 45
2.4.2 Center of Gravity Dynamics and Shape Dynamics ............. 46
xv

xvi Contents
2.5 Consensus with First-Order Discrete-Time Dynamics .................... 47
2.5.1 Perron Discrete-Time Systems ............................................ 47
2.5.2 Normalized Protocol Discrete-Time Systems ...................... 49
2.5.3 Average Consensus Using Two Parallel Protocols
at Each Node ........................................................................ 51
2.6 Higher-Order Consensus: Linear Systems on Graphs ..................... 53
2.7 Second-Order Consensus ................................................................. 55
2.7.1 Analysis of Second-Order Consensus Using
Position/Velocity Local Node States ................................... 55
2.7.2 Analysis of Second-Order Consensus Using
Position/Velocity Global State ............................................. 59
2.7.3 Formation Control Second-Order Protocol ......................... 60
2.8 Matrix Analysis of Graphs ............................................................... 62
2.8.1 Irreducible Matrices and Frobenius Form ........................... 63
2.8.2 Stochastic Matrices .............................................................. 65
2.8.3 M-Matrices .......................................................................... 66
2.9 Lyapunov Functions for Cooperative Control on Graphs ................ 67
2.10 Conclusions and Setting for the Subsequent Chapters .................... 70
References ................................................................................................. 70
Part I Local Optimal Design for Cooperative Control
in Multi-Agent Systems on Graphs
3 Riccati Design for Synchronization of Continuous-Time Systems ...... 75
3.1 Duality, Stability, and Optimality for Cooperative Control ............. 75
3.2 State Feedback Design of Cooperative Control Protocols ............... 76
3.2.1 S ynchronization of Multi-Agent Systems on Graphs .......... 77
3.2.2 C ooperative SVFB Control .................................................. 79
3.2.3 L ocal Riccati Design of Synchronizing Protocols ............... 83
3.3 Region of Synchronization .............................................................. 84
3.4 Cooperative Observer Design .......................................................... 86
3.5 Duality for Cooperative Systems on Graphs ................................... 89
3.6 Cooperative Dynamic Regulators for Synchronization ................... 91
3.6.1 Neighborhood Controller and Neighborhood Observer ...... 91
3.6.2 Neighborhood Controller and Local Observer .................... 93
3.6.3 Local Controller and Neighborhood Observer .................... 95
3.7 Simulation Examples ....................................................................... 96
References ................................................................................................. 104
4 Riccati Design for Synchronization of Discrete-Time Systems ............ 107
4.1 Graph Properties .............................................................................. 108
4.2 State Feedback Design of Discrete-Time Cooperative Controls ..... 108
4.2.1 Synchronization of Discrete-Time Multi-Agent
Systems on Graphs .............................................................. 109

Contents xvii
4.3 Synchronization Region ................................................................... 112
4.4 Local Riccati Design of Synchronizing Protocols ........................... 112
4.5 Robustness Property of Local Riccati Design ................................. 116
4.6 Application to Real Graph Matrix Eigenvalues
and Single-Input Systems ................................................................ 118
4.6.1 Case of Real Graph Eigenvalues ......................................... 118
4.6.2 Case of Single-Input Agent Dynamics ................................ 119
4.6.3 Mahler Measure, Graph Condition Number,
and Graph Channel Capacity ............................................... 120
4.7 Cooperative Observer Design .......................................................... 121
4.7.1 Distributed Neighborhood Observer Dynamics .................. 122
4.7.2 Convergence Region ............................................................ 124
4.7.3 Local Riccati Cooperative Observer Design ....................... 124
4.7.4 Duality on Graphs for Discrete-Time Cooperative Systems .. 127
4.8 Cooperative Dynamic Regulators for Synchronization ................... 128
4.8.1 Neighborhood Controller and Neighborhood Observer ...... 128
4.8.2 Neighborhood Controller and Local Observer .................... 129
4.8.3 Local Controller and Neighborhood Observer .................... 130
4.9 Simulation Examples ....................................................................... 132
4.9.1 Example 4.1. Importance of Weighting in Control
and Observer Protocols ........................................................ 132
4.9.2 Example 4.2. Three Cooperative Dynamic
Regulator Designs ................................................................ 134
4.10 Conclusion ....................................................................................... 136
References ................................................................................................. 140
5 Cooperative Globally Optimal Control for Multi-Agent
Systems on Directed Graph Topologies .................................................. 141
5.1 Stability, Local Optimality, and Global Optimality
for Synchronization Control on Graphs ........................................... 142
5.2 Graph Definitions ............................................................................. 143
5.3 Partial Asymptotic Stability ............................................................. 144
5.4 Inverse Optimal Control .................................................................. 147
5.4.1 Optimality ............................................................................ 148
5.4.2 Inverse Optimality ............................................................... 149
5.5 Optimal Cooperative Control for Quadratic Performance
Index and Single-Integrator Agent Dynamics ................................. 153
5.5.1 Optimal Cooperative Regulator ........................................... 153
5.5.2 Optimal Cooperative Tracker .............................................. 156
5.6 Optimal Cooperative Control for Quadratic Performance
Index and Linear Time-Invariant Agent Dynamics ......................... 158
5.6.1 Optimal Cooperative Regulator ........................................... 158
5.6.2 Optimal Cooperative Tracker .............................................. 161

xviii Contents
5.7 Constraints on Graph Topology ....................................................... 164
5.7.1 Undirected Graphs ............................................................... 165
5.7.2 Detail Balanced Graphs ....................................................... 165
5.7.3 Directed Graphs with Simple Laplacian .............................. 166
5.8 Optimal Cooperative Control for General Digraphs:
Performance Index with Cross-Weighting Terms ............................ 167
5.8.1 Optimal Cooperative Regulator—Single-Integrator
Agent Dynamics .................................................................. 168
5.8.2 Optimal Cooperative Tracker—Single-Integrator
Agent Dynamics .................................................................. 170
5.8.3 Condition for Existence of Global Optimal Control
with Cross-weighting Terms in the Performance Index ...... 171
5.8.4 General Linear Time-Invariant Systems—Cooperative
Regulator .............................................................................. 172
5.8.5 General Linear Time-Invariant Systems—Cooperative
Tracker ................................................................................. 175
5.9 Conclusion ....................................................................................... 178
References ................................................................................................. 179
6 Graphical Games: Distributed Multiplayer Games on Graphs .......... 181
6.1 Introduction: Games, RL, and PI ..................................................... 182
6.2 Synchronization and Node Error Dynamics .................................... 183
6.2.1 Graphs .................................................................................. 183
6.2.2 Synchronization and Node Error Dynamics ........................ 184
6.3 Cooperative Multiplayer Games on Graphs .................................... 186
6.3.1 Cooperative Performance Index .......................................... 186
6.3.2 Global and Local Performance Objectives:
Cooperation and Competition .............................................. 188
6.3.3 Graphical Games ................................................................. 188
6.4 Interactive Nash Equilibrium ........................................................... 192
6.5 Stability and Solution of Graphical Games ..................................... 195
6.5.1 Coupled Riccati Equations .................................................. 196
6.5.2 Stability and Solution for Cooperative Nash Equilibrium ... 198
6.6 PI Algorithms for Cooperative Multiplayer Games ......................... 200
6.6.1 Best Response ...................................................................... 200
6.6.2 PI Solution for Graphical Games ......................................... 201
6.6.3 PI Solution for Graphical Games ......................................... 205
6.6.4 Critic NN ............................................................................. 206
6.6.5 Action NN and Online Learning .......................................... 207
6.7 Simulation Results ........................................................................... 211
6.7.1 Position and Velocity Regulated to Zero ............................. 213
6.7.2 All the Nodes Synchronize to the Curve Behavior
of the Leader Node .............................................................. 213
6.8 Conclusion ....................................................................................... 215
References ................................................................................................. 215

Contents xix
Part II Distributed Adaptive Control for Multi-Agent Cooperative Systems
7 Graph Laplacian Potential and Lyapunov Functions
for Multi-Agent Systems .......................................................................... 221
7.1 Graph Laplacian Potential ................................................................ 222
7.2 Laplacian Potential for Undirected Graphs ...................................... 223
7.2.1 Laplacian Potential for Directed Graphs ............................. 225
7.3 Lyapunov Analysis for Cooperative Regulator Problems ................ 228
7.3.1 Consensus of Single Integrator Cooperative Systems ......... 229
7.3.2 Synchronization of Passive Nonlinear Systems .................. 231
References ................................................................................................. 234
8 Cooperative Adaptive Control for Systems with First-Order
Nonlinear Dynamics ................................................................................. 235
8.1 Synchronization Control Formulation and Error Dynamics ............ 236
8.1.1 Graph Theory Basics ........................................................... 236
8.1.2 Synchronization Control Problem ....................................... 237
8.1.3 Synchronization Error Dynamics ........................................ 238
8.1.4 Synchronization Control Design .......................................... 239
8.2 Adaptive Design and Distributed Tuning Law ................................. 241
8.3 Relation of Error Bounds to Graph Structural Properties ................ 249
8.4 Simulation Examples ....................................................................... 250
References ................................................................................................. 256
9 Cooperative Adaptive Control for Systems
with Second-Order Nonlinear Dynamics ............................................... 259
9.1 Sliding Variable Cooperative Control Formulation
and Error Dynamics ......................................................................... 260
9.1.1 Cooperative Tracking Problem for Synchronization
of Multi-Agent Systems ....................................................... 260
9.1.2 Sliding Mode Tracking Error ............................................... 262
9.1.3 Synchronization Control Design and Error Dynamics ........ 263
9.2 Cooperative Adaptive Design and Distributed Tuning Laws .......... 265
9.3 Simulation Example ......................................................................... 273
References ................................................................................................. 278
10 Cooperative Adaptive Control for Higher-Order
Nonlinear Systems .................................................................................... 279
10.1 Sliding Variable Control Formulation and Error Dynamics ............ 280
10.1.1 Synchronization for Nonlinear Higher-Order
Cooperative Systems ........................................................... 280
10.1.2 Local Neighborhood Error Dynamics ................................. 283
10.1.3 Communication Graph Structure and the Graph
Lyapunov Equation .............................................................. 284

xx Contents
10.2 Distributed Control Structure ........................................................... 285
10.2.1 Sliding Mode Error Variables and Performance
Lyapunov Equation .............................................................. 285
10.2.2 Local NN Approximators for Unknown Nonlinearities ...... 287
10.2.3 Distributed Control Law Structure ...................................... 290
10.3 Distributed Tuning Laws for Cooperative Adaptive Control ........... 291
10.4 Simulation Example ......................................................................... 297
References ................................................................................................. 303
Index ................................................................................................................ 305

Chapter 1
Introduction to Synchronization in Nature
and Physics and Cooperative Control
for Multi-Agent Systems on Graphs
This chapter presents an overview of synchronization behavior in nature and social
systems. It is seen that distributed decisions made by each agent in a group based
only on the information locally available to it can result in collective synchronized
motion of an overall group. The idea of a communication graph that models the
information flows in a multi-agent group is introduced. Mechanisms are given by
which decisions can be made locally by each agent and informed leaders can guide
collective behaviors by interacting directly with only a few agents. Synchronization
and collective behavior phenomena are discussed in biological systems, physics
and chemistry, and engineered systems. The dependence of collective behaviors of
a group on the type of information flow allowed between its agents is emphasized.
Various different graph topologies are presented including random graphs, small-
world networks, scale-free networks, and distance formation graphs. The early
work in cooperative control systems on graphs is outlined.
This chapter presents the fundamental ideas used in the rest of the book to devel-
op analysis and design methods for the cooperative control of multi-agent dynami-
cal systems on graphs. It is seen that the basic ideas and philosophy of cooperative
control systems rest upon phenomena that occur every day in natural and biological
systems, physics, and chemistry.
1.1 Synchronization in Nature and Social Systems
The collective motions of animal social groups are among the most beautiful sights
in nature. Each individual has its own inclinations and motions; yet, the aggregate
motion makes the group appear to be a single entity with its own laws of motion,
psychology, and responses to external events. Flocks of birds, schools of fish, and
herds of animals are aggregate entities that take on an existence of their own due to
the collective motion instincts of their individual members (see Fig. 1.1). The ag-
gregate turns and wheels to achieve its objectives such as seeking food or migrating
and to avoid predators and obstacles. Such synchronized and responsive motion
makes one think of choreographed motions in a dance; yet, they are a product not of
F. L. Lewis et al., Cooperative Control of Multi-Agent Systems, 1
Communications and Control Engineering, DOI 10.1007/978-1-4471-5574-4_1,
© Springer-Verlag London 2014

2 1 Introduction to Synchronization in Nature and Physics and Cooperative …
Fig. 1.1 The collective motion of animal social groups depends on individual member responses
and is different for different species: a A flock of geese on migration. Courtesy of Bill Boaden, b
A flock of birds appears to be a single composite entity in its motion and behaviors. Courtesy of
Eric Tofsrud Photography, c A school of fish in synchronized motion. Courtesy of Russell Taylor,
d A school of fish responding as a single organism. Courtesy of Burak Dedeler, e Wildebeest herd
on migration. Courtesy of John Harrison, f Wildebeest stampede to avoid danger. Courtesy of
Jacqueline C. Baz
planned scripts, but of instantaneous decisions and responses by individual mem-
bers. In this section, we study the mechanisms of such synchronized choreographic
behavior of groups in terms of instantaneous decisions made by their individual
members.
Collective motions allow the group to achieve what the individual cannot. The
benefits of aggregate motion include defense from predators, social and mating ad-
vantages, and group foraging for food. In migrating bird flocks, the energy required
by individual birds in flying is reduced by remaining in the wingtip vortex upwash
of those ahead. Choreographed motions of groups of lions, wolves, and jackals
allow a more efficient pursuit of prey. In collective motion situations, the impor-

1.1 Synchronization in Nature and Social Systems 3
tant entity becomes the group, not the individual. Such behavior has been observed
in human crowd panic and mob situations, where there is pressure to follow the
group’s collective lead, and not to think on one’s own.
1.1.1 Animal Motion in Collective Groups
To reproduce the collective motion of an animal group in computer animation has
been a challenge. It would be impossible to script the motion of each individual us-
ing planned motions or trajectories. An analysis of groups based on social behaviors
is complex; yet, the individuals in collectives appear to follow simple rules that
make their motion efficient, responsive, and practically instantaneous. The cumula-
tive motion of animal groups can be programmed in computer animation by endow-
ing each individual with the same few rules that allow it to respond to the situations
it encounters. The responses of the individuals accumulate to produce the combined
motion of the group. The material in this section is from Reynolds [6].
Dependence of Group Motion on the Information Flow in Social Groups In
large social groups, each individual is aware only of the motions of its immediate
neighbors. The field of perceptual awareness of the individual changes for differ-
ent types of animal groups and in different motion scenarios. This results in dif-
ferent types of motion for different species. In flocking motion, birds are aware
only of a few neighbors ahead of them or beside them. This results in the elegant,
slow, wheeling motions of geese and ducks in migration. In schools of fish, shock
waves transmitted by the water allow individuals to be aware instantaneously of the
motions of neighbors that they may not even see. This results in the quick, darting
motions of fish schools that respond as a single entity. In animal herds, vibrations of
the earth allow individuals to be aware of the general motion tendencies of others
that may not be close by.
It is thus seen that the type of motion of the overall group depends on the man-
ner in which information is allowed to flow between the individuals of the group.
In well-connected social groups where each individual is aware of the motion of a
greater number of neighbors, response speeds are generally faster.
Reynolds’ Rules The collective motion of large groups can be captured by using a
few simple rules governing the behavior of the individuals. Individual motions in a
group are the result of the balance of two opposing behaviors: a desire to stay close
to the group and a desire to avoid collisions with other individuals. Reynolds [6] has
captured the tendencies governing the motions of individuals through his three rules.
These rules depend on the motions of the neighbors of each individual in the group.
Reynolds’ Rules [6]:
1. Collision avoidance: avoid collisions with neighbors;
2. Velocity matching: match speed and direction of motion with neighbors; and
3. Flock centering: stay close to neighbors.

4 1 Introduction to Synchronization in Nature and Physics and Cooperative …
F ig. 1.2 A directed graph
models the information flow
between individuals of a
social group
1.1.2 Communication Graphs and Implementing Reynolds’
Rules
Reynolds’ rules capture very well the collective motion of animal groups and can
also be used as control schemes for human systems such as vehicle formations.
These rules depend on the awareness of each individual of his neighbors. We have
seen that the information flow between members of a social group is instrumental in
determining the motion of the overall group. In this book, we are concerned with the
behaviors and interactions of dynamical systems that are interconnected by the links
of a communication network. This communication network is modeled as a graph
with directed edges corresponding to the allowed flow of information between the
systems. The systems are modeled as the nodes in the graph and are sometimes
called agents.
Communication Graph Figure 1.2 shows a representative graph that models
the information flow interactions between six agents in a group. A graph is a pair
G (V, E) with V {v , . . . , v } being a set of N nodes or vertices and E a set of
= = 1 N
edges or arcs. Elements of E are denoted as (v, v) which is termed an edge or an
i j
arc from v to v, and is represented as an arrow with tail at v and head at v. The
i j i j
in-degree of v is the number of edges having v as a head. The out-degree of a node
i i
v is the number of edges having v as a tail. The set of (in-) neighbors of a node
i i
v is N ={v :(v ,v )∈E}, i.e., the set of nodes with edges incoming to v. The
i i j j i i
neighbor set N represents the nodes from which agent i receives information and
i
in response to which it determines its own motion. The number of neighbors N i of
| |
node v is equal to its in-degree.
i
We have already intimated that the number of neighbors of each individual de-
termines the speed of response and the type of motion of the collective group. In
subsequent chapters, we shall study relationships between the graph topology and
the resulting motion of each agent.

| 1.1  Synchronization in Nature and Social Systems  |     |     |     |     | 5   |
| -------------------------------------------------- | --- | --- | --- | --- | --- |
Associate with each edge  (v ,v ) E a weight  a >0. Note the order of
|     |     | j i ∈ |     | ij  |     |
| --- | --- | ----- | --- | --- | --- |
the indices in this definition. Then the neighbor set of node i can be written as
N v :a >0 . The weights  a ij are selected to model the strength of the in-
| i ={ j ij | }   |     |     |     |     |
| --------- | --- | --- | --- | --- | --- |
teraction between nodes. For instance, if agent j has higher social standing, then
a
ij might be selected larger so that agent i is more responsive to the behaviors of
agent j.
|                              |     | a 0 a       | 0 so that communication between  |     |     |
| ---------------------------- | --- | ----------- | -------------------------------- | --- | --- |
| A graph is bidirectional if  |     | ij ji       |                                  |     |     |
|                              |     | (cid:31)= ⇒ | (cid:31)=                        |     |     |
agents occurs bidirectionally. A graph is said to be undirected if a a , i,j,
|     |     |     |     | ij = | ji ∀ |
| --- | --- | --- | --- | ---- | ---- |
that is, if it is bidirectional and the weights of edges (v, v) and (v, v) are the same.
|     |     |     | i   | j j i |     |
| --- | --- | --- | --- | ----- | --- |
A directed path is a sequence of nodes v 0 , v 1  ,. . ., v such that (v, v r )   E,
|     |     |     |     | i   | i+1 ∈ |
| --- | --- | --- | --- | --- | ----- |
i   {0, 1,. . ., r - 1}. Node v is said to be connected to node v if there is a directed
| ∈   | i   |     |     | j   |     |
| --- | --- | --- | --- | --- | --- |
path from v to v. The distance from v to v is the length of the shortest path from v  i j i j i
to v . Graph G is said to be strongly connected if v i ,v j are connected for all distinct
j
nodes v ,v V. For bidirectional and undirected graphs, if there is a directed path
i j
∈
| from v to v, then there is a directed path from v to v, and the qualifier ‘strongly’  i j |     |     | j i |     |     |
| ----------------------------------------------------------------------------------------- | --- | --- | --- | --- | --- |
is omitted. If a graph is not connected, it is disconnected. A component of an undi-
rected graph is a connected subgraph that is not connected to the remainder of the
graph.
Information in social networks only travels directly between immediate neigh-
bors in a graph. Nevertheless, if a graph is connected, then this locally transmitted
information travels finally to every agent in the graph.
The diameter of a graph is the longest distance between two nodes. If the graph
is disconnected, the diameter is infinity. The diameter is a global property of the
graph.
 Implementing Reynolds’ Rules in Dynamical Motion Systems
There are many mechanisms for implementing Reynolds’ rules in dynamical sys-
tems control. Of importance is the definition of an individual’s ‘neighborhood’.
Consider motion in the R2 and define (p (t),q (t)) as the position of node i in the
|     |     | i   | i   |     |     |
| --- | --- | --- | --- | --- | --- |
(x,y)-plane. Define the state of agent i asx [p q ]T R2. In this discussion, all
|     |     | i   | i i |     |     |
| --- | --- | --- | --- | --- | --- |
|     |     | =   | ∈   |     |     |
interaction graphs are assumed undirected. That is,  a ij a ji so that communica-
=
tion between agents occurs bidirectionally.
Agents seek to avoid collisions. Therefore, define a circle of radius ρ  which
c
each agent seeks to keep clear of other agents. Define the collision neighbor-
hood for agent i as Nc ={j:r ≤ρ} where the distance between nodes i and j is
|     | i   | ij c |     |     |     |
| --- | --- | ---- | --- | --- | --- |

p)2 -q)2
|     | r = x | -x = (p - | +(q |     | (1.1) |
| --- | ----- | --------- | --- | --- | ----- |
|     | ij j  | i j       | i j | i   |       |
ρ>ρ
Define also an interaction radius  c  and the interaction neighborhood by
N ={j:r ≤ρ}. It is noted that radii ρ,ρ are different for different animal groups
| i ij |     | c   |     |     |     |
| ---- | --- | --- | --- | --- | --- |
and different vehicles. Moreover, for some groups, such as flocks of birds in migra-
tion, the collision and interaction neighborhoods are not circular.

6 1  Introduction to Synchronization in Nature and Physics and Cooperative …
The dynamics used to simulate the individual group members can be very sim-
ple; yet, realistic results are obtained. Consider agent motion in two dimensions
(2-D) according to the dynamics

x u
|     |     | i i | (1.2) |
| --- | --- | --- | ----- |
˙ =
with states x [p q ]T R2. This is a simple point-mass dynamics with veloc-
i i i
| =                      | ∈ ]T R2.   |     |     |
| ---------------------- | ---------- | --- | --- |
| ity control inputs u i | [u pi u qi |     |     |
= ∈
A suitable law for collision avoidance is given by
|     | =−∑ |          |       |
| --- | --- | -------- | ----- |
|     | u   | c (x −x) | (1.3) |
|     | i   | ij j i   |       |
j∈Nc
i
which causes agent i to turn away from other agents inside the collision neighbor-
| hood Nc. Here c  is the collision-avoidance gain. |     |     |     |
| ------------------------------------------------- | --- | --- | --- |
i
ij
A suitable law for flock centering is given by
|     | u = ∑ | a (x −x ) |       |
| --- | ----- | --------- | ----- |
|     | i     | ij j i    | (1.4) |
j∈N\Nc
i i
which causes agent i to turn toward other agents inside the interaction neighborhood
 and outside the collision neighborhood Nc. The flock-centering protocol can be
N
| i   |     | i   |     |
| --- | --- | --- | --- |
written in terms of the components of velocity as

|     | p u   | a (p p ) | (1.5) |
| --- | ----- | -------- | ----- |
|     | i pi  | ij j i   |       |
|     | ˙ = = | −        |       |
j N Nc
∈(cid:31)i\ i
|     | q u   | a (q q ) |       |
| --- | ----- | -------- | ----- |
|     | i qi  | ij j i   | (1.6) |
|     | ˙ = = | −        |       |
j N Nc
∈(cid:31)i\ i
The net velocity control u i applied to the system is the sum of (1.3) and (1.4). The
c
relation between the collision-avoidance gains  ij and the flock-centering gains
a ij determines different response behaviors insofar as agents prefer to flock or pre-
fer to avoid neighbors. The relation between the radii ρ,ρ c is also instrumental in
designing different behaviors.
Distributed Control Protocols on Communication Graphs The control proto-
cols (1.4)–(1.6) are known as local voting protocols because each agent seeks to
make the difference between his state and those of his neighbors equal to zero. That
is, each agent seeks to achieve consensus with its neighbors. These protocols are
distributed in the sense that they depend only on the local neighbor information as
allowed by the communication graph topology.
Alternative protocols for collision avoidance and flock centering are given re-
spectively by

| 1.1  Synchronization in Nature and Social Systems  |     |     |     |      |     |     |         |     | 7     |
| -------------------------------------------------- | --- | --- | --- | ---- | --- | --- | ------- | --- | ----- |
|                                                    |     |     | (x  | x i) |     |     | (x x i) |     |       |
|                                                    |     |     | c   | j −  |     | c   | j −     |     |       |
|                                                    | u   |     | ij  |      |     | ij  |         |     | (1.7) |
|                                                    | i=− |     |     | r    | =−  |     | x x     |     |       |
|                                                    |     | j   | Nc  | ij   | j   | Nc  | j − i   |     |       |
|                                                    |     |     | ∈ i |      |     | ∈ i |         |     |       |

|     |     |     | (x   | j x i) |     |      | (x j x i) |     |       |
| --- | --- | --- | ---- | ------ | --- | ---- | --------- | --- | ----- |
|     | u   |     | a    | −      |     | a    | −         |     | (1.8) |
|     | i=  |     | ij   | r      | =   | ij   | x x       |     |       |
|     |     |     |      | ij     |     |      | j i       |     |       |
|     |     | j N | Nc   |        | j N | Nc   | −         |     |       |
|     |     | ∈   | i\ i |        | ∈   | i\ i |           |     |       |
which are normalized by dividing by the distance between agents. Note that the sum
is over the components of a unit vector. Therefore, these laws prescribe a desired
direction of motion and result in motion of uniform velocity. By contrast, the laws
(1.3) and (1.4) give velocities that are larger if one is further from one’s neighbors.
These protocols guarantee consensus behavior in terms of (x,y) position, yet do
not include velocity matching control. Simple motions of a group of N agents in the
(x,y)-plane can alternatively be described by the node dynamics
|     |     |     |     | p   | V cosθ |     |     |     |       |
| --- | --- | --- | --- | --- | ------ | --- | --- | --- | ----- |
|     |     |     |     | i   | i      | i   |     |     | (1.9) |
˙ =
|     |     |     |     | q i V | i sinθ i |     |     |     |     |
| --- | --- | --- | --- | ----- | -------- | --- | --- | --- | --- |
˙ =
where V  is the speed and  θ  the heading of agent i. Velocity matching can be
| i   |     |     | i   |     |     |     |     |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
achieved by using the local voting protocol to reach heading consensus according to

|     |     |     | θ   |     | a (θ   | θ ) |     |     | (1.10) |
| --- | --- | --- | --- | --- | ------ | --- | --- | --- | ------ |
|     |     |     | ˙i  | =   | ij j − | i   |     |     |        |
j N
(cid:31)∈ i
and a second local voting protocol to match speeds according to

|     |     |     | V   |     | a (V | V ) |     |     | (1.11) |
| --- | --- | --- | --- | --- | ---- | --- | --- | --- | ------ |
|     |     |     | ˙i  |     | ij j | i   |     |     |        |
|     |     |     | =   |     | −    |     |     |     |        |
j Ni
(cid:31)∈
As a third alternative, one can use the Newton’s law agent dynamics
|                        |     |     |             | x   | v                            |     |     |     |           |
| ---------------------- | --- | --- | ----------- | --- | ---------------------------- | --- | --- | --- | --------- |
|                        |     |     |             | ˙ i | = i                          |     |     |     | (1.12)    |
|                        |     |     |             | v   | u                            |     |     |     |           |
|                        |     |     |             | i   | i                            |     |     |     |           |
|                        |     |     |             | ˙   | =                            |     |     |     |           |
|                        |     |     | Rn, speed v |     | Rn, and acceleration input u |     |     |     | Rn. This  |
| with vector position x |     | i   |             | i   |                              |     |     | i   |           |
|                        |     | ∈   |             | ∈   |                              |     |     |     | ∈         |
is more realistic than (1.2) for the motion of physical bodies in n dimensions. For
motion in the 2-D plane, one would take x [p q ]T  where (p (t),q (t)) is the
|     |     |     |     |     | i   | i i |     | i   | i   |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
=
position of node i in the (x,y)-plane.
Consider the distributed position/velocity feedback at each node given by the
second-order local neighborhood protocols

8 1  Introduction to Synchronization in Nature and Physics and Cooperative …
| =c∑ |      | +cγ∑    |           |     |
| --- | ---- | ------- | --------- | --- |
| u   | a    | (x −x ) | a (v −v ) |     |
| i   | ij   | j i     | ij j i    |     |
|     | j∈Ni |         | j∈Ni      |     |

|     | ∑ca | (( )+γ(v | )    |        |
| --- | --- | -------- | ---- | ------ |
| =   |     | (x −x    | −v ) | (1.13) |
|     | ij  | j i      | j i  |        |
j∈Ni
where c>0 is a stiffness gain and cγ >0 is a damping gain. This is based on lo-
cal voting protocols in both position and velocity so that each node seeks to match
all its neighbors’ positions as well as their velocities. Thus, this protocol realizes
Reynolds’ rules for flock centering and velocity matching. A protocol such as (1.3)
could be added for collision avoidance.
Alternatively, offsets could be added for desired relative separation as in

| u =c∑a | ( x | -x -∆ ) +cγ∑a | (v -v ) | (1.14) |
| ------ | --- | ------------- | ------- | ------ |
| i      | ij  | j i ji        | ij j i  |        |
| j∈N    |     |               | j∈N     |        |
|        | i   |               | i       |        |
where (cid:31) Rn are the desired offsets of node i from node j. This law contains both
ji
∈
flock-centering and collision-avoidance aspects.
Alternative methods to local cooperative protocols for implementing Reynolds’
rules include potential field approaches [34–36]. Potential field methods include
approaches for obstacle avoidance and goal seeking, and are intimately related to
the topics in this section.
1.1.3   Leadership in Animal Groups on the Move
We have seen that information can be transferred locally between individual neigh-
boring members of animal groups, yet result in collective synchronized motions of
the whole group. Local motion control protocols are based on a few simple rules
that are followed by all individuals. However, in many situations, the whole group
must move toward some goal, such as along migratory routes or toward food sourc-
es. In these cases, only a few informed individuals may have pertinent information
about the required directions of motion. In this section, we will study how a small
percentage of informed individuals can have a global impact that results in control
of the whole group toward desired goals. The role of different leaders was discussed
in [16].
The material in this section is from Couzin et al. [15]. Some species have evolved
specialized mechanisms for conveying information about the location and direction
of goals. One example is the waggle dance of the honeybee that recruits hive mem-
bers to visit food sources. However, in many groups such as schools of fish, bird
flocks, and mammal herds on the move evidence supports the idea that the decisions
made by all individuals follow simple local protocols based on nearest neighbors

| 1.1  Synchronization in Nature and Social Systems  |     |     |     |     |     |     |     | 9   |
| -------------------------------------------------- | --- | --- | --- | --- | --- | --- | --- | --- |
similar to Reynolds’ rules. Mechanisms of information transfer in groups involve
questions such as how information about required motion directions, originally held
by only a few informed individuals, can propagate through an entire group by sim-
ple mechanisms that are the same for every individual. It is not clear how individu-
als recognize leaders who are informed, or even if this is required, or how conflict
is resolved when several informed individuals differ in their motion preferences.
 Protocols for Leadership by a Small Percentage of Informed Individuals
The setup used in Couzin et al. [15] is as follows. Consider a set of N agents and
let the communication between the agents be modeled by a general directed graph.
The edges of the graph correspond to agents that are close together in some sense
depending on the specific animal group considered, as discussed in the previous
section. Each agent has a position vector, a direction vector, and a speed of motion.
One dynamics that captures this for motion in the (x,y)-plane is the discrete-
time dynamics
|     |     | p (k | 1)  | p (k) V | (k)T      | cosθ (k) |     |        |
| --- | --- | ---- | --- | ------- | --------- | -------- | --- | ------ |
|     |     | i    | + = | i +     | i         | i        |     |        |
|     |     | q (k | 1)  | q (k) V | (k)T sinθ | (k)      |     | (1.15) |
|     |     | i    |     | i       | i         | i        |     |        |
|     |     |      | + = | +       |           |          |     |        |
where V  is the speed of agent i,  θ i its heading, and  x [p q ]T  its position.
|     | i   |     |     |     |     | i = | i i |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
The time index is k and the sampling period is T. This is the discrete-time version of
(1.9). The velocity vector of agent i is
T
|     |     | v (k) | V (k)cosθ | (k) | V (k)sinθ | (k) |     | (1.16) |
| --- | --- | ----- | --------- | --- | --------- | --- | --- | ------ |
|     |     | i     | i         | i   | i         | i   |     |        |
=
|     |     |     | (cid:31) |     |     |     | (cid:30) |     |
| --- | --- | --- | -------- | --- | --- | --- | -------- | --- |
Each agent turns away from others in a collision avoidance region Nc according to
i
|     |     |           |     | x     | (k)-x | (k) |     |        |
| --- | --- | --------- | --- | ----- | ----- | --- | --- | ------ |
|     |     | θ(k+1)=-∑ |     | c     | j     | i   |     |        |
|     |     | i         |     | ij    |       |     |     | (1.17) |
|     |     |           |     | x     | (k)-x | (k) |     |        |
|     |     |           |     | j∈N c | j     | i   |     |        |
i
|     |     | cosθ (k+1) |     |     |     |     |     |     |
| --- | --- | ------------ | --- | --- | --- | --- | --- | --- |
where θ (k+1)= i . This causes agent i to turn away from other agents
|     | i   |              |     |     |     |     |     |     |
| --- | --- | ------------- | --- | --- | --- | --- | --- | --- |
|     |     |  sinθ (k+1) |     |     |     |     |     |     |
i
inside the collision neighborhood. If agents are not detected within the collision
avoidance region, then each agent will turn toward and align with its neighbors in
| an interaction region N |     |  according to |     |     |     |     |     |     |
| ----------------------- | --- | ------------- | --- | --- | --- | --- | --- | --- |
i
|     |         |        |     | x (k)-x | (k) |        | v (k) |        |
| --- | ------- | ------ | --- | ------- | --- | ------ | ----- | ------ |
|     |         | ∑      |     | j i     |     | ∑      | j     |        |
|     | θ(k+1)= |        | a   |         | +   | a      |       | (1.18) |
|     | i       |        | ij  |         |     |        | ij    |        |
|     |         |        |     | x (k)-x | (k) |        | v (k) |        |
|     |         | j∈N\Nc |     | j i     |     | j∈N\Nc | j     |        |
|     |         |        | i i |         |     | i i    |       |        |

10 1 Introduction to Synchronization in Nature and Physics and Cooperative …
This is converted to a unit vector by
θ(k+1)
θˆ i (k+1)= i (1.19)
θ(k+1)
i
A small percentage p of the group consists of informed individuals i, each of whom
has a preferred desired direction of motion given by a unit reference direction vector
r i. The final heading control protocols for (1.15) are therefore taken as
cosθ(k+1) θˆ (k+1)+g r
 i = i i i (1.20)
sinθ i (k+1) θˆ i (k+1)+g i r i
with g 0 being a leader weighting gain. If g 0, agent i is not informed,
i i
≥ =
exhibits no preferred direction of travel, and merely aligns with his neighbors. If
g >0, agent i is an informed individual and, as g increases, agent i exhibits a
i i
stronger desire to move in its reference direction r i.
1.2 Networks of Coupled Dynamical Systems
in Nature and Science
The study of networks of coupled dynamical systems arises in many fields of re-
search. Charles Darwin [1] showed that the interactions between coupled biological
species over long timescales are responsible for natural selection. Adam Smith [2]
showed that the dynamical relationships between geopolitical entities are respon-
sible for the balances in international finance and the wealth of nations.
In this section, we look at some collective synchronization phenomena in biol-
ogy, sociology, physics, chemistry, and human-engineered systems. The nature of
synchronization in different groups depends on the manner in which information
is allowed to flow between the individuals of the group. Therefore, we also study
several different types of graph topologies which support different types of informa-
tion flows and have different basic properties. These different topologies result in
different sorts of synchronization behaviors. Finally, we give a literature survey of
cooperative control of multi-agent dynamical systems on communication graphs,
which is the topic of interest in this book.
1.2.1 Collective Motion in Biological and Social Systems,
Physics and Chemistry, and Engineered Systems
Distributed networks of coupled dynamical systems have received much attention
over the years because they occur in many different fields including biological and

1.2 Networks of Coupled Dynamical Systems in Nature and Science 11
social systems, physics and chemistry, and computer science. Various terms are
used in the literature for phenomena related to collective behavior regarding net-
works of systems, such as flocking, consensus, synchronization, formation, rendez-
vous, and so on.
In many biological and sociological groups, such as schools of fish, bird flocks,
mammal herds on the move, and human panic behavior in emergency building
evacuation, evidence supports the idea that the decisions made by all individuals
follow simple local protocols based on their nearest neighbors. Mechanisms of in-
formation transfer in groups involve questions such as how information about re-
quired motion directions, originally held by only a few informed individuals, can
propagate through an entire group by simple mechanisms that are the same for
every individual.
Reynolds developed a distributed behavioral model for animal flocks, herds, and
schools [6]. He presented three rules by which decisions are made by agents using
information only from their nearest neighbors. Reynolds rules are: collision avoid-
ance, avoid collisions with neighbors; velocity matching, match speed and direction
of motion with neighbors; and flock centering, stay close to neighbors. Couzin et al.
[15] studied leadership and decision making in animal groups on the move. They
showed that by using protocols based only on local neighbor information, a small
percentage of informed individuals can have a global impact that results in control
of the whole group toward desired goals. The role of different types of leaders was
studied in [16].
Axelrod [5] studied the evolution of cooperation in social groups. Strogatz and
Stewart [8] studied coupled oscillator effects in biological synchronization. Was-
serman and Faust [9] provided analysis methods for social networks. Helbing et al.
[14] showed that local neighbor responses can accurately model the panic behavior
of crowds during emergency building evacuation. The spread of infectious diseases
in structured populations was studied by Sattenspiel and Simon [7]. Metabolic sta-
bility in random genetic nets was studied by Kauffman [3].
Kuramoto [4] analyzed local coupling in populations of chemical oscillators to
study waves and turbulence. He showed that there is a critical information coupling
coefficient, above which coupled oscillators synchronize. The dynamics of a ring of
pulse-coupled oscillators were studied by Bresslof et al. [13]. Results on frequency-
locking dynamics of disordered Josephson arrays were given by Wiesenfeld [12].
In 1995, Vicsek et al. [11] reported interesting results of collective behaviors of
self-driven particles in phase transition. They showed that by using nearest neighbor
interaction rules, all agents eventually move in the same direction.
The ability to coordinate agents is important in many real-world decision tasks
where it is necessary for agents to exchange information with each other. Distrib-
uted local decision and control algorithms are often desirable due to their compu-
tational simplicity, flexibility, and robustness to the loss of single agents. Parallel
problem solving was studied by Das et al. [10] based on phenomena in nature.
In the past few decades, an increasing number of industrial, military, and con-
sumer applications have called for the coordination of multiple interconnected
agents. Research on behaviors of networked cooperative systems, or multi-agent

12 1 Introduction to Synchronization in Nature and Physics and Cooperative …
systems, and distributed decision algorithms has received extensive attention due
to their widespread applications in spacecraft, unmanned air vehicles (UAVs) [19],
multi-vehicle systems [21], mobile robots, multipoint surveillance [18], sensor net-
works [20], networked autonomous teams, and so on. See [17, 18] for surveys of
engineering applications of cooperative multi-agent control systems.
1.2.2 Graph Topologies and Structured Information Flow in
Collective Groups
It is seen from different social groups that the type of collective motion of the over-
all group depends on the manner in which information is allowed to flow between
the individuals of the group. In this section, we study several different types of
graph topologies which support different types of information flows and have dif-
ferent basic properties. These different topologies result in different sorts of syn-
chronization behaviors. We shall discuss random graphs, small-world networks,
scale-free networks, and distance graphs. A review of graph topologies is given by
Strogatz [22].
Random Graphs
The growth, evolution, and properties of random graphs were studied by Erdos and
Renyi [23] and Bollobas [24]. Random graphs are a class of undirected graphs.
In random graphs, there are N agents that are initially disconnected. It is
desired to form m edge links between these agents in a random fashion. This is
accomplished by selecting two agents at random, and with probability p form-
ing an edge between them. This is repeated until all of the m edges have been
disbursed.
Phase Transitions The key factor in the growth of random graphs is the relation-
ship between the number of agents N and the allowed number of edges m. It is found
that there exists a threshold value m* such that for m > m* a large connected compo-
nent of the graph emerges. The value of this threshold is shown to be m* N/2. This
=
giant cluster contains most of the N nodes in the graph. It is connected in the sense
that one can move from any agent in the cluster to any other agent in the cluster by
following the graph edges.
A sample random graph topology is shown in Fig. 1.3. The graph agents have
been reorganized to show connected components. A giant connected cluster is clear-
ly seen in this figure.
Phase transitions are of extreme importance in graph theory. They capture transi-
tions between phases, for instance, in chemical and physical systems, as well as the
transition between normal behavior and panic behavior in human crowds.
Note that a random graph is connected if m ln(N) [24].
≥

1.2 Networks of Coupled Dynamical Systems in Nature and Science 13
F ig. 1.3 Random graph
showing a giant connected
component. (Courtesy of
[22])
Small-World Networks
Random graphs represent one extreme of graph organization, namely complete dis-
organization. Regular lattices represent another extreme where the graph is com-
pletely organized. An undirected graph is regular if all nodes have the same number
of neighbors. Small-world networks provide a method for generating graph topolo-
gies that interpolate between these two extremes. The material here is from [25].
In human social groups, we can define a graph by friendship links. That is, an
edge exists between two individuals if they are friends. In today’s global society,
it is observed that, remarkably, any two individuals selected at random worldwide
are connected by a path made up of friendship links. Moreover, the length of this
friendship path is generally equal to six edges. That is to say, two people who meet
at random can find a path of length six that connects them together through pairs of
mutual friends. Now, with the advent of Facebook and Twitter, this friendship short-
est path is no doubt decreasing.
Regular graphs and random graphs cannot capture the small-world connectivity
phenomenon of social networks. To construct networks with the small-world prop-
erty, Watts and Strogatz proceeded as follows [25]. Start with a regular ring lattice.
Cycle through all the edges once, with probability p rewiring one end of each edge
to a node selected uniformly at random from all edges in the graph. Repeated edges
are not allowed.
Figure 1.4 shows the graphs resulting from this procedure for various values of
the rewiring probability p. It is seen that the small-world graphs form a continuum
between the regular ring lattices and the random graphs that is a function of p.

14 1 Introduction to Synchronization in Nature and Physics and Cooperative …
Fig. 1.4 Random rewiring procedure for generating small-world networks that interpolate between
a regular ring lattice and a random graph. Courtesy of [25]
To study the properties of small-world networks, two concepts are defined. De-
fine the characteristic path length L( p) as the number of edges in the shortest path
connecting any two vertices, averaged over all pairs of vertices. The characteristic
path length is a global quantity related to the graph diameter. The clustering coef-
ficient captures the local connectivity properties of the graph. Suppose a node has k
neighbors. Then, these k neighbors have at most k(k 1)/2 edges between them,
−
which occurs when all the neighbor pairs have edges connecting them. Let (cid:31) be the
number of edges that actually exist between the neighbors. The fraction of edges
that actually exist out of all possible edges is (cid:31)/(k(k 1)/2). Then, the clustering
−
coefficient is defined as the average of this ratio over all nodes in the graph.
In terms of human social groups, L( p) is the average number of friendships in the
shortest chain connecting two people. The clustering coefficient C( p) measures how
many friends of an individual are also friends of each other, and hence captures the
cliquishness of the group.
Figure 1.5 shows the change in the characteristic path length and the clustering
coefficient as a function of rewiring probability p. It is seen that with even a few
rewired edges, the path length decreases dramatically, whereas the clustering coef-
ficient remains approximately the same. This means that a few rewired edges result
in a few long hops that decrease the friendship distance between nodes in the graph,
while the local friendship structures in the graph are preserved.
The fast change of the characteristic path length with p is a phase transition phe-
nomenon of the sort discussed above in connection with random graphs.
It is shown in [25] that both the collaboration graph of movie actors and the
western US electric power grid are small-world networks. Moreover, small-world
networks explain the spread patterns of infectious diseases in humans.
Homogeneity Property of Random Graphs and Small-World Networks In both
the random graphs and the small-world networks, most nodes have the same num-
bers of neighbors. This is known as the homogeneity property and expresses the fact
that the nodes are anonymous in the sense that they have the same neighborhood

1.2 Networks of Coupled Dynamical Systems in Nature and Science 15
Fig. 1.5 Characteristic path length L( p) and clustering coefficient C( p) for small-world networks
as a function of rewiring probability p. (Courtesy of [25])
structures. The number of neighbors of a node in an undirected graph is known as its
degree. The degree distribution P(k) is the probability that a node has degree k in a
given graph. For random graphs, the degree distribution is Poison. Figure 1.6 shows
Poisson distributions for some representative values of the defining parameter λ. It
is seen that the probability of having k neighbors decreases quickly either above or
below the mean value.
Scale-Free Networks
In random graphs and small-world networks, the nodes are homogeneous in the
sense that most nodes have the same number of neighbors. That is, the nodes are
anonymous in terms of their degrees. Figure 1.7 shows the domestic route map of
China Southern Airlines in China. This network has an immediately visible feature
that is not explained by random graphs or small-world networks. Namely, there are
a few large hubs that are directly connected to each other, while most nodes are con-
nected only to these large hubs.
In human social networks, it is usually the case that there are a few very influ-
ential individuals with many friends, with most individuals having fewer friends.
The degree, or number of friends, can be interpreted as the social standing of an
individual. In these networks, the nodes are not anonymous, but a few are more
influential.
The properties of graphs with a few well-connected nodes were studied as the
emergence of scaling in random networks by Barabasi and Albert [26]. They con-

16 1 Introduction to Synchronization in Nature and Physics and Cooperative …
F ig. 1.6 Poisson degree dis-
tribution for random graphs,
showing P( k), the probability
that a node has degree k, vs. k
Fig. 1.7 Domestic route map for China Southern Airlines, showing a few well-connected large
hubs. (Courtesy of GCW Consulting)
sidered two new features that are not present in random graphs or small-world net-
works. First, actual networks in real-life applications exhibit growth. Think of the
World Wide Web and the collaboration network of scientific authors, both of which
accrue new nodes as time passes. Second, new nodes attach themselves preferen-
tially to existing nodes with large degree, or social influence.

1.2 Networks of Coupled Dynamical Systems in Nature and Science 17
F ig. 1.8 Scale-free network
showing a few large well-
connected nodes and many
small nodes. (Courtesy of
Prof. Hawoong Jeong and
[27])
To construct graphs that exhibit growth and preferential attachment, they pro-
ceeded as follows. Start with a small number,m , of nodes. At every time step,
0
add a new node that links to m m existing nodes in the network. These links
0
≤
are made preferentially to existing nodes with large degrees as follows. Define the
degree of node i as k i. The volume of the graph is defined as the sum of the de-
grees Vol =∑ k. Then, the m new links are connected to node i with probability
i i
(cid:31)(i) k / k .
= i j j
A sample network grown by this algorithm is shown in Fig. 1.8. It has a few
(cid:31)
nodes with large degree and many with small degree. A node is said to be large if
it has many neighbors. This connection probability growth model results in new
nodes connecting preferentially to larger existing nodes, and results in large nodes
becoming larger. It explains the airline network and social network just discussed.
As the number of time steps becomes large, the network evolves into a graph that
has a power law degree distribution P(k) k γ, with γ approximately equal to 3.
−
=
This is a scale-free state that does not depend on the number of nodes in the graph.
A power law distribution is shown in Fig. 1.9.
In [26], it is shown that many well-known networks are scale-free with power
law distributions P(k) k γ. The collaboration network of movie actors (212,250
−
=
nodes) has actors as nodes and an edge if two actors were in the same movie, and is
scale-free with γ 2.3. The World Wide Web (800 million nodes) has web pages
≈
as nodes and an edge if one page points to another, and has γ 2.1. The electric
≈
power grid in the western USA (4941 nodes) has edges corresponding to transmis-
sion lines and has γ 4.
≈
Distance Graphs
In vehicle formations, mobile sensor networks, and the animal synchronization
examples described in Sect. 1.1, the connectivity of the graph depends on the

18 1 Introduction to Synchronization in Nature and Physics and Cooperative …
F ig. 1.9 Power law degree 100
distribution showing P( k), the
probability that a node has
degree k, vs. k 10−2
(cid:51)(cid:11)(cid:78)(cid:12)(cid:32)(cid:78)(cid:237)(cid:22)
10−4
10−6
10−8
10−10
100 101 102 103
F ig. 1.10 Distance or Prox- y
imity graph with interaction
radius of d
2d
X
maximum communication or sensing range of each individual agent. Given any
node, its neighbors are those nodes that fall within its communication range. As
the agents move and the separation distances change, new edges may form and
the existing edges may break. The result is a time-varying dynamically changing
graph topology. This distance or proximity graph idea also describes the connec-
tivity in flocks of birds and animal herds on the move. A distance graph is shown
in Fig. 1.10.
Research has shown that a social group on a time-varying distance graph still
has cohesiveness and responds as a single collective as long as some conditions
on the graph topology are satisfied. Although the graph may not be connected at
one particular time, the union of the time-varying graphs should be connected over
intervals of time. Many papers have been written about defining potential fields or
distributed motion protocols that guarantee that the group does not lose connectivity
(see, for instance, [31, 32, 37–41]). Quite interesting in this context are the potential
field methods [34–36].

1.3 Cooperative Control of Multi-Agent Systems on Communication Graphs 19
1.3 Cooperative Control of Multi-Agent Systems on
Communication Graphs
The main interest of this book is cooperative control of multi-agent dynamical systems
interconnected by a communication graph topology. The links of the graph represent
the allowed information flow between the systems. In general, directed graphs are
used to represent the direction of the allowed flow of information. In cooperative con-
trol systems on graphs, there are intriguing interactions between the individual agent
dynamics and the topology of the communication graph. The graph topology may
severely limit the possible performance of any control laws used by the agents. More-
over, in cooperative control on graphs, all the control protocols must be distributed in
the sense that the control law of each agent is only allowed to depend on information
from its immediate neighbors in the graph topology. If enough care is not shown in the
design of the local agent control laws, the individual agent dynamics may be stable,
but the networked systems on the graph may exhibit undesirable behaviors.
In cooperative control, each agent is endowed with its own state variable and
dynamics. A fundamental problem in multi-agent dynamical systems on graph is the
design of distributed protocols that guarantee consensus or synchronization in the
sense that the states of all the agents reach the same value. The states could repre-
sent vehicle headings or positions, estimates of sensor readings in a sensor network,
oscillation frequencies, trust opinions of each agent, and so on.
The principles of networked dynamical systems that we have discussed in this
chapter have been applied to the cooperative control problem. Distributed decision
and parallel computation algorithms were studied and developed in [28–30]. The
field of cooperative control was started in earnest with the two seminal papers in
2003 [31] and 2004 [32]. Early work was furthered in [33, 37–39]. In the develop-
ment of cooperative control theory, work was generally done initially for simple
systems including first-order integrator dynamics in continuous time and discrete
time. Then, results were established for second-order systems and higher order dy-
namics. Applications were made to vehicle formation control and graphs with time-
varying topologies and communication delays (see [40–45]).
Early work focused on reaching consensus or synchronization of networks of
anonymous dynamical systems, where all agents have the same role. This is known
as the leaderless consensus problem or the cooperative regulator problem. Later
work focused on synchronization to the dynamics of a leader or root node which
generates a command target trajectory. This is the controlled consensus problem or
the cooperative tracker. We shall have more to say about the background references
and the design techniques for these problems in subsequent chapters.

20 1 Introduction to Synchronization in Nature and Physics and Cooperative …
References
Networks of Coupled Dynamical Systems. Collective Motion in Biological and Social Sys-
tems, Physics and Chemistry, and Engineered Systems
1. Darwin CR (1859) The Origin of Species. John Murray Publisher, London
2. Smith A (1776) An Inquiry into the Nature and Causes of the Wealth of Nations. Strahan and
Cadell, London
3. Kauffman SA (1969) Metabolic stability and epigenesis in randomly constructed genetic
nets. J Theor Biol 22:437–467
4. Kuramoto Y (1984) Chemical Oscillations, Waves, and Turbulence. Springer, Berlin
5. Axelrod R (1984) The Evolution of Cooperation. Basic Books, New York
6. Reynolds CW (1987) Flocks, herds, and schools: a distributed behavioral model. Comput
Graphics 21(4):25–34
7. Sattenspiel L, Simon CP (1988) The spread and persistence of infectious diseases in struc-
tured populations. Math Biosci 90:341–366
8. Strogatz SH, Stewart I (1993) Coupled oscillators and biological synchronization. Sci Am
269(6):102–109
9. Wasserman S, Faust K (1994) Social Network Analysis: Methods and Applications. Cam-
bridge University Press, Cambridge
10. Das R, Mitchell M, Crutchfield JP (1994) Parallel Problem Solving from Nature. In: Davido
Y, Schwefel H-P, Manner R (eds) Lecture Notes in Computer Science 866. Springer, Berlin,
pp 344–353
11. Vicsek T, Czirok A, Ben-Jacob E, Cohen I, Shochet O (1995) Novel type of phase transition
in a system of self-driven particles. Phys Rev Lett 75(6):1226–1229
12. Wiesenfeld K (1996) New results on frequency-locking dynamics of disordered Josephson
arrays. Physica B 222:315–319
13. Bressloff PC, Coombes S, De Souza B (1997) Dynamics of a ring of pulse-coupled oscilla-
tors: a group theoretic approach. Phys Rev Lett 79:2791–2794
14. Helbing D, Farkas I, Vicsek T (2000) Simulating dynamical features of escape panic. Nature
407:487–490
15. Couzin ID, Krause J, Franks NR, Levin SA (2005) Effective leadership and decision-making
in animal groups on the move. Nature 533:513–516
16. Wang W, Slotine J (2006) A theoretical study of different leader roles in networks. IEEE
Trans Autom Control 51(7):1156–1161
17. Defoort M, Floquet T, Kokosy A, Perruquetti W (2008) Sliding-mode formation control for
cooperative autonomous mobile robots. IEEE Trans Ind Electron 55(11):3944–3953
18. Cruz D, McClintock J, Perteet B, Orqueda O, Cao Y, Fierro R (2007) Decentralized coopera-
tive control—a multivehicle platform for research in networked embedded systems. IEEE
Control Syst Mag 27(3):58–78
19. Wang X, Yadav V, Balakrishnan S (2007) Cooperative UAV formation flying with obstacle/
collision avoidance. IEEE Trans Contr Syst Technol 15(4):672–679
20. Chen J, Cao X, Cheng P, Xiao Y, Sun Y (2010) Distributed collaborative control for in-
dustrial automation with wireless sensor and actuator networks. IEEE Trans Ind Electron
57(12):4219–4230
21. Murray R (2007) Recent research in cooperative control of multivehicle systems. J Dyn Syst
Meas Control 129(5):571–583
Types of Graph Topologies and Structured Information Flow in Collective Groups
22. Strogatz SH (2001) Exploring complex networks. Nature 410:268–276
23. Erdos P, Renyi A (1960) On the evolution of random graphs. Publ Math Inst Hung Acad Sci
5:17–61
24. Bollobas B (1985) Random Graphs. Academic Press, London

References 21
25. Watts DJ, Strogatz SH (1998) Collective dynamics of small world networks. Nature 393:440–
442
26. Barabasi AL, Albert R (1999) Emergence of scaling in random networks. Science 286:509–
512
27. Jeong H, Mason SP, Barabasi A-L, Oltvai ZN (2001) Lethality and centrality in protein net-
works. Nature 411:41–42
Distributed Computation and Cooperative Control of Multi-Agent Systems on Graphs
28. Tsitsiklis J (1984) Problems in Decentralized Decision Making and Computation. Ph.D. dis-
sertation, Dept. Elect. Eng. and Comput. Sci. MIT, Cambridge, MA
29. Tsitsiklis J, Bertsekas D, Athans M (1986) Distributed asynchronous deterministic and sto-
chastic gradient optimization algorithms. IEEE Trans Autom Control 31(9):803–812
30. Bertsekas D, Tsitsiklis JN (1997) Parallel and Distributed Computation: Numerical Methods.
Athena Scientific, Belmont, MA
31. Jadbabaie A, Lin J, Morse A (2003) Coordination of groups of mobile autonomous agents
using nearest neighbor rules. IEEE Trans Autom Control 48(6):988–1001
32. Olfati-Saber R, Murray R (2004) Consensus problems in networks of agents with switching
topology and time-delays. IEEE Trans Autom Control 49(9):1520–1533
33. Fax J, Murray R (2004) Information flow and cooperative control of vehicle formations.
IEEE Trans Autom Control 49(9):1465–1476
34. Leonard NE, Fiorelli E (2001) Virtual leaders, artificial potentials, and coordinated control of
groups. In: Proc. IEEE Conf. Decision Control, Orlando, FL, pp. 2968–2973
35. Gazi V, Passino KM (2003) Stability analysis of swarms. IEEE Trans. Autom Control
48(4):692–697
36. Gazi V, Passino KM (2004) Stability analysis of social foraging swarms. IEEE Trans Sys
Man Cyber-Part B: Cybernetics 34(1):539–557
37. Ren W, Beard R (2005) Consensus seeking in multiagent systems under dynamically chang-
ing interaction topologies. IEEE Trans Autom Control 50(5):655–661
38. Moreau L (2005) Stability of multiagent systems with time-dependent communication links.
IEEE Trans Autom Control 50(2):169–182
39. Ren W, Beard R, Atkins E (2005) A survey of consensus problems in multi-agent coordina-
tion. In: Proc. Amer. Control Conf., Portland, OR, pp. 1859–1864
40. Han J, Li M, Guo L (2006) Soft control on collective behavior of a group of autonomous
agents by a shill agent. J Syst Sci Complexity 19:54–62
41. Ren W, Beard R, Atkins E (2007) Information consensus in multivehicle cooperative control.
IEEE Control Syst Mag 27(2):71–82
42. Ren W, Moore K, Chen Y (2007) High-order and model reference consensus algorithms in
cooperative control of multivehicle systems. J Dyn Syst Meas Control 129(5):678–688
43. Olfati-Saber R, Fax J, Murray R (2007) Consensus and cooperation in networked multi-agent
systems. Proc IEEE 95(1):215–233
44. Zhu W, Cheng D (2010) Leader-following consensus of second-order agents with multiple
time-varying delays. Automatica 46(12):1994–1999
45. Ren W, Cao C (2011) Distributed Coordination of Multi-Agent Networks: Emergent Prob-
lems, Models, and Issues. Springer-Verlag, London

Chapter 2
Algebraic Graph Theory and Cooperative
Control Consensus
Cooperative control studies the dynamics of multi-agent dynamical systems linked
to each other by a communication graph. The graph represents the allowed infor-
mation flow between the agents. The objective of cooperative control is to devise
control protocols for the individual agents that guarantee synchronized behavior of
the states of all the agents in some prescribed sense. In cooperative systems, any
control protocol must be distributed in the sense that it respects the prescribed graph
topology. That is, the control protocol for each agent is allowed to depend only on
information about that agent and its neighbors in the graph. The communication re-
strictions imposed by graph topologies can severely limit what can be accomplished
by local distributed control protocols at each agent. In fact, the graph topological
properties complicate the design of synchronization controllers and result in intrigu-
ing behaviors of multi-agent systems on graphs that do not occur in single-agent,
centralized, or decentralized feedback control systems.
Of fundamental concern for cooperative systems on graphs is the study of their
collective behaviors under the influence of the information flow allowed in the
graph. This chapter introduces cooperative synchronization control of multi-agent
dynamical systems interconnected by a fixed communication graph topology. Each
agent or node is mathematically modeled by a dynamical linear time-invariant (LTI)
system. First, in Sect. 2.1 we give a review of graph basics and algebraic graph the-
ory, which studies certain matrices associated with the graph. The graph Laplacian
matrix is introduced and its eigenstructure is studied, including the first eigenvalue,
the first left eigenvector, and the second eigenvalue or Fiedler eigenvalue.
In Sect. 2.2, dynamical systems on graphs are introduced. The idea of distributed
control and the consensus problem are introduced. Section 2.3 studies consensus
for first-order integrator dynamics for continuous-time systems. The basic results
and key ideas of cooperative control emerge from this study. The importance of the
graph eigenstructure in interconnected agent dynamical behavior is shown. Sec-
tion 2.4 reveals the existence of certain motion invariants for consensus on graphs.
Section 2.5 studies consensus for first-order discrete-time systems.
Section 2.6 introduces consensus for general linear dynamical systems on
graphs. A fundamental result is given that relates the synchronization of multi-agent
systems to the stability of a set of systems that depend on the graph topology prop-
F. L. Lewis et al., Cooperative Control of Multi-Agent Systems, 23
Communications and Control Engineering, DOI 10.1007/978-1-4471-5574-4_2,
© Springer-Verlag London 2014

24 2 Algebraic Graph Theory and Cooperative Control Consensus
erties. This reveals the relationships between local agent feedback design and the
global synchronization properties based on the graph communication restrictions.
Section 2.7 studies consensus for second-order position–velocity systems which
include motion control in formations.
In Sect. 2.8, we present some key concepts needed in this book for the design of
optimal and adaptive distributed controllers on graphs. The section introduces sev-
eral important matrix analysis methods for systems in graphs, including irreducible
matrices, Frobenius form, stochastic matrices, and M-matrices. Relationships with
the graph topology and eigenstructure are given.
In Sect. 2.9, we introduce Lyapunov functions for the analysis of the stability
properties of cooperative multi-agent control systems. It is seen that Lyapunov
functions for studying the stability properties of cooperative control protocols de-
pend on the graph topology. Therefore, a given cooperative control protocol may be
stable on one graph topology but not on another. This reveals the close interactions
between the performance of locally designed control protocols and the manner in
which the agents are allowed to communicate.
This chapter follows the development of cooperative control results in the early
literature since the first papers [7, 9, 10, 15, 22]. To understand the relationships be-
tween the communication graph topology and the local design of distributed feed-
back control protocols, it was natural to study first-order systems and then second-
order systems. Early applications were made to formation control [13, 14, 16, 18].
These studies brought an understanding of the limitations and caveats imposed by
the graph communication restrictions and opened the way for many well-known
results from systems theory to be extended to the case of multi-agent systems on
graphs.
The relations discovered between the communication graph topology and the
design of distributed control protocols have resulted in new design techniques for
cooperative feedback control. New intriguing interactions have been discovered be-
tween graph topology and local control protocol design that reveal the richness of
the study of cooperative multi-agent control on graphs, where new phenomena are
seen that do not occur in control of single-agent systems. In the remainder of the
book, we explore these relationships for optimal design and adaptive control on
graphs.
2.1 Algebraic Graph Theory
In this book, we are concerned with the behaviors and interactions of dynamical
systems that are interconnected by the links of a communication network. This
communication network is modeled as a graph with directed edges corresponding
to the allowed flow of information between the systems. The systems are modeled
as the nodes in the graph and are sometimes called agents. We call this the study of
multi-agent dynamical systems on graphs. The fundamental control issues concern

| 2.1   Algebraic Graph Theory  |     |     |     | 25  |
| ----------------------------- | --- | --- | --- | --- |
how the graph topology interacts with the local feedback control protocols of the
agents to produce overall behaviors of the interconnected nodes.
2.1.1   Graph Theory Basics
Here we present some basic graph theory concepts that are essential in the study of
multi-agent dynamical systems. Good references are [3, 5].
 Basic Definitions and Connectivity
A graph is a pair G=(V,E) with V ={v,,v } being a set of N nodes or ver-
1 N
tices and E a set of edges or arcs. Elements of E are denoted as (v,v ) which is
|     |     |     |     | i j |
| --- | --- | --- | --- | --- |
termed an edge or arc from v to v, and represented as an arrow with tail at v and
|     | i j |     |     | i   |
| --- | --- | --- | --- | --- |
head at v. We assume the graph is simple, i.e., (v,v)∉E,∀i no self-loops, and no
| j   |     | i i |     |     |
| --- | --- | --- | --- | --- |
multiple edges between the same pairs of nodes. Edge (v,v ) is said to be outgo-
i j
ing with respect to node v and incoming with respect to v; and node v is termed
|     | i   |     | j   | i   |
| --- | --- | --- | --- | --- |
the parent and v the child. The in-degree of v is the number of edges having v as
| j   |     | i   |     | i   |
| --- | --- | --- | --- | --- |
a head. The out-degree of a node v is the number of edges having v as a tail. The
|     | i   |     |     | i   |
| --- | --- | --- | --- | --- |
set of (in-) neighbors of a node v is N ={v :(v ,v)∈E}, i.e., the set of nodes
|     | i i | j j i |     |     |
| --- | --- | ----- | --- | --- |
with edges incoming to v. The number of neighbors  N  of node v is equal to its
i
|     | i   |     |     | i   |
| --- | --- | --- | --- | --- |
in-degree.
If the in-degree equals the out-degree for all nodes v ∈V the graph is said to be
i
balanced. If (v,v )∈E⇒(v ,v)∈E,∀i, j the graph is said to be bidirectional,
| i j | j i |     |     |     |
| --- | --- | --- | --- | --- |
otherwise it is termed a directed graph or digraph. Associate with each edge
(v ,v)∈E a weight a . Note the order of the indices in this definition. We assume
ij
j i
in this chapter that the nonzero weights are strictly positive. A graph is said to be
undirected if a =a ,∀i, j, that is, if it is bidirectional and the weights of edges
| ij ji |     |     |     |     |
| ----- | --- | --- | --- | --- |
(v,v ) and (v ,v) are the same.
| i j j i |     |     |     |     |
| ------- | --- | --- | --- | --- |
A directed path is a sequence of nodes  v ,v,,v  such that  (v,v )∈E,
|     |     | 0 1 | r   | i i+1 |
| --- | --- | --- | --- | ----- |
i∈{0,1,,r−1}. Node v is said to be connected to node v if there is a directed path
|     | i   |     | j   |     |
| --- | --- | --- | --- | --- |
from v to v. The distance from v to v is the length of the shortest path from v to v.
| i j | i j |     |     | i j |
| --- | --- | --- | --- | --- |
Graph G is said to be strongly connected if v,v  are connected for all distinct nodes
i j
v,v ∈V. For bidirectional and undirected graphs, if there is a directed path from v
i j i
to v, then there is a directed path from v to v, and the qualifier ‘strongly’ is omitted.
| j   | j   | i   |     |     |
| --- | --- | --- | --- | --- |
A (directed) tree is a connected digraph where every node except one, called
the root, has in-degree equal to one. A spanning tree of a digraph is a directed tree
formed by graph edges that connects all the nodes of the graph. A graph is said to
have a spanning tree if a subset of the edges forms a directed tree. This is equivalent
to saying that all nodes in the graph are reachable from a single (root) node by fol-
lowing the edge arrows. A graph may have multiple spanning trees. Define the root
set or leader set of a graph as the set of nodes that are the roots of all spanning trees.

26 2 Algebraic Graph Theory and Cooperative Control Consensus
If a graph is strongly connected, it contains at least one spanning tree. In fact, if a
graph is strongly connected, then all nodes are root nodes.
2.1.2 Graph Matrices
Graph structure and properties can be studied by examining the properties of cer-
tain matrices associated with the graph. This is known as algebraic graph theory
[3, 5].
Given the edge weights a , a graph can be represented by an adjacency or con-
ij
nectivity matrix A = [a ij ] with weights a ij >0if (v j ,v i )∈E and a ij =0 other-
wise. Note that a =0. Define the weighted in-degree of node v as the i-th row sum
ii i
of A
N
d =∑a (2.1)
i ij
j=1
and the weighted out-degree of node v as the i-th column sum of A
i
N
do =∑a (2.2)
i ji
j=1
The in-degree and out-degree are local properties of the graph. Two important glob-
al graph properties are the diameter Diam G, which is the greatest distance between
two nodes in a graph, and the (in-)volume, which is the sum of the in-degrees
VolG=∑d (2.3)
i
i
The adjacency matrix A of an undirected graph is symmetric, A= AT. A graph is
said to be weight balanced if the weighted in-degree equals the weighted out-degree
for all i. If all the nonzero edge weights are equal to 1, this is the same as the defi-
nition of balanced graph. An undirected graph is weight balanced, since if A= AT
then the ith row sum equals the ith column sum. We may be loose at times and refer
to node v simply as node i, and refer simply to in-degree, out-degree, and the bal-
i
anced property, without the qualifier ‘weight’, even for graphs having non-unity
weights on the edges.
Graph Laplacian Matrix Define the diagonal in-degree matrix D=diag{d} and
i
the (weighted) graph Laplacian matrix L= D−A. Note that L has all row sums
equal to zero. Many properties of a graph may be studied in terms of its graph
Laplacian. In fact, we shall see that the Laplacian matrix is of extreme importance
in the study of dynamical multi-agent systems on graphs.

2.1 Algebraic Graph Theory 27
F ig. 2.1 A directed graph
F ig. 2.2 A spanning tree for
the graph in Fig. 2.1 with root
node 1
Example 2.1 Graph Matrices
Consider the digraph shown in Fig. 2.1 with all edge weights equal to 1. The graph
is strongly connected since there is a path between any two pairs of nodes. A span-
ning tree with root node 1 is shown in bold in Fig. 2.2. There are other spanning
trees in this graph. In fact, every node is a root node since the graph is strongly
connected.
The adjacency matrix is given by
0 0 1 0 0 0
1 0 0 0 0 1
 
1 1 0 0 0 0
A
=0 1 0 0 0 0
 
0 0 1 0 0 0
 
0 0 0 1 1 0
 
 
and the diagonal in-degree matrix and Laplacian are

28 2  Algebraic Graph Theory and Cooperative Control Consensus
|     | 1 0 0 | 0 0 0 |     | 1 0 | −1 0 | 0 0 |     |
| --- | ------ | ------ | --- | --- | ---- | ---- | --- |

|     |        |         |     |        |         |     |     |
| --- | ------- | ------- | ----- | ------ | ------- | ---- | --- |
|     | 0 2 0   | 0 0 0   | −1    | 2      | 0 0 0   | −1   |     |
|     |        |         |     |        |         |     |     |
|     | 0 0 2  | 0 0 0  | −1   | −1     | 2 0     | 0 0 |     |
|     | D=     |         |  L= |        |         |     |     |
|     | 0 0 0   | 1 0 0   |       | 0 −1   | 0 1     | 0 0  |     |
|     |        |         |     |        |         |     |     |
|     | 0 0 0  | 0 1 0  |      | 0 0 −1 | 0       | 1 0 |     |
|     |        |         |     |        |         |     |     |
|     | 0 0 0 | 0 0 2 |       | 0 0    | 0 −1 −1 | 2  |     |

,,
Note that the row sums of L are all zero.
2.1.3   Eigenstructure of Graph Laplacian Matrix
We shall see that the eigenstructure of the graph Laplacian matrix L plays a key role
in the analysis of dynamical systems on graphs. Define the Jordan normal form [2]
of the graph Laplacian matrix by
L=MJM−1
|     |     |     |     |     |     |     | (2.4) |
| --- | --- | --- | --- | --- | --- | --- | ----- |
with the Jordan form matrix and transformation matrix given as
|     | λ  |     |    |     |     |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- |
1
|     |    |     |    |     |     |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- |
λ
|     | =  | 2        |    |            |                 |     |       |
| --- | --- | -------- | --- | ---------- | --------------- | --- | ----- |
|     | J   |          | ,M  | =v 1 v 2 | (cid:31) v N  |     | (2.5) |
|     |    | (cid:30) |    |            |                 |     |       |
|     |    |          |    |            |                 |     |       |
λ
|                                                  |    |         | N  |          |     |     |       |
| ------------------------------------------------ | --- | ------- | --- | -------- | --- | --- | ----- |
| where the eigenvalues λ and right eigenvectors v |     |         |     |  satisfy |     |     |       |
|                                                  | i   |         |     | i        |     |     |       |
|                                                  |     | (λI−L)v |     | =0       |     |     | (2.6) |
|                                                  |     |         | i i |          |     |     |       |
with I being the identity matrix.
In general, the λ in (2.5) are not scalars but are Jordan blocks of the form
i
|     |     | λ  | 1   |    |     |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- |
i
|     |     |    |            |    |     |     |     |
| --- | --- | --- | ---------- | --- | --- | --- | --- |
|     |     |     | λ (cid:30) |     |     |     |     |
|     |     |    | i          |    |     |     |     |
|     |     |    | (cid:30)   | 1  |     |     |     |
|     |     |    |            |    |     |     |     |
λ
|     |     |    |     | i  |     |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- |
The number of such Jordan blocks associated with the same eigenvalue λ is known
i
as the geometric multiplicity of eigenvalue λ. The sum of the sizes of all Jordan
i
blocks associated with λ is called its algebraic multiplicity. For ease of notation
i
and discussion, we assume here that the Jordan form is simple, that is, it is diagonal
with all Jordan blocks of size 1. This is guaranteed if all eigenvalues of L are dis-
tinct. A symmetric matrix may not have distinct eigenvalues but has a simple Jordan

2.1 Algebraic Graph Theory 29
form. All of our discussions generalize without difficulty to the case of nontrivial
Jordan blocks.
The inverse of the transformation matrix M is given as
wT
1
 
wT
M-1 = 2 (2.7)
 
(cid:29)
 
 wT
N


where the left eigenvectors w satisfy
i
wT(λI-L)=0 (2.8)
i i
and are normalized so that wTv =1.
i i
We assume the eigenvalues are ordered so that λ ≤ λ ≤(cid:31)≤ λ . Any un-
1 2 N
directed graph has L= LT so all its eigenvalues are real and one can order them as
λ ≤λ ≤(cid:31)≤λ .
1 2 N
Since L has all row sums zero, one has
L1c=0 (2.9)
with 1=[1(cid:31)1]T ∈RN being the vector of ones and c any constant. Therefore,
λ =0 is an eigenvalue with a right eigenvector of 1c. That is, 1c∈N(L) the
1
null-space of L. If the dimension of the null-space of L is equal to one, i.e., the rank
of L is N-1, then λ =0 is nonrepeated and 1c is the only vector in N(L). The next
1
standard result states when this occurs.
Theorem 2.1 L has rank N-1, i.e., λ =0 is nonrepeated, if and only if graph G
1
has a spanning tree [13, 16].
If the graph has a spanning tree, then λ >0. If the graph is strongly connected,
2
then it has a spanning tree and L has rank N-1.
The Laplacian has at least one eigenvalue at λ =0. The remaining eigenvalues
1
can be localized using the following result.
Geršgorin Circle Criterion All eigenvalues of a matrix E [e ] RN N are
ij ×
= ∈
located within the union of N disks [6].
N  
z∈C: z−e ≤∑ e 
ii ij
i=1
j≠i

The i-th disk in the Geršgorin circle criterion is drawn with a center at the diagonal
element e and with a radius equal to the i-th absolute row sum with the diagonal
ii
element deleted, ∑ e . Therefore, the Geršgorin disks for the graph Laplacian
ij
j≠i
matrix L= D−A are centered at the in-degrees d and have radius equal to d.
i i
Let d be the maximum in-degree of G. Then, the largest Geršgorin disk of the
Max

30 2 Algebraic Graph Theory and Cooperative Control Consensus
F ig. 2.3 Geršgorin disks of L
in the complex plane
Laplacian matrix L is given by a circle centered at d and having radius of d .
Max Max
This circle contains all the eigenvalues of L. See Fig. 2.3. The Geršgorin circle cri-
terion ties the eigenvalues of L rather closely to the graph structural properties in
terms of the in-degrees.
We have thus discovered that if the graph has a spanning tree, there is a nonre-
peated eigenvalue at λ =0 and all other eigenvalues have positive real parts, i.e.,
1
in the open right-half plane, and are within a circle centered at d and having
Max
radius of d .
Max
When comparing eigenvalues between two graphs, it is often more useful to use
the normalized Laplacian matrix
L = D−1L= D−1(D−A)= I−D−1A (2.10)
Since the normalized adjacency matrix A= D−1A has row sums equal to one,
d =1,∀i and L has all Geršgorin disks centered at s = 1 with radius of 1.
i
Example 2.2 Laplacian Matrix Eigenvalues for Various Graph Types
In this example, we will compute the eigenvalues of the graph Laplacian matrix
L= D−A for various types of graphs. The intent is to give a feeling for the depen-
dence of the Laplacian eigenvalues on the graph topology. This example is the work
of David Maxwell in the class EE 5329 Distributed Decision & Control, Spring
2011, Department of Electrical Engineering, The University of Texas at Arlington,
TX, USA. The class link is http://arri.uta.edu/acs
The graphs studied in this example include several commonly occurring topolo-
gies and are depicted in Fig. 2.4. The graph notation is standard and is explained in
[3, 5]. We include it for interest only and do not use this notation further in the book.
All edge weights are taken equal to 1. Note that a complete (or fully connected)
graph is one that has all possible edges between the nodes.
The eigenvalues of these graphs are listed in Table 2.1 and plotted in the complex
s-plane in Fig. 2.5. Several things are worthy of note:

2.1   Algebraic Graph Theory  31

Fig. 2.4  Different graph topologies for Example 2.2. a Directed graph. b Undirected graph. c
Complete graph K6. d Directed tree graph (formation graph). e Undirected star K . f Directed star.
1,5
g Undirected 6-cycle (2-regular graph). h Directed 6-cycle (6-periodic graph). i Undirected path P5
Table 2.1  Eigenvalues for different graph topologies in Example 2.2
| a.   | b.   | c.   d.   | e.   f.   | g.   | h.   i.   |
| ---- | ---- | --------- | --------- | ---- | --------- |
Directed graph Undirec- Com- Direc- Undi- Direc- Undi- Directed  Undirec-
ted graph plete  ted tree rected ted star rected  6-cycle ted path
|                  |        | graph | star | 6-cycle |                     |
| ---------------- | ------ | ----- | ---- | ------- | ------------------- |
| 0                | 0      | 0 0   | 0 0  | 0       | 0.0000 0            |
| 0.7793           | 1.3820 | 6 1   | 1 1  | 1       | 0.5 + 0.866i 0.2679 |
| 1.0000           | 1.6972 | 6 1   | 1 1  | 1       | 0.5 − 0.866i 1      |
| 2.2481 + 1.0340i | 3.6180 | 6 1   | 1 1  | 3       | 1.5 + 0.866i 2      |
| 2.2481 − 1.0340i | 4.0000 | 6 1   | 1 1  | 3       | 1.5 − 0.866i 3      |
| 2.7245           | 5.3028 | 6 1   | 6 1  | 4       | 2. 3.7321           |

32 2  Algebraic Graph Theory and Cooperative Control Consensus
|   1.5 |     |     | 1   |     |     |
| ----- | --- | --- | --- | --- | --- |
0.8
| 1   |     |     | 0.6 |     |     |
| --- | --- | --- | --- | --- | --- |
0.4
0.5
| sixa yranigami |     |     | sixa yranigami |     |     |
| -------------- | --- | --- | -------------- | --- | --- |
0.2
| 0   |     |     | 0   |     |     |
| --- | --- | --- | --- | --- | --- |
−0.2
−0.5
−0.4
−0.6
−1
−0.8
| −1.5 −0.5 0 0.5 | 1 1.5     | 2 2.5 3 | −1 0 1         | 2 3       | 4 5 6 |
| --------------- | --------- | ------- | -------------- | --------- | ----- |
| a               | real axis |         | b              | real axis |       |
| 1               |           |         | 1              |           |       |
| 0.8             |           |         | 0.8            |           |       |
| 0.6             |           |         | 0.6            |           |       |
| 0.4             |           |         | 0.4            |           |       |
| sixa yranigami  |           |         | sixa yranigami |           |       |
| 0.2             |           |         | 0.2            |           |       |
| 0               |           |         | 0              |           |       |
| −0.2            |           |         | −0.2           |           |       |
| −0.4            |           |         | −0.4           |           |       |
| −0.6            |           |         | −0.6           |           |       |
| −0.8            |           |         | −0.8           |           |       |
| −1 −1 0         | 1 2 3     | 4 5 6   | −1 0 0.2       | 0.4 0.6   | 0.8 1 |
| c               | real axis |         | d              | real axis |       |
| 1               |           |         | 1              |           |       |
| 0.8             |           |         | 0.8            |           |       |
| 0.6             |           |         | 0.6            |           |       |
| 0.4             |           |         | 0.4            |           |       |
| sixa yranigami  |           |         | sixa yranigami |           |       |
| 0.2             |           |         | 0.2            |           |       |
| 0               |           |         | 0              |           |       |
| −0.2            |           |         | −0.2           |           |       |
| −0.4            |           |         | −0.4           |           |       |
| −0.6            |           |         | −0.6           |           |       |
| −0.8            |           |         | −0.8           |           |       |
| −1 −1 0         | 1 2 3     | 4 5 6   | −1 0 0.2       | 0.4 0.6   | 0.8 1 |
| e               | real axis |         | f              | real axis |       |
Fig. 2.5  Complex plane plots of graph eigenvalues for Example 2.2. a Directed graph. b Undi-
rected graph. c Complete graph K6. d Directed tree (formation graph). e Undirected star K .
1,5
f Directed star. g Undirected 6-cycle (2-regular graph). h Directed 6-cycle (6-periodic graph).
i Undirected path P5
1. The Laplacian matrix has row sums equal to zero so that all graphs have the first
| eigenvalue at λ | =0. |     |     |     |     |
| --------------- | --- | --- | --- | --- | --- |
1
2. All undirected graphs have a symmetric Laplacian matrix L and so their graph
eigenvalues are real.

| 2.1   Algebraic Graph Theory  |           |         |                |           | 33    |
| ----------------------------- | --------- | ------- | -------------- | --------- | ----- |
| 1                             |           |         | 1              |           |       |
| 0.8                           |           |         | 0.8            |           |       |
| 0.6                           |           |         | 0.6            |           |       |
| 0.4                           |           |         | 0.4            |           |       |
| sixa yranigami                |           |         | sixa yranigami |           |       |
| 0.2                           |           |         | 0.2            |           |       |
| 0                             |           |         | 0              |           |       |
| −0.2                          |           |         | −0.2           |           |       |
| −0.4                          |           |         | −0.4           |           |       |
| −0.6                          |           |         | −0.6           |           |       |
| −0.8                          |           |         | −0.8           |           |       |
| −1                            |           |         | −1             |           |       |
| g 0                           | 0.5 1 1.5 | 2 2.5 3 | 3.5 4 h 0      | 0.5 1     | 1.5 2 |
|                               | real axis |         |                | real axis |       |
1
0.8
0.6
0.4
sixa yranigami
0.2
0
−0.2
−0.4
−0.6
−0.8
−1
|     |     | 0 0.5 | 1 1.5 2   | 2.5 3 3.5 4 |     |
| --- | --- | ----- | --------- | ----------- | --- |
|     |     | i     | real axis |             |     |
Fig. 2.5  (continued)
3. Complete (or fully connected) graphs with N nodes have all the nonzero eigen-
values at s = N.
4. Directed trees have all the nonzero eigenvalues at s = 1.
5. A directed star is a directed tree, so it has all the nonzero eigenvalues at s = 1.
6. Directed cycle graphs of length N have N eigenvalues uniformly spaced around a
circle in the s-plane centered at s = 1 with radius of s = 1, with the first eigenvalue
at λ =0.
1
2.1.4   The Fiedler Eigenvalue
We shall see in Theorem 2.2 that the second eigenvalue λ of the graph Laplacian
2
matrix L is important in determining the speed of interaction of dynamic systems
on graphs. Graph topologies that have a large value of λ are better for achieving
2
convergence. The second eigenvalue of L is known as the Fiedler eigenvalue and it
has important and subtle connections to the topology of the graph. It is also known
as the graph algebraic connectivity. Fiedler eigenvalues for some different graph
topologies are given in Example 2.2.

34 2 Algebraic Graph Theory and Cooperative Control Consensus
For undirected graphs, there are many useful bounds on the Fiedler eigenvalue,
including [23]
N
λ ≤ d (2.11)
2 N−1 min
where d is the minimum in-degree, and for connected undirected graphs
min
1
λ ≥ .
2 DiamG×VolG (2.12)
The distance between two nodes in an undirected graph is the length of the shortest
path connecting them, and if they are not connected the distance between them is
infinity. The diameter of a graph Diam G is the greatest distance between any two
nodes in G and the volume VolG is given by (2.3). Bounds on the Fiedler eigen-
value for directed graphs are more complicated [23].
Interactive systems on graph converge to steady-state values faster when λ is
2
larger, as we shall see. Given that, according to (2.12) convergence is faster in
graphs that are more fully connected, that is, have shorter distances between any
pair of nodes, and for graphs whose nodes have fewer neighbors. Among the fastest
graph topologies are the fully connected complete graph and the star graph [23],
where one root node is connected to all other nodes. The star is a tree graph with
depth equal to one.
2.2 Systems on Communication Graphs and Consensus
A network may be considered as a set of nodes or agents that collaborate to achieve
what each cannot achieve alone. To capture the notion of dynamical agents, endow
each node i of a graph with a time-varying state vector x(t). A graph with node dy-
i
namics [10] is (G,x) with G being a graph having N nodes and x [xT xT] T a
= 1 ··· N
global state vector, where the state of each node evolves according to some dynamics
x = f (x,u ) (2.13)
i i i i
with u being a control input and f (.) some flow function. Given a graph
i i
G=(V,E), we interpret (v,v )∈E to mean that node v can obtain information
i j j
from node v for feedback control purposes [7, 9, 10].
i
Definition 2.1 Distributed Control Protocols The control given by
u =k (x ,x ,,x ) for some function k (.) is said to be distributed if m < N,∀i,
i i i1 i2 imi i i
that is, the control input of each node depends on some proper subset of all the
nodes. It is said to be a protocol with topology G if u =k (x,{x | j∈N}), that is,
i i i j i
each node can obtain information about the state only of itself and its (in)-neigh-
bors in N.
i

2.3 Consensus with Single-Integrator Dynamics 35
Cooperative control, or control of distributed dynamical systems on graphs, refers
to the situation where each node can obtain information for controls design only
from itself and its neighbors. The graph might represent a communication network
topology that restricts the allowed communications between the nodes. This has
also been referred to as multi-agent control, but is not the same as the notion of
multi-agent systems used by the Computer Science community [20].
Of fundamental concern for systems on graphs is the study of their collective
behaviors under the influence of the information flow allowed in the graph. A basic
control design objective is the following.
Definition 2.2 Consensus Problem Find a distributed control protocol that drives
all states to the same values x = x ,∀i, j. This value is known as a consensus
i j
value.
2.3 Consensus with Single-Integrator Dynamics
We start our study of dynamical systems on graphs, or cooperative control, by
considering the case where all nodes of the graph G have scalar single-integrator
dynamics
x =u (2.14)
i i
with x,u ∈R. This corresponds to endowing each node or agent with a memory.
i i
2.3.1 Distributed Control Protocols for Consensus
Consider the local control protocols for each agent i
u = ∑a (x −x) (2.15)
i ij j i
j∈Ni
with a being the graph edge weights. This control is distributed in that it only
ij
depends on the immediate neighbors N of node i in the graph topology. This is
i
known as a local voting protocol since the control input of each node depends on
the difference between its state and all its neighbors. Note that if these states are all
the same, then x =u =0. In fact, it will be seen that, under certain conditions, this
i i
protocol drives all states to the same value.
We wish to show that protocol (2.15) solves the consensus problem and to deter-
mine the consensus value reached. Write the closed-loop dynamics as
x = ∑a (x −x) (2.16)
i ij j i
j∈Ni

36 2  Algebraic Graph Theory and Cooperative Control Consensus

x 
1
|     | ∑a            | ∑a    |       |        |     |                      |        |
| --- | ------------- | ----- | ----- | ------ | --- | ---------------------- | ------ |
|     | x(cid:28) =-x | +     | x =-d | x +a |     | (cid:31) a  (cid:29) | (2.17) |
|     | i i           | ij    | ij j  | i i    | i1  | iN                   |        |
|     | j∈N           | i j∈N | i     |        |     |  x                 |        |
N
with d  being the in-degree. Define the global state vector x [x x ]T RN
|     | i   |     |     |     |     | = 1··· | N ∈ |
| --- | --- | --- | --- | --- | --- | ------ | --- |
and the diagonal matrix of in-degrees D=diag{d}. Then the global dynamics are
i
given by
|     |     |     | x =−Dx+Ax=−(D−A)x |         |     |     | (2.18) |
| --- | --- | --- | ------------------ | ------- | --- | --- | ------ |
|     |     |     |                    | x =−Lx |     |     | (2.19) |
]T ∈RN is given by
| Note that the global control input vector u=[u |     |     |     |     | u  |     |     |
| ---------------------------------------------- | --- | --- | --- | --- | --- | --- | --- |
|                                                |     |     |     |     | 1   | N   |     |
(2.20)
|     |     |     |     | u=−Lx |     |     |     |
| --- | --- | --- | --- | ----- | --- | --- | --- |
It is seen that using the local voting protocol (2.15), the closed-loop dynamics (2.19)
depends on the graph Laplacian matrix L. We shall now see how the evolution of
first-order integrator dynamical systems on graphs depends on the graph properties
through the Laplacian matrix. The eigenvalues of L are instrumental in this analysis.
The dynamics given by (2.19) has a system matrix of -L, and hence has eigen-
values in the left-half plane, specifically inside the circle in Fig. 2.3 reflected into
the left-half plane. At steady state, according to (2.19) one has
|     |     |     | 0=−Lx |     |     |     | (2.21) |
| --- | --- | --- | ----- | --- | --- | --- | ------ |
|     |     |     |       |     | ss  |     |        |
Therefore, the steady-state global state is in the null-space of L. According to (2.9)
one vector in N(L) is 1c for any constant c. If L has rank of N-1, then 1c is the only
vector in the null-spac−e of L and one has x 1c for some constan−t c. Then one
ss
=
| has at steady state |     |     |     |     | −   |     |     |
| ------------------- | --- | --- | --- | --- | --- | --- | --- |
|                     |     |     | x  |    | c |     |     |
1
|     |     |     |     |              |        |     |        |
| --- | --- | --- | ---- | ------------- | -------- | --- | ------ |
|     |     |     | x=   | (cid:29) =c1= | (cid:29) |     | (2.22) |
|     |     |     |     |              |        |     |        |
|     |     |     |  x |              |  c    |     |        |
|     |     |     |      | N            |         |     |        |
and x = x =c=const,∀i, j. Then, consensus is reached. The next result formal-
|     | i j |     |     |     |     |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- |
izes this discussion and delivers the consensus value c.
Theorem 2.2 Consensus for First-order Systems The local voting protocol (2.15)
guarantees consensus of the single-integrator dynamics (2.14) if and only if the
graph has a spanning tree. Then, all node states come to the same steady-state val-
| ues x | = x =c,∀i, | j. The consensus value is given by |     |     |     |     |     |
| ----- | ---------- | ---------------------------------- | --- | --- | --- | --- | --- |
|       | i j        |                                    |     |     |     |     |     |
N
c=∑px(0)
|     |     |     |     |     |     |     | (2.23) |
| --- | --- | --- | --- | --- | --- | --- | ------ |
i i
i=1

| 2.3   Consensus with Single-Integrator Dynamics  |     |     |     | 37  |
| ------------------------------------------------ | --- | --- | --- | --- |
T
where w =p (cid:31)p   is the normalized left eigenvector of the Laplacian L for
| 1   | 1 N |     |     |     |
| --- | --- | --- | --- | --- |
λ =0. Finally, consensus is reached with a time constant given by
1
|     |     | τ=1/λ |     | (2.24) |
| --- | --- | ----- | --- | ------ |
2
with λ being the second eigenvalue of L, that is, the Fiedler eigenvalue.
2
Proof The proof is given for case that L is simple, i.e., has all Jordan blocks of order
one. The general case follows similarly. Using modal decomposition [2] write the
solution of (2.19) in terms of the Jordan form of L as
|                                   |     | N          | N      |               |
| --------------------------------- | --- | ---------- | ------ | ------------- |
|                                   |     | twTx(0)=∑( |        | )             |
|  x(t)=e-Ltx(0)=Me-JtM-1x(0)=∑ve-λ |     |            | wTx(0) | e-λ tv (2.25) |
|                                   |     | i i i      | i      | i i           |
|                                   |     | i=1        | i=1    |               |
Here, the left and right eigenvectors are normalized so that wTv =1. If the graph
i i
has a spanning tree, then Theorem 2.1 shows that λ =0 is simple and the Geršgorin
1
circle criterion shows that all other eigenvalues of L are in the open right half of the
complex plane. Then system (2.19) is marginally stable with one pole at the origin
and the rest in the open left-half plane. Therefore, in the limit as t→∞ one has
|     | x(t)→v | e-λ 2 twTx(0)+ve-λ | 1 twTx(0) | (2.26) |
| --- | ------ | ------------------ | --------- | ------ |
|     |        | 2 2                | 1 1       |        |
with Fiedler eigenvalue λ  being the smallest magnitude nonzero eigenvalue. One
2
|                        | =1. Define the left eigenvector w |     | =p (cid:31)p | T              |
| ---------------------- | --------------------------------- | --- | -------------- | -------------- |
| has λ 1 =0, and take v |                                   |     | 1 1            | N  , normal- |
1
| ized so that wTv | =1, that is, ∑p | =1. Then |     |     |
| ---------------- | --------------- | -------- | --- | --- |
i
i i
i
N
|     | x(t)→v | e-λ 2 twTx(0)+1∑p | x (0) | (2.27) |
| --- | ------ | ----------------- | ----- | ------ |
|     |        | 2 2               | i i   |        |
i=1
The last term in this equation is the steady-state value  x c1, with c given in
ss
(2.23). The first term on the right verifies that the consensus value− is reached with a  =
time constant given by τ=1/λ.  □
2
If the graph is strongly connected, then it has a spanning tree and consensus is
reached.
If the graph does not have a spanning tree, then the dimension of null-space of L
is greater than 1 and there is a ramp term in (2.25) that increases with time. Then,
consensus is not reached.
If the graph has a spanning tree, there is a simple pole at zero and the system is
of Type I. Then, it reaches a steady-state value. Otherwise, the system is of Type 2
or higher and a constant steady-state value is not reached. This is in line with the
previous paragraph. Thus, we have the curious situation that the system dynamical
behavior, notably the system type, depends on the graph topology, that is, the man-
ner in which the nodes communicate.

38 2 Algebraic Graph Theory and Cooperative Control Consensus
Theorem 2.2 shows that the consensus value is in the convex hull of the initial
node states and is the normalized linear combination of the initial states weighted
by the elements p of the left eigenvector w for λ =0.
i 1 1
Due to their importance in the analysis of dynamics and consensus on graphs, we
call 1 the first right eigenvector of L and w its first left eigenvector.
1
It is seen from (2.24) that the speed of convergence to consensus depends on the
Fiedler eigenvalue λ. Convergence is faster for graphs with larger λ. The Fiedler
2 2
eigenvalue was displayed for various graph topologies in Example 2.2.
This development has made clear the importance for networked dynamical sys-
tems of the communication graph topology as given in terms of the eigenstructure
of the Laplacian matrix L, including its first eigenvalue λ =0, its right eigenvector
1
v 1 and left eigenvector w, and the second (Fiedler) eigenvalue λ. In some
1 = 1 2
cases,− especially in undirected graphs, these quantities can be more closely tied to
topological properties of the graph.
Example 2.3 Single-Integrator Consensus for Different Graph Topologies
In this example, we plot the system states in consensus dynamics (2.19) for the
graph topologies in Example 2.2 that is in Fig. 2.4. This example is the work of
Ernest Strinden in the class EE 5329 Distributed Decision & Control, Spring 2011,
Department of Electrical Engineering, The University of Texas at Arlington, TX,
USA. The class link is http://arri.uta.edu/acs
Note first that the Fiedler eigenvalues λ are shown in Table 2.1. According to
2
Theorem 2.2, these give a first-order estimate of the time to reach consensus, since
from (2.24), consensus is reached faster for graph topologies having larger λ.
2
The consensus plots in Fig. 2.6 show the states x in the consensus dynamics
i
x =−Lx of (2.19) for the graph topologies in Example 2.2. Several things are wor-
thy of note:
1. Speed of convergence is generally faster for larger Fiedler eigenvalues in
Table 2.1.
2. Undirected graphs have real eigenvalues, so there is no oscillation on the way to
consensus.
3. Complete graph has fastest consensus since information flows immediately
between any pair of nodes.
4. Undirected graph b. has faster consensus than directed graph a., since more
information passes between the nodes.
5. Directed 6-cycle graph has slow convergence and oscillations since it has com-
plex eigenvalues uniformly spaced around a circle in the s-plane.
6. Undirected path has very slow convergence since it has a large diameter.
E xample 2.4 Consensus of Headings in Swarm Motion Control
The local voting protocol (2.15) can be used in many applications to yield consen-
sus. An example is the consensus of headings in a formation or in animal groups.

2.3 Consensus with Single-Integrator Dynamics 39
t (seconds) t (seconds)
t (seconds) t (seconds)
t (seconds) t (seconds)
Fig. 2.6 Consensus plots for different graph topologies for Example 2.3. a Directed graph.
b Undirected graph. c Complete graph K6. d Directed tree graph (formation graph). e Undirected
star K . f Directed star
1,5
setatS
setatS
setatS
setatS
setatS
setatS

40 2 Algebraic Graph Theory and Cooperative Control Consensus
setatS
setatS
setatS
t (seconds) t (seconds)
t (seconds)
Fig. 2.6 (continued)
Fig. 2.7 Motion of nodes in
( x, y)-plane

| 2.3   Consensus with Single-Integrator Dynamics  |     |     | 41     |
| ------------------------------------------------ | --- | --- | ------ |
| F ig. 2.8  Tree graph for                        |     |     | Leader |
motion control
Followers
Simple motions of a group of N agents in the (x,y)-plane as shown in Fig. 2.7 can
be described by the node dynamics

x(cid:28) =Vcosθ
|     | i                | i   |        |
| --- | ---------------- | --- | ------ |
|     | y(cid:28) =Vsinθ |     | (2.28) |
|     | i                | i   |        |
where V is the speed of the agents, assumed here to be the same, and θ
i  is the head-
ing of agent i.
According to the observed behavior of animal social groups such as flocks, fish
schools, etc., agents moving in groups tend to align their headings to a common value.
This is formalized in Reynolds three rules of animal behavior in groups [19]. There-
fore, use the local voting protocol (2.15) to reach heading consensus according to
|     | θ(cid:28) = ∑ a | (θ -θ) | (2.29) |
| --- | --------------- | ------ | ------ |
|     | i ij            | j i    |        |
j∈N
i
Consider the tree graph shown in Fig. 2.8 with six agents. A simulation is run of the
dynamics (2.29), (2.28). Figure 2.9 shows the headings of the agents, starting from
random values. All headings reach the same consensus value. Figure 2.10 shows
the motion of the agents in the (x,y)-plane with different randomly selected initial
positions. All agents converge to the same heading and move off in a formation
together. Note that all nodes converge to the heading of the leader.
In this example, if the node speeds are not all the same, one could run two con-
sensus algorithms at each node, one for the headings θ  and one for the speeds V
|     |         | i      | i      |
| --- | ------- | ------ | ------ |
|     | V = ∑a | (V −V) |        |
|     |         |        | (2.30) |
|     | i ij    | j i    |        |
j∈Ni
2.3.2   Consensus Value for Balanced Graphs—Average
Consensus
The consensus value (2.23) is the weighted average of the initial conditions of the
states of the nodes. It depends on the graph topology through the left eigenvector
=[p ]T
w 1 1 (cid:31)p N  of the zero eigenvalue of Laplacian matrix L. It is not always de-

42 2 Algebraic Graph Theory and Cooperative Control Consensus
60
40
20
0
-20
-40
-60
-80
-100
-120
0 5 10 15 20 25 30
Time
gnidaeH
Fig. 2.9 Consensus of headings
200
150
100
50
0
-50
-100
-150
-200
10 20 30 40 50 60 70 80 90 100
x x
y
F ig. 2.10 Motion consensus
in (x,y)-plane
Leader
y
sirable for the consensus value to depend on the graph topology, i.e., on the manner
in which the nodes communicate. An important problem in cooperative control is
therefore the following [7, 10].
Average Consensus Problem Find a control protocol that drives all states to the
same constant steady-state values x = x =c,∀i, j, where c is the average of the
i j
initial states of the nodes

2.3 Consensus with Single-Integrator Dynamics 43
1
c= ∑x(0) (2.31)
N i
i
This value does not depend on the graph structure. The average consensus problem
is important in many applications. For instance, in wireless sensor networks, each
node measures some quantity (e.g., temperature, salinity content, etc.) and it is de-
sired to determine the best estimate of the measured quantity, which is the average
if all sensors have identical noise characteristics.
A graph is said to be weight balanced if the weighted in-degree equals the
weighted out-degree for all nodes v∈V. We shall omit the qualifier ‘weight’ for
simplicity. The row sums of the Laplacian L are all zero. For balanced graphs, the
i-th row sum and i-th column sum of adjacency matrix A, and hence L, are equal.
Then, the column sums of the Laplacian matrix are also all equal to zero and
wTL=c1TL=0 (2.32)
1
so that a left eigenvector for λ =0 is w c1. This is normalized by dividing each
1 1 =
element by N. Then the consensus value (2.2−3) is (2.31) and average consensus is
reached.
Note that if a graph is undirected, it is balanced such that average consensus is
reached.
2.3.3 Consensus Leaders
A (directed) tree is a connected digraph where every node except one, called the
root or leader, has in-degree equal to one. It was seen in Example 2.4 that all nodes
reached a consensus heading equal to the initial heading of the leader. The con-
sensus value is given by (2.23) with p the i-th component of the left eigenvector
i
w for the zero eigenvalue. If the graph is strongly connected, one has p >0,∀i
1 i
since each node influences all other nodes along directed paths. If the graph has a
spanning tree but is not strongly connected, then some nodes do not have paths to all
other nodes. Thus, all other nodes cannot be aware of the initial states of such nodes.
Suppose a graph contains a spanning tree. Then it may contain more than one.
Define the root set or leader set of a graph as the set of nodes that are the roots of
all spanning trees.
Theorem 2.3 Consensus Leaders [23] Suppose a graph G=(V,E) contains
a spanning tree and define the leader set W ⊂V. Define the left eigenvector of
T
Laplacian matrix L for λ
1
=0 as w
1
=p
1
(cid:31)p
N
 . Then p
i
>0,i∈W and
p =0,i∉W.
i

44 2  Algebraic Graph Theory and Cooperative Control Consensus
This result shows that the consensus value (2.23) is actually the weighted average
of the initial conditions of the root or leader nodes in a graph, that is, of the nodes
that have a path to all other nodes in the graph. In Example 2.4, the graph is a
tree. Therefore, all nodes reach a consensus heading equal to the initial heading of
the leader node. In a strongly connected graph, all nodes are leader nodes so that
>0,∀i.
p
i
2.3.4   Non-Scalar Node States
It was assumed that the node states and controls in the dynamics (2.14) are scalars
x,u ∈R. If the states and controls are vectors so that x,u ∈Rn, then the global
i i i i
state and control are x=[xTxT]T ∈RnN, u=[uTuT]T ∈RnN and the elements
|     | 1   | N   | 1 N |     |
| --- | --- | --- | --- | --- |
a  and d  in (2.17) are multiplied by the n×n identity matrix I . Then, the global
ij i n
dynamics are written as
|     |     | u=−(L⊗I | )x  | (2.33) |
| --- | --- | ------- | --- | ------ |
n
|     |     | x =−(L⊗I | )x  | (2.34) |
| --- | --- | --------- | --- | ------ |
n
with ⊗ being the Kronecker product [1]. All of our developments still hold if the
Kronecker product is added where appropriate.
Given  two  matrices  A [a ],B  the  Kronecker  product  is  defined  as
= ij
| A B | [a B], the matrix with block elements a |     | B.  |     |
| --- | --------------------------------------- | --- | --- | --- |
|     | ij                                      |     | ij  |     |
⊗ =
 Simulation of Cooperative Systems with Vector States
If the states in (2.14) are vectors so that  x,u ∈Rn, then x=[xTxT]T ∈RnN,
|     |     |     | i i 1 | N   |
| --- | --- | --- | ----- | --- |
u=[uTuT]T ∈RnN and the global dynamics are written as (2.34). This can cause
| 1   | N   |     |     |     |
| --- | --- | --- | --- | --- |
numerical integration problems in simulations since the dimension nN of the global
state becomes large quickly as the node state dimension n and the number of nodes
N increase. The matrix (L⊗I )∈RnN ×RnN is a large sparse matrix with many zero
n
entries. For simulation purposes, it is better to define the N×n matrix of states
xT
1
xT
|     |     | X  | 2  | (2.35) |
| --- | --- | --- | --- | ------ |
=
xT
|     |     |    | N  |     |
| --- | --- | --- | --- | --- |
|     |     |    |    |     |
Then
X
|     |     | =−LX |     | (2.36) |
| --- | --- | ---- | --- | ------ |

| 2.4   Motion Invariants for First-Order Consensus  |     |     |     | 45  |
| -------------------------------------------------- | --- | --- | --- | --- |
which does not involve the Kronecker product and has better numerical properties
for simulation.
2.4   Motion Invariants for First-Order Consensus
The first-order local protocol (2.15) has a number of important properties. We have
seen that it guarantees consensus if the graph has a spanning tree. Here we show
that it induces a decomposition based on motion invariants that depend on the graph
topology [8].
2.4.1   Graph Motion Invariant and ‘Internal Forces’
T
Let w =p (cid:31) p   be a (not necessarily normalized) left eigenvector of L for
| 1 1 N |     |     |     |     |
| ----- | --- | --- | --- | --- |
λ =0. Then according to (2.19)
1
d
|     | (wTx)=wTx | =−wTLx=0 |     |        |
| --- | ---------- | -------- | --- | ------ |
|     |            |          |     | (2.37) |
|     | dt 1       | 1 1      |     |        |
so that the quantity
|     |     | x  |     |     |
| --- | --- | ---- | --- | --- |
1
|     | ≡wTx=[p | ]  =∑p           |     |        |
| --- | ------- | ------------------ | --- | ------ |
|     | x       | (cid:31)p (cid:30) | x   | (2.38) |
|     | 1       | 1 N              | i i |        |
|     |         |  x N           | i   |        |
is invariant. That is, regardless of the values of the node states x(t), the quantity
i
=∑px(t) is a constant of the motion. This means that the global velocity vec-
x
i i
i
| tor x(t)∈RN is always orthogonal to the vector w |     | ∈RN. |     |     |
| ------------------------------------------------- | --- | ---- | --- | --- |
1
Accordingly, ∑px(0)=∑px(t),∀t. Therefore, if the graph has a spanning
|     | i i | i i |     |     |
| --- | --- | --- | --- | --- |
i i
tree, at steady state one has consensus so that x = x =c,∀i, j, where the consen-
i j
sus value is given by
∑px(0)
i i
|     |     | c= i |     | (2.39) |
| --- | --- | ---- | --- | ------ |
∑p
i
i
This provides another proof for (2.23) (note that in (2.23), the left eigenvector is
normalized).

46 2  Algebraic Graph Theory and Cooperative Control Consensus
According to (2.20), the global control input is u=−Lx so that
|     | wTu=∑pu |     | =−wTLx=0 |     | (2.40) |
| --- | ------- | --- | -------- | --- | ------ |
|     |         | 1   | i i      | 1   |        |
i
with u (t) being the node control inputs. This states that the linear combination of
i
control inputs weighted by the elements of the left eigenvector for λ =0 is equal
1
to zero. This can be interpreted as a statement that the internal forces in the graph
do not work.
2.4.2   Center of Gravity Dynamics and Shape Dynamics
The quantity x  in (2.38) is a weighted centroid, or center of gravity, of the group of
agents, which remains stationary under the local voting protocol. Define the state-
space coordinate transformation [8] z=Mx with
|     |     | p   | p p | p   |     |
| --- | --- | --- | --- | --- | --- |
|     |     | 1   | 2 3 | N   |     |
···
|     |     | 1   | 1   |       |        |
| --- | --- | --- | --- | ----- | ------ |
|     |     |  − |     |      |        |
|     |     |     | 1 1 |       |        |
|     | M   |     |     |       | (2.41) |
|     | =  |     | −   |       |        |
|     |     |     |     | ...  |        |
|     |     |    |     |      |        |
|     |     |    |     |      |        |
|     |     |     |     | 1 1  |        |

|     |     |    |     | −  |     |
| --- | --- | --- | --- | --- | --- |
|     |     |    |     |    |     |
T
with w =p (cid:31) p   being the normalized first left eigenvector of L, that is,
| 1 1 N              |     |     |     |     |     |
| ------------------ | --- | --- | --- | --- | --- |
| wTL=0, ∑p =1. Then |     |     |     |     |     |
1 i
i
|     |     |    | x         |            |        |
| --- | --- | --- | ---------- | ---------- | ------ |
|     |     |    |           |            |        |
|     |     | x   | -x         | x        |        |
|     |     | z= | 1 2 ≡    |            |        |
|     |     |     |            |           | (2.42) |
|     |     |    | (cid:29)  | x(cid:27) |        |

|     |     |    |    |     |     |
| --- | --- | --- | --- | --- | --- |
|     |     | x  | -x  |     |     |
N-1 N
with x(t)∈RN−1 being an error vector that shows how far the node states are from
consensus. It can be seen that
|     |         | 1 P 2             | P 3      | (cid:31) P N  |        |
| --- | ------- | ------------------ | -------- | --------------- | ------ |
|     |         |                   |          |                |        |
|     |         |  1 P 2 −1         | P 3      | P N            |        |
|     | M−1 =1 |                    |          |                |        |
|     |         | P 2 −1             | P 3 −1   | (cid:30)        | (2.43) |
|     |         |                   |          |                |        |
|     |         | (cid:30) (cid:30) | (cid:30) | (cid:29) P N   |        |
|     |         | 1                 |          |                |        |
|     |         |  P −1             | P 3 −1   | P N −1         |        |
2
=∑N
| where P p. |     |     |     |     |     |
| ---------- | --- | --- | --- | --- | --- |
| k i=k i    |     |     |     |     |     |
Now, one has
|     |     | z=−MLM−1z |     |     | (2.44) |
| --- | --- | ---------- | --- | --- | ------ |

| 2.5   Consensus with First-Order Discrete-Time Dynamics  |     |     |     | 47  |
| -------------------------------------------------------- | --- | --- | --- | --- |
where
0 0
MLM-1
|     |     | =  |    | (2.45) |
| --- | --- | --- | --- | ------ |
0 L
(Note that the first row of M is the first left eigenvector of L and the first column of
M-1 the first right eigenvector of L.) Therefore,
x(cid:31) =0

|     |     | (cid:30)x(cid:31) =−Lx(cid:30) |     | (2.46) |
| --- | --- | ------------------------------ | --- | ------ |
Since a state-space transformation does not change the eigenvalues, the eigenvalues
of L  are the eigenvalues λ,(cid:31),λ  of L. If the graph has a spanning tree, there-
|     | 2   | N   |     |     |
| --- | --- | --- | --- | --- |
fore, -L  has all eigenvalues in the left-half plane and so is asymptotically stable
(AS). This means that the weighted centroid remains stationary, while, if there is
a spanning tree, the error vector x(t) converges to zero. Vector x(t) is called the
shape vector and it indicates the spread of the node error vectors about the centroid.
2.5   Consensus with First-Order Discrete-Time Dynamics
Now suppose each node or agent has scalar discrete-time (DT) dynamics given by
|     | x(k+1)= | x(k)+u | (k) | (2.47) |
| --- | ------- | ------ | --- | ------ |
|     | i       | i      | i   |        |
∈R. This corresponds to endowing each node with a memory in the form
with x,u
i i
of a shift register of order one. We discuss two ways to select the distributed control
| input protocols u | (k) [7, 10, 11, 16]. |     |     |     |
| ----------------- | -------------------- | --- | --- | --- |
i
2.5.1   Perron Discrete-Time Systems
Consider the distributed local control protocols

|     | u (k) ε | a (x | (k) x (k)) |        |
| --- | ------- | ---- | ---------- | ------ |
|     | i       | ij j | i          | (2.48) |
|     | =       |      | −          |        |
j Ni
(cid:31)∈
 being the graph edge weights and ε>0. The closed-loop system becomes
with a
ij
(k)+ε∑
|     | x (k+1)= x | a   | (x (k)−x (k)) |     |
| --- | ---------- | --- | ------------- | --- |
|     | i i        |     | ij j i        |     |
j∈Ni
|     |        | (k)+ε∑ |          |        |
| --- | ------ | ------ | -------- | ------ |
|     | =(1−εd | )x     | a x (k)) | (2.49) |
|     |        | i i    | ij j     |        |
j∈Ni

48 2  Algebraic Graph Theory and Cooperative Control Consensus
The corresponding global input is
|     |     |     |     |     | u(k) | εLx(k) |     |        |
| --- | --- | --- | --- | --- | ---- | ------ | --- | ------ |
|     |     |     |     |     |      |        |     | (2.50) |
=−
and the global dynamics is

|        |                |        | x(k                                                        | 1)  | (I εL)x(k) | Px(k)  |     | (2.51) |
| ------ | -------------- | ------ | ---------------------------------------------------------- | --- | ---------- | ------ | --- | ------ |
|        |                |        |                                                            | +   | = −        | ≡      |     |        |
| with u | [u             | u      | ]T RN, x                                                   |     | [x x       | ]T RN. |     |        |
|        |                | 1··· N |                                                            |     | 1···       | N      |     |        |
|        | The matrix P = |        | I ∈ εL is known as the Perron matrix. Laplacian L has one  | =   |            | ∈      |     |        |
= −
eigenvalue at s = 0 and the remaining eigenvalues in the right half of the s-plane, as
seen in Fig. 2.3. Therefore, −L has all eigenvalues in the open left-half plane, and
P has all eigenvalues in the shaded region of the z-plane shown in Fig. 2.11. If ε is
small enough, P has all eigenvalues inside the unit circle. Then, if the graph has a
spanning tree, it has a simple eigenvalue λ =1 at z=1, and the rest strictly inside
1
the unit circle. Then, (2.51) is marginally stable and of Type 1, and a steady-state
value is reached. A sufficient condition for P to have all eigenvalues in the unit
circle is
|     |     |     |     |     | ε<1/d | Max |     | (2.52) |
| --- | --- | --- | --- | --- | ----- | --- | --- | ------ |
Note that the conditions for stability of each agent’s dynamics (2.49) are ε<1/d
i.
Since Laplacian matrix L has row sums of zero, P has row sums of 1, and so is a
row stochastic matrix. That is,
|     |     |     |     |     | P1=1     |     |     | (2.53) |
| --- | --- | --- | --- | --- | -------- | --- | --- | ------ |
|     |     |     |     |     | (I−P)1=0 |     |     | (2.54) |
and 1 is the right eigenvector of λ =1. Let w  be a left eigenvector of L for λ =0.
|     |     |     |     |     | 1   | 1   |     | 1   |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
Then wTP wT(I εL) wT so that w  is a left eigenvector of P for λ =1.
|     | 1   | 1   |     | 1   |     |     |     | 1   |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
|     | =   |     | −   | =   |     | 1   |     |     |
If the system (2.51) reaches steady state, then

|     |     |     |     |     | x = | Px  |     | (2.55) |
| --- | --- | --- | --- | --- | --- | --- | --- | ------ |
|     |     |     |     |     | ss  | ss  |     |        |
If the graph has a spanning tree, then the only solution of this is x c1 for some
ss
|                                             |     |     |     |     |     |            | =   | −   |
| ------------------------------------------- | --- | --- | --- | --- | --- | ---------- | --- | --- |
| c>0. Then, consensus is reached such that x |     |     |     |     |     | = x =c,∀i, | j.  |     |
|                                             |     |     |     |     |     | i j        |     |     |
T
Let w =p (cid:31)p   be a left eigenvector of P for λ =1, not necessarily nor-
|     | 1   | 1   | N   |     |     |     | 1   |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
malized. Then
|     |     |     | wTx(k+1)=wTPx(k)=wTx(k) |     |     |     |     | (2.56) |
| --- | --- | --- | ----------------------- | --- | --- | --- | --- | ------ |
|     |     |     |                         | 1   | 1   | 1   |     |        |

| 2.5   Consensus with First-Order Discrete-Time Dynamics  |     |     |     | 49  |
| -------------------------------------------------------- | --- | --- | --- | --- |
F ig. 2.11  Region of eigenva-
lues of Perron matrix P
so that the quantity
|     |     | x  |     |     |
| --- | --- | ---- | --- | --- |
1
|     | Tx=p |   =∑p                |     |        |
| --- | ------ | ---------------------- | --- | ------ |
|     | x ≡w   | (cid:31) p  (cid:29) | x   | (2.57) |
|     | 1      | 1 N                  | i i |        |
|     |        |                      |     |        |
|     |        | x                    | i   |        |
N
is invariant. That is, the quantity x =∑px(k) is a constant of the motion. Thus,
i i
i
∑px(0)=∑px(k),∀k. Therefore, if the graph has a spanning tree, at steady
| i i | i i |     |     |     |
| --- | --- | --- | --- | --- |
| i i |     |     |     |     |
state one has consensus so that x = x =c,∀i, j, where the consensus value is giv-
i j
en by (2.39), the normalized linear combination of the initial states weighted by the
elements of the left eigenvector of P for λ =1. This depends on the graph topology
1
and hence on how the nodes communicate.
If the graph is balanced, then row sums of L are equal to column sums, and this
property carries over to P. Then w c1 is a left eigenvector of P for λ =1 and the
|                                                                                         |     | 1   | 1   |     |
| --------------------------------------------------------------------------------------- | --- | --- | --- | --- |
| consensus value is the average of the ini−tial conditions (2.31), which is independent  |     | =   |     |     |
of the graph topology.
2.5.2   Normalized Protocol Discrete-Time Systems
Now consider the local control protocols
1
|     | u (k)= | ∑a (x (k)−x(k)) |     | (2.58) |
| --- | ------ | --------------- | --- | ------ |
|     | i 1+d  | ij j            | i   |        |
i j∈Ni
which are normalized by dividing by 1+d , with d  being the in-degree of node i.
|     |     | i i |     |     |
| --- | --- | --- | --- | --- |
Thus, nodes with larger in-degrees must use less relative control effort than in the
protocol (2.48). The closed-loop system becomes

50 2  Algebraic Graph Theory and Cooperative Control Consensus
|           |        | 1   |                   | 1   |        |           |         |
| --------- | ------ | --- | ----------------- | --- | ------- | --------- | -------- |
|  x (k+1)= | x (k)+ |     | ∑a (x (k)−x (k))= |     | x (k)+ | ∑a x (kk) |          |
| i         | i      |     | ij j i            |     | i       | ij j      |  (2.59) |
|           |        | 1+d |                   | 1+d |        |           |         |
|           |        |     | i j∈Ni            |     | i       | j∈Ni      |          |
which is a weighted average of the previous states of node i and its neighbors. The
corresponding global input is
|     |     |     | u(k)=−(I+D)−1Lx(k) |     |     |     | (2.60) |
| --- | --- | --- | ------------------ | --- | --- | --- | ------ |
with D=diag{d}. The global dynamics is
i
|     | x(k+1)= | x(k)−(I+D)−1Lx(k)=(I+D)−1(I+A)x(k)≡ |     |     |     | Fx(k) | (2.61) |
| --- | ------- | ----------------------------------- | --- | --- | --- | ----- | ------ |
where the normalized DT consensus matrix is
|     |     |     | F = I−(I+D)−1L=(I+D)−1(I+A) |     |     |     | (2.62) |
| --- | --- | --- | --------------------------- | --- | --- | --- | ------ |
According  to  the  Geršgorin  circle  criterion  the  normalized  Laplacian  matrix
(I+D)−1L has all eigenvalues in the right-half s-plane within a disk centered at
d /(1+d ) with radius equal to d /(1+d ). Therefore, the F matrix has
| Max | Max |     | Max | Max |     |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- |
eigenvalues inside the shaded region in Fig. 2.12. Since d /(1+d )<1, this
|     |     |     |     |     | Max | Max |     |
| --- | --- | --- | --- | --- | --- | --- | --- |
region is always inside the unit circle. Therefore, if the graph has a spanning tree,
F has a simple eigenvalue at λ =1 and all other eigenvalues strictly inside the
1
unit circle. Then, the system (2.61) is marginally stable and of Type I, and the state
reaches a steady-state value.
Since Laplacian matrix L has row sums of zero, F has row sums of 1, and so is a
row stochastic matrix since
|                                             |     |     | (              | )   |     |     |        |
| ------------------------------------------- | --- | --- | -------------- | --- | --- | --- | ------ |
|                                             |     |     | F1= I−(I+D)−1L | 1=1 |     |     | (2.63) |
| Then, 1 is the right eigenvector of F for λ |     |     |                | =1. |     |     |        |
1
Let w =[p (cid:31) p ]T be a left eigenvector of F for λ =1, not necessarily nor-
|     | 1 1 | N   |     |     | 1   |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- |
malized. Then

wTx(k+1)=wTFx(k)=wTx(k)
(2.64)
|     |     |     | 1 1 |     | 1   |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- |
so that the quantity (2.57) is invariant, but now p  are defined with respect to matrix
i
F. Then, the quantity x =∑px(k) is a constant of the motion. If the graph has a
i i
i
spanning tree, the consensus value x = x =c,∀i, jis given by (2.39) in terms of
|                                            |     |     | i j      |     |     |     |     |
| ------------------------------------------ | --- | --- | -------- | --- | --- | --- | --- |
| the elements of the left eigenvector for λ |     |     | =1 of F. |     |     |     |     |
1
If the graph is balanced, however, then row sums of L are equal to column sums
and c1 is a left eigenvector of L for λ =0. However, in (I+D)−1L the i-th row is
1
divide−d by 1+d . Therefore, (I+D)−1L is not balanced. Hence, F is not balanced
i
and so even for balanced graphs the average consensus (2.31) is not reached. The
consensus value of (2.61) depends on graph properties even for balanced graphs.

2.5 Consensus with First-Order Discrete-Time Dynamics 51
F ig. 2.12 Region of eigen-
values of discrete-time graph
matrix F
This is true also for general undirected graphs. However, if all nodes have the same
in-degree, then L balanced implies that (I+D)−1L is balanced. Hence, F is bal-
anced and average consensus is reached. An undirected graph where all nodes have
the same degree d is called d-regular.
Let w be a left eigenvector of L for λ =0. Then w is not a left eigen-
1 1 1
vector of F for λ =1 unless the graph is regular. Then, it can be checked that
1
wTF =wT(I−(I+D)−1L)=wT.
i i i
2.5.3 Average Consensus Using Two Parallel Protocols
at Each Node
The average consensus problem yields the average of the initial states (2.31), inde-
pendently of the left eigenvector of λ =1 and hence of the graph topology. This is
1
important in a variety of applications. It has been seen that if the graph is balanced,
the continuous-time protocol (2.16) and the Perron protocol (2.49) both yield av-
erage consensus (2.31) independently of the detailed topology of the graph. The
normalized DT protocol (2.59) does not yield average consensus unless the graph is
regular (all nodes have the same in-degree). There are several ways to obtain aver-
age consensus for this protocol [12].
Suppose each node i knows its component p of the normalized left eigenvector
i
w of F for λ =1, and the number of nodes N in the graph. Suppose it is desired
1 1
T
to reach average consensus on a prescribed vector x(0)=x
1
(0)x
2
(0)(cid:31)x
N
(0) .
Then, let each node run the normalized protocol (2.59) with initial state selected as
x(0)/Np. If the graph has a spanning tree, the weighted average consensus (2.39)
i i
is achieved. Substituting the selected initial conditions into (2.39) yields average
consensus (2.31).
The requirement for each node to know its own p as well as the number of
i
nodes N in the graph assumes that there is a central authority which computes the

52 2  Algebraic Graph Theory and Cooperative Control Consensus
graph structure and disseminates this global information, which is contrary to the
idea of distributed cooperative control. It is possible in some graph topologies for
each node to estimate global graph structural information by using multiple proto-
cols at each node, as follows.
Let each node be endowed with two states y (k),z (k), each running local proto-
i i
cols in the form (2.59) so that
|     |     | 1  |    |     |
| --- | --- | --- | --- | --- |
∑a
|     | y (k+1)= | y (k)+ | y (k)   | (2.65) |
| --- | -------- | ------- | -------- | ------ |
|     | i        | 1+d i   | ij j     |        |
|     |          | i      | j∈Ni    |        |
|     |          | 1      |         |        |
|     | z (k+1)= | z (k)+ | ∑a z (k) |        |
|     |          |         |         | (2.66) |
|     | i        | 1+d  i | ij j    |        |
|     |          | i       | j∈Ni     |        |
with prescribed initial states y (0),z (0). The global dynamics of y=[y y ]T ∈RN
|     | i   | i   | 1   | N   |
| --- | --- | --- | --- | --- |
are then
|     | y(k+1)=(I+D)−1(I+A)y(k)≡ |     | Fy(k) |        |
| --- | ------------------------ | --- | ----- | ------ |
|     |                          |     |       | (2.67) |
|     | z(k+1)=(I+D)−1(I+A)z(k)≡ |     | Fz(k) | (2.68) |
Now suppose the graph has a special topology known as the bidirectional equal-
neighbor weight topology [12]. In this topology, one has a ≠0⇒a ≠0 and
ij ji
a ≠0⇒a =1. Thus, each node equally weights its own current state and its
ij ij
neighbors’ current states by 1/(1+d ) in computing the next state. For this special
i
topology, it is easy to give explicit formulae for the components p  of left eigenvec-
i
N
tor w. Define the (modified) volume of the graph as Vol′=∑(1+d ). Then, for the
| 1                                                      |     |     | i   |     |
| ------------------------------------------------------ | --- | --- | --- | --- |
| bidirectional equal-neighbor weight topologies one has |     |     | i=1 |     |
1+d
p = i
|     |     | i   |     | (2.69) |
| --- | --- | --- | --- | ------ |
Vol′
This is easily verified by verifying that wTF =wT(I+D)−1(I+A)=wT for the
|     |     | 1   | 1   | 1   |
| --- | --- | --- | --- | --- |
given graph topology and left eigenvector components. Note that (2.69) gives a
 since ∑p
| normalized w | =1. |     |     |     |
| ------------ | --- | --- | --- | --- |
1 i
i
Now suppose it is desired to reach average consensus on a prescribed vec-
| x(0)=x |     | T   |     |     |
| -------- | --- | --- | --- | --- |
tor  1 (0)x 2 (0)(cid:31)x N (0) . Then, select initial states  y (0)=1/(1+d ),
i i
z (0)= x(0)/(1+d ). This is local information available to each node i. If the graph
| i i | i   |     |     |     |
| --- | --- | --- | --- | --- |
has a spanning tree, then according to (2.39) the two protocols (2.65), (2.66) reach
respective consensus values of
|     |        | N        | 1      |        |
| --- | ------ | -------- | ------ | ------ |
|     | y (k)→ | , z (k)→ | ∑x (0) |        |
|     |        |          |        | (2.70) |
|     | i      | Vol′ i   | Vol′ i |        |
i

| 2.6   Higher-Order Consensus: Linear Systems on Graphs  |     |     |     | 53  |
| ------------------------------------------------------- | --- | --- | --- | --- |
Then, the estimate of the average consensus value is given by
z (k) 1
|     | x(k)= | i → ∑x(0) |     | (2.71) |
| --- | ----- | --------- | --- | ------ |
|     | i     |           | i   |        |
y (k) N
|     |     | i i |     |     |
| --- | --- | --- | --- | --- |
This procedure results in average consensus independent of the graph topology.
This has been achieved by running two local voting protocols at each node, one of
which, y (k), estimates the global graph property N/Vol′. This is used to divide out
i
| the volume in the second protocol for z |     | (k). |     |     |
| --------------------------------------- | --- | ---- | --- | --- |
i
2.6   Higher-Order Consensus: Linear Systems on Graphs
We have just discussed cooperative control on graphs for dynamical systems that
have first-order dynamics, that is, a single integrator or discrete-time shift register at
each node. Now we discuss cooperative control for networked systems with higher-
order dynamics. In this case, conditions for consensus become more complex and
interesting. First, we consider linear systems, then systems having second-order
position/velocity type dynamics in the form of Newton’s second law.
In this section, we use A to denote the node dynamics system matrix, and a  to
ij
denote the graph edge weights. These should not be confused.
Consider the N systems distributed on communication graph G with identical
LTI node dynamics
x = Ax +Bu
|     |     |       |     | (2.72) |
| --- | --- | ----- | --- | ------ |
|     |     | i i i |     |        |
where x(t)∈Rn is the state of node i and u (t)∈Rm its control input. Select the
| i   |     | i   |     |     |
| --- | --- | --- | --- | --- |
node controls as the distributed local state variable feedback

|     | u   | =cK∑a (x −x) |     | (2.73) |
| --- | --- | ------------ | --- | ------ |
|     |     | i ij j       | i   |        |
j∈Ni
∈Rm×n. Here, a
with scalar coupling gain c>0 and feedback control matrix K
ij
are the elements of the graph adjacency matrix, not the node system matrix. That is,
they are the edge weights of graph G. These controls are based on the local voting
protocol structure where the control input of each node depends on the difference
between its state and those of all its neighbors. The coupling gains c and feedback
gains K of all nodes are the same.
The node closed-loop dynamics are

|     | x = Ax +Bu | = Ax +cBK∑a | (x −x) | (2.74) |
| --- | ----------- | ----------- | ------ | ------ |
|     | i i         | i i         | ij j i |        |
j∈Ni

54 2  Algebraic Graph Theory and Cooperative Control Consensus
The overall closed-loop graph dynamics is
|     |     | x   | [(I   | A) cL | BK]x |     |        |
| --- | --- | --- | ----- | ----- | ---- | --- | ------ |
|     |     |     | N     |       |      |     | (2.75) |
|     |     |     | ˙ = ⊗ | −     | ⊗    |     |        |
T
|                                             |     |     |     |     | =xT xT | (cid:31)xT  ∈RnN,  L is the  |     |
| ------------------------------------------- | --- | --- | --- | --- | ------- | ----------------------------- | --- |
| where the overall (global) state vector is  |     |     |     | x   |        | N                            |     |
1 2
graph Laplacian matrix, and ⊗ is the Kronecker product [1]. We use the Kronecker
product heavily in this section, mainly the property (M⊗N)(P⊗Q)=MP⊗NQ
for commensurate matrices M, N, P, and Q.
Define the cooperative feedback closed-loop system matrix on communication
graph G as
|     |     | A   | [(I | A)  | cL BK] |     |        |
| --- | --- | --- | --- | --- | ------ | --- | ------ |
|     |     |     | c N |     |        |     | (2.76) |
|     |     |     | =   | ⊗ − | ⊗      |     |        |
This matrix reflects the local closed-loop system matrix (A-BK) as modified by
distributed control on the graph structure L. Its stability depends on both the stabil-
ity properties of (A-BK) and the graph topology properties.
The next key result from [4] provides a method for analysis of the dynamics
(2.74)/(2.75) and relates their stability properties to the graph eigenvalues.
Lemma 2.1 Stability Condition for Cooperative Control Let λ,i=1,(cid:31),N be
i
the eigenvalues of the graph Laplacian matrix L. Then the stability properties of
dynamics (2.74)/(2.75) are equivalent to the stability properties of the N systems
|     |     |     | A-cλBK, | i=1,(cid:31),N |     |     | (2.77) |
| --- | --- | --- | ------- | -------------- | --- | --- | ------ |
i
in that they have the same eigenvalues.
Proof Define  a  transformation  M  such  that  J =M−1LM  is  upper  triangular
with the eigenvalues λ,i=1,(cid:31),N of L on the diagonal. Apply the state-space
i
transformation
1
|     | (M  | −   | I)[(I N | A) cL  | BK](M | I)  |        |
| --- | --- | --- | ------- | ------ | ----- | --- | ------ |
|     |     | ⊗   | ⊗       | −      | ⊗     | ⊗   |        |
|     |     | [(I | A)      | cJ BK] |       |     | (2.78) |
N
|     |     | =   | ⊗ − | ⊗   |     |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- |
and define new state ξ (M 1 I)δ. Then the transformed system is in block
|     |     | =   | − ⊗ |     |     |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- |
triangular form with diagonal blocks of the form
(cid:28)
|     |     |     | ξ =(A-cλBK)ξ |     |     |     | (2.79) |
| --- | --- | --- | ------------ | --- | --- | --- | ------ |
|     |     |     | i            | i   | i   |     |        |
Hence, stability of (2.74)/(2.75) is equivalent to stability of all of these systems,
since a state-space transformation does not change the eigenvalues.  □
This proof shows that A =[(I ⊗A)−cL⊗BK] is equivalent to the system
|     |                                      | c   | N   |     |     |      |        |
| --- | ------------------------------------ | --- | --- | --- | --- | ---- | ------ |
|     | diag{(A-cλBK),(A-cλBK),(cid:31)(A-cλ |     |     |     |     | BK)} | (2.80) |
|     |                                      |     | 1   | 2   |     | N    |        |
with λ,i=1,(cid:31),N being the eigenvalues of the graph Laplacian matrix L, in the
i
sense that they have the same eigenvalues.

| 2.7   Second-Order Consensus  |     |     |     |     | 55  |
| ----------------------------- | --- | --- | --- | --- | --- |
Condition (2.77) is complicated and means that consensus for a given feedback
matrix K may occur on some graphs but not on others. To guarantee consensus on
a given graph with given λ,i=1,(cid:31),N, matrix K must be selected to stabilize all
i
the systems (2.77). This is a complicated robust control problem. In subsequent
chapters, we show how to select K to obtain guaranteed consensus properties. Now,
we apply Lemma 2.1 to second-order consensus.
2.7   Second-Order Consensus
One application of consensus in cooperative control is the control of formations of
vehicles. Therefore, we now wish to study consensus for coupled systems that satisfy
Newton’s law x =u, which yields the second-order (double-integrator) node dynamics
i i
|     |     | x =v |     |     |        |
| --- | --- | ----- | --- | --- | ------ |
|     |     | i i   |     |     |        |
|     |     | v =u |     |     | (2.81) |
|     |     | i i   |     |     |        |
with position  x ∈R, speed  v ∈R, and acceleration input u ∈R. Consider the
|     | i   | i   |     | i   |     |
| --- | --- | --- | --- | --- | --- |
distributed position/velocity feedback at each node given by the second-order local
neighborhood protocols

|     | =c∑a | )+cγ∑a      |       |     |        |
| --- | ---- | ----------- | ----- | --- | ------ |
|     | u    | (x −x       | (v −v | )   |        |
|     | i    | ij j i      | ij j  | i   |        |
|     |      | j∈N i       | j∈N i |     |        |
|     | ∑ca  | ((          | )     |     |        |
|     | =    | (x −x )+γ(v | −v )  |     | (2.82) |
|     |      | ij j i      | j i   |     |        |
|     | j∈N  | i           |       |     |        |
where c>0 is a stiffness gain and cγ >0 is a damping gain. This is based on local
voting protocols in both position and speed, so that each node seeks to match all
its neighbors’ positions as well as their velocities. This is a variant of proportional-
plus-derivative control.
We would like to determine when this protocol delivers consensus and to find the
consensus values of position and speed. We analyze this protocol by two methods.
2.7.1   Analysis of Second-Order Consensus Using Position/
Velocity Local Node States
The first method for analyzing second-order consensus follows [24]. Define the
position/velocity local node states as z x v  and write the position/velocity
|     |     | i   | i i |     |     |
| --- | --- | --- | --- | --- | --- |
=
node dynamics at each node as
(cid:31) (cid:30)
|     |          | 0 1 0             |          |     |        |
| --- | -------- | ----------------- | -------- | --- | ------ |
|     | z        | z                 | u Az     | Bu  | (2.83) |
|     | ˙ i =    | 0 0 i + 1         | i = i +  | i   |        |
|     | (cid:31) | (cid:30) (cid:31) | (cid:30) |     |        |

56 2  Algebraic Graph Theory and Cooperative Control Consensus
Define the local distributed control protocols
|                                     |     |      |       | x −x    |           |        |
| ----------------------------------- | --- | ---- | ----- | --------- | --------- | ------ |
|                                     |     | =c[1 | γ] ∑  | j i       | ∑         |        |
|                                     | u   |      |       | a   =cK | a (z −z ) | (2.84) |
|                                     | i   |      |       | ij v −v  | ij j i    |        |
|                                     |     |      |       |  j i   |           |        |
|                                     |     |      | j ∈Ni |           | j ∈Ni     |        |
| where the feedback gain matrix is K |     |      |       | 1 γ       |           |        |
. This is state variable feedback at
=
each node.
|     |     |     |     | (cid:31) (cid:30) | T   |     |
| --- | --- | --- | --- | ----------------- | --- | --- |
Now identify this with (2.74), define z =zT zT (cid:31)zT  ∈R2N, and write the
|     |     |     |     |  1 | 2 N |     |
| --- | --- | --- | --- | --- | ---- | --- |
global closed-loop dynamics (2.75) as
|     |     | z   | [(I | A) cL BK]z | A z |        |
| --- | --- | --- | --- | ---------- | --- | ------ |
|     |     |     | N   |            | c   | (2.85) |
|     |     | ˙ = | ⊗   | − ⊗        | =   |        |
for the specific A, B, K just given.
Assume the graph has a spanning tree. Then, L has a simple eigenvalue at λ =0,
1
and hence has rank N-1, and the rest of its eigenvalues are strictly in the right half
of the s-plane. Under these conditions, we want to study consensus properties of
the protocol (2.82). First, we need to look at the stability properties of (2.85), and
second to find the position and speed consensus values.
To examine stability of the protocol, according to the proof of Lemma 2.1, A in
c
(2.85) is equivalent to
|     |     | diag{A,(A-cλBK),(cid:31)(A-cλ |     |     | BK)} | (2.86) |
| --- | --- | ----------------------------- | --- | --- | ---- | ------ |
|     |     |                               |     | 2   | N    |        |
with Re{λ}>0,i=2,(cid:31),N. Matrix A has two eigenvalues at µ 0 with geo-
| i   |     |     |     |     | 1 = |     |
| --- | --- | --- | --- | --- | --- | --- |
metric multiplicity equal to one and a Jordan block of order two. The characteristic
polynomials of the other blocks are
|                                         |     | sI-(A-cλBK) |     | =s2+cγλs+cλ |     | (2.87) |
| --------------------------------------- | --- | ----------- | --- | ----------- | --- | ------ |
|                                         |     |             |     | i           | i i |        |
| Then the characteristic polynomial of A |     |             |     |  is         |     |        |
c
N
|     |     |     | sI-A | =∏(s2+cγλs+cλ) |     | (2.88) |
| --- | --- | --- | ---- | -------------- | --- | ------ |
|     |     |     | c    |                | i i |        |
i=1
| Therefore, the eigenvalues of A |     |     |     |  are given by |     |     |
| ------------------------------- | --- | --- | --- | ------------- | --- | --- |
c
|     |     |     | (    |             | )    |        |
| --- | --- | --- | ---- | ----------- | ---- | ------ |
|     |     |     | s=-1 | cγλ± (cγλ)2 | -4cλ | (2.89) |
|     |     |     |      | i i         | i    |        |
2
| There are two eigenvalues of A |     |     |     |  for each eigenvalue λ of L. |     |     |
| ------------------------------ | --- | --- | --- | ---------------------------- | --- | --- |
|                                |     |     | c   |                              | i   |     |
The stability of the eigenvalues of A  can be studied using the Routh test. Sup-
c
pose graph eigenvalue λ is real. Then the Routh test shows that (2.87) is AS for all
i
cγ >0. If λ is complex, then
i
(s2+cγλs+cλ)(s2+cγλ*s+cλ*)
|     |                                        | i   | i   | i i |     |        |
| --- | -------------------------------------- | --- | --- | --- | --- | ------ |
|     | =s4+2cγαs3+(2cα+c2γ2µ2)s2+2c2γµ2s+c2µ2 |     |     |     |     | (2.90) |

| 2.7  |  Second-Order Consensus  |     |     |     |     |     |     |     | 57  |
| ---- | ------------------------ | --- | --- | --- | --- | --- | --- | --- | --- |
where * denotes complex conjugate, α=Re{λ},µ= λ . In the case c = 1, one can
|     |     |     |     |     |     | i   | i   |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
obtain explicit expression for stability from the Routh test. When c = 1, performing
the Routh test shows that (2.90) is AS if and only if
|     |     |     |     | γ2>(β2 | α2)/αµ2 |     |     |     | (2.91) |
| --- | --- | --- | --- | ------ | ------- | --- | --- | --- | ------ |
−
where β=Im{λ}. Therefore, all the systems in (2.86) for i=2,,N are AS if and
i
only if
Im2{λ}-Re2{λ}
|     |     |     | cγ2 >max | i        |     | i , i=2,(cid:31),N |     |     | (2.92) |
| --- | --- | --- | -------- | -------- | --- | ------------------ | --- | --- | ------ |
|     |     |     |          | i Re{λ}λ | 2   |                    |     |     |        |
|     |     |     |          |          | i i |                    |     |     |        |
The next result tells when the nodes reach consensus under the second-order proto-
col (2.82) and specifies the consensus values reached.
Theorem 2.4 Consensus of Second-Order Dynamics Consider the Newton’s law
systems at each node given by (2.81) with the local neighborhood protocols (2.82)
with c = 1. The nodes reach consensus in both position and speed if and only if the
graph has a spanning tree and the gain γ is selected to satisfy condition (2.92),
with λ being the eigenvalues of the graph Laplacian L. Then, the position and
i
speed consensus values are given respectively by
|     |     |     |     | 1 N    |     | 1 N     |     |     |        |
| --- | --- | --- | --- | ------ | --- | ------- | --- | --- | ------ |
|     |     |     |     | ∑px(0) |     | t∑pv(0) |     |     |        |
|     |     |     | x   | =      | +   |         |     |     | (2.93) |
|     |     |     |     | N i    | i   | N i     | i   |     |        |
|     |     |     |     | i=1    |     | i=1     |     |     |        |
N
1
|     |     |     |     | v = | ∑p  | v (0) |     |     |        |
| --- | --- | --- | --- | --- | --- | ----- | --- | --- | ------ |
|     |     |     |     |     |     | i i   |     |     | (2.94) |
N i=1
Proof It has been seen that, when c = 1, (2.85) is AS if and only if (2.92) holds.
Now, it is necessary to examine the eigenstructure of A  in (2.85). First we need
c
to find the left and right eigenvectors of A , which is equivalent to (2.86) in the
c
sense that they have the same eigenvalues. Matrix A in (2.83) has an eigenvalue at
µ 0 of geometric multiplicity one and algebraic multiplicity two. The rank-1
1 =
|     |     |     |     | T   | T   |     |     |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
right eigenvector is  1 0  since A 1 0 0. The rank-2 right eigenvector is
=
|     | T   |     | T   | T   |     |     |     |     | T   |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
0 1  since A 0 1 1 0 . (cid:31)The ra(cid:30)nk-1 left eigenvector is  0 1  since
(cid:31) = (cid:30)
T
0 1 A 0. T(cid:31)he ran(cid:30)k-2 le(cid:31)ft eige(cid:30)nvector is  1 0  since  1 0 A 0 1 .
| (cid:31) | (cid:30) = |     |     |     |     |     |     | (cid:31) | = (cid:30) |
| -------- | ---------- | --- | --- | --- | --- | --- | --- | -------- | ---------- |
The right eigenvector of L for λ =0 is 1 RN. Let the corresponding left ei-
(cid:31) (cid:30) 1 (cid:31)∈ (cid:30) (cid:31) (cid:30) (cid:31) (cid:30)
|                         |     |     |            | ]T, normalized s | −      | o that wT1 |                          |                   |     |
| ----------------------- | --- | --- | ---------- | ---------------- | ------ | ---------- | ------------------------ | ----------------- | --- |
| genvector be w          |     | =[p | (cid:31) p |                  |        |            | 1. Then we claim a rank- |                   |     |
|                         |     | 1   | 1          | N                |        | 1          | =                        |                   |     |
|                         |     |     |            |  in (2.85) for λ | =0 is  | y1−        | =1⊗[1                    | 0]T               |     |
| 1 right eigenvector of  |     |     | A          |                  | 1      | 1          |                          | . This is easily  |     |
c
verified by checking that A y1 =0. It is easy to verify that a rank-2 right eigenvec-
c 1
|     |     | y2 =1⊗[0 |     | 1]T |     |     |     |     |     |
| --- | --- | -------- | --- | --- | --- | --- | --- | --- | --- |
tor of  A  is   by checking that A y2 = y1. Similarly, it is found
|                                     | c   | 1   |     |        |                   | c   | 1 1 |     |         |
| ----------------------------------- | --- | --- | --- | ------ | ----------------- | --- | --- | --- | ------- |
|                                     |     |     |     |        | =0 is given by w1 |     |     | ⊗[0 | 1]T     |
| that a rank-1 left eigenvector of A |     |     |     |  for λ |                   |     | =w  |     |  and a  |
|                                     |     |     |     | c      | 1                 |     | 1   | 1   |         |
| rank-2 left eigenvector by w2       |     |     |     | ⊗[1    | 0]T               |     |     |     |         |
|                                     |     |     |     | =w     |                   | .   |     |     |         |
|                                     |     |     |     | 1 1    |                   |     |     |     |         |

58 2  Algebraic Graph Theory and Cooperative Control Consensus
Now we will study the Jordan normal form of A  and perform a modal decom-
c
position on (2.85) to find the steady-state consensus values for position and speed.
Bring A  to Jordan normal form
c

(w 2)T
|     |     |     |     | 0  | 1   | 0  | 1   |     |     |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
 
|     | =MJM−1 |     | =y1 y2 | (cid:31)  |     |  (w1)T |     |        |     |     |     |
| --- | ------ | --- | ------- | ----------- | --- | -------- | --- | ------ | --- | --- | --- |
|     | A      |     |         |             | 0 0 | 0        |    | (2.95) |     |     |     |
|     | c      |     |  1 1   |           |     |         | 1   |        |     |     |     |
 
|     |     |     |     |  0 | 0   | stable  | (cid:30) |     |     |     |     |
| --- | --- | --- | --- | ---- | --- | --------- | -------- | --- | --- | --- | --- |
 
where M is the matrix having right eigenvectors as columns, and M-1 is the matrix
having left eigenvectors as rows. Then
2) T
|     |     |     |     |     |     |     |     | 1 t 0 |     | (w  |     |
| --- | --- | --- | --- | --- | --- | --- | --- | ----- | --- | --- | --- |
¯1
|     |     |       | eActz(0)      | MeJtM     |       | 1z(0)     | 1 2   |          |     | (w 1) | T      |
| --- | --- | ----- | ------------- | --------- | ----- | --------- | ----- | -------- | --- | ----- | ------ |
|     |     | z(t)  |               |           | −     |           | y y   | 0 1 0    |   | ¯1    |  z(0) |
|     |     |       | =             | =         |       | =         | ¯1 ¯1 | ···     |     | .     |        |
|     |     |       |               |           |       |           |       | 0 0st a  | ble | .     |        |
|     |     |       |               |           |       | (cid:31)  |       | (cid:30) |     | .     |        |
|     |     |       |               |           | (w   | 2)T      |       |          |    |       |       |
|     |     |       | 1            | t         | 0    |           |       |         |   |       |       |
|     |     |       |               |           |      | 1        |       |          |     |       |        |
|     |     |       |              |           |      |           |       |          |     |       |        |
|     | =  | y 1 y | 2 (cid:31) 0 | 1         | 0 (w | 1)T z(0) |       |          |     |       |        |
|     |     |  1   | 1           |           |      | 1         |       | (2.96)   |     |       |        |
|     |     |       |               |           |      |          |       |          |     |       |        |
|     |     |       |  0          | 0 stable |       | (cid:29)  |       |          |     |       |        |
|     |     |       |               |           |    |         |       |          |     |       |        |
yields the modal decomposition
(w2)Tz(0)+t(w1)Tz(0)
|     |          |            | 1   |           | 1   |     |     |     |     |     |     |
| --- | -------- | ---------- | --- | --------- | --- | --- | --- | --- | --- | --- | --- |
|     |          |            |    |           |     |    |     |     |     |     |     |
|     | z(t)=y1 | y2         |     | (w1)Tz(0) |     |     |     |     |     |     |     |
|     |          | (cid:31) |     |           |     |    |     |     |     |     |     |
|     |  1      | 1          |    | 1         |     |     |     |     |     |     |     |
|     |          |            |    |           |     |    |     |     |     |     |     |
(cid:29)
|     |                        |     |   |                              |     |   |     |        |     |     |     |
| --- | ---------------------- | --- | --- | ---------------------------- | --- | --- | --- | ------ | --- | --- | --- |
|     | ( (w2)Tz(0)+t(w1)Tz(0) |     |     | ) y1+(w1)Tz(0)y2+stableterms |     |     |     |        |     |     |     |
|     | =                      |     |     |                              |     |     |     | (2.97) |     |     |     |
|     | 1                      |     | 1   | 1                            | 1   | 1   |     |        |     |     |     |
Note now that
|               |           |      |          | 1        |      | 0                 |     |        |     |     |     |
| ------------- | --------- | ---- | -------- | -------- | ---- | ----------------- | --- | ------ | --- | --- | --- |
|               |           | z(t) | x(t)     |          | v(t) |                   |     |        |     |     |     |
|               |           |      |          |          |      |                   |     | (2.98) |     |     |     |
|               |           | =    | ⊗        | 0 +      | ⊗    | 1                 |     |        |     |     |     |
|               |           |      | (cid:31) | (cid:30) |      | (cid:31) (cid:30) |     |        |     |     |     |
|               |           |      |          |          |      | xT xT             | xT  | T RN,  |     |     |     |
| with  global  | position  | and  | speed    | vectors  | x    |                   |     |        |     |     |     |
|               |           |      |          |          | =    | 1 2               | ··· | N ∈    |     |     |     |
T T T T RN. According to the de(cid:31)finitions of the left (cid:30)and right
| v v | v     | v   |     |     |     |     |     |     |     |     |     |
| --- | ----- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| = 1 | 2 ··· | N ∈ |     |     |     |     |     |     |     |     |     |
eigen(cid:31)vectors of A  for λ(cid:30)1 =0, one sees that the position and speed consensus val-
c
| ues induced by the protocol (2.82) are (2.93), (2.94).  |     |     |     |     |     |     |     | □   |     |     |     |
| ------------------------------------------------------- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
It is seen that condition (2.92) depends on the graph topology through the eigenval-
ues of the graph Laplacian matrix L. Therefore, for a given feedback gain matrix K,
one may have consensus on one graph but not on a different graph.
If there is no spanning tree, then λ =0 in (2.86). Then, there are unstable terms
2
in (2.96) and consensus is not reached.
If the graph is strongly connected then it has a spanning tree and Theorem 2.4
holds. Moreover, if the initial velocities are all equal to zero, then the consensus

| 2.7   Second-Order Consensus  |     |     |     | 59  |
| ----------------------------- | --- | --- | --- | --- |
speed is equal to zero and all nodes end up at rest at the weighted center of gravity
of the initial positions, that is, the first term in (2.93). The next result has also been
established.
Corollary 2.1 Let the graph have a spanning tree and all eigenvalues of the Lapla-
cian L be real. Then the consensus values (2.93), (2.94) are reached for any positive
control gains c,γ in (2.82).
Proof The Routh test reveals that (2.87) is AS under the hypotheses.  □
If the graph is undirected, then the Laplacian eigenvalues are real and this corollary
holds.
2.7.2   Analysis of Second-Order Consensus Using Position/
Velocity Global State
The second method for analyzing second-order consensus follows [16, 18]. It hing-
es on another way to write the global dynamics than (2.85).
Take  Newton’s  law  node  dynamics  (2.81)  and  the  second-order  protocols
(2.82). Define the global position and speed vectors as x=xT xT (cid:31)xT T ∈RN ,

 1 2 N
T
v =vT vT(cid:31)vT  ∈RN. Define the global state vector in position/velocity form
|  1 2 | N  |     |     |     |
| ----- | --- | --- | --- | --- |
T
as z =xT vT ∈R2N. Then the global dynamics can be written as
|    |          |     |         |        |
| --- | --------- | --- | ------- | ------ |
|     |           |  0 | I      |        |
|     | z(cid:28) | =  | z ≡ A z | (2.99) |
 c
|     |     | -cL -cγL |    |     |
| --- | --- | --------- | --- | --- |
This is in global position/velocity form, whereas (2.85) has the global state defined
in terms of the interleaved node positions and velocities according to the local posi-
tion/velocity state definitions (2.83).
The characteristic polynomial of this system is
sI -I
|     | sI-A = |     | = s2I+cγLs+cL | (2.100) |
| --- | ------ | --- | ------------- | ------- |
c
cL sI+cγL
As in the proof of Lemma 2.1, define a transformation M such that J =M−1LM is
upper triangular with the eigenvalues λ,i=1,(cid:31),N of L on the diagonal. Write
i
|     | s2I+cγLs+cL | = M ⋅ M-1 | ⋅ s2I+cγLs+cL |     |
| --- | ----------- | --------- | ------------- | --- |

|     | M-1(s2I+cγLs+cL)M |     | s2I+cγJs+cJ |         |
| --- | ----------------- | --- | ----------- | ------- |
|     | =                 |     | =           | (2.101) |
Matrix (s2I cγJs cJ) is in block triangular form with the eigenvalues λ of
| +   | +   |     |     | i   |
| --- | --- | --- | --- | --- |
L on the diagonal. Consequently,

60 2  Algebraic Graph Theory and Cooperative Control Consensus
N
|     |     |     | s2I+cγLs+cL |     | =∏(s2+cγλs+cλ) |     |     |     | (2.102) |
| --- | --- | --- | ----------- | --- | -------------- | --- | --- | --- | ------- |
|     |     |     |             |     |                |     | i   | i   |         |
i=1
| Therefore, the eigenvalues of A |     |     |     |  are given by |     |     |     |     |     |
| ------------------------------- | --- | --- | --- | ------------- | --- | --- | --- | --- | --- |
c
|     |     |     |     | 1(   |        |      | )   |     |         |
| --- | --- | --- | --- | ---- | ------ | ---- | --- | --- | ------- |
|     |     |     | s=- | cγλ± | (cγλ)2 | -4cλ |     |     | (2.103) |
|     |     |     |     |      | i      | i    | i   |     |         |
2
and there are two eigenvalues of A  for each eigenvalue λ of L.
|     |     |     |     | c   |     |     |     | i   |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
These results are the same as (2.88). Therefore, all the subsequent development
there follows here, eventually providing another path to Theorem 2.4.
2.7.3   Formation Control Second-Order Protocol
In the control of formations, it is desired for not only all vehicles to reach the same
consensus speed but also the steady-state positions to be in some prescribed forma-
tion relative to each other. The protocol just given causes all nodes to move to the
same final position. Moreover, in formation control the positions are in 2-D or 3-D.
Therefore, let the formation move in an n-dimensional space and consider the
node dynamics
x =v
|     |     |     |     |     | i   | i   |     |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
(2.104)
v =u
|     |     |     |     |     | i   | i   |     |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
with vector position x ∈Rn, speed v ∈Rn, and acceleration input u ∈Rn. For mo-
|     |     |     | i   |     | i   |     |     | i   |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
q]T, where (p(t),q(t))
| tion in the 2-D plane, for instance, one would take x |     |     |     |     |     |     | =[p |     |     |
| ----------------------------------------------------- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
|                                                       |     |     |     |     |     |     | i   | i i | i i |
T
is the position of node i in the (x, y)-plane. The node states are z x T v T R2n
|     |     |     |     |     |     |     |     | i i | i   |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
|     |     |     |     |     |     |     |     | =   | ∈   |
and the local node dynamics are given by
|     |     |     |              |        |      |        |     | (cid:31) | (cid:30) |
| --- | --- | --- | ------------ | ------ | ---- | ------ | --- | -------- | -------- |
|     |     |     |              | 0 I  | 0  |        |     |          |          |
|     |     |     | z(cid:28) = | n      | z + | u = Az | +Bu |          |          |
|     |     |     | i            |       | i    |  i    | i   | i        | (2.105)  |
|     |     |     |              | 0 0  | I   |       |     |          |          |
n
Define the constant desired position of node i relative to the moving formation cen-
ter x  as ∆ ∈Rn. Suppose it is desired for the nodes to follow a leader or control
| 0                                        | i   |     |     |     |     |                                      |     |     |     |
| ---------------------------------------- | --- | --- | --- | --- | --- | ------------------------------------ | --- | --- | --- |
| node with position and speed given by x |     |     |     |     |     | =v                                   |     |     |     |
|                                          |     |     |     |     | 0   | 0 . Consider the distributed second- |     |     |     |
order leader-following formation protocols at each node given by [16]
|     | u   | =v(cid:28) +γk | (v -v | )+k   | (x +∆ | -x ) |       |         |     |
| --- | --- | -------------- | ----- | ----- | ----- | ---- | ----- | ------- | --- |
|     | i   | 0              | v 0   | i     | p 0   | i i  |       |         |     |
|     |     | +c∑a           |       | (     |       | )    | +cγ∑a |         |     |
|     |     |                |       | (x -∆ | )-(x  | -∆ ) |       | (v -v ) |     |
|     |     |                | ij    | j     | j i   | i    |       | ij j i  |     |
|     |     |                | j∈N i |       |       |      | j∈N   | i       |     |

|     | =v(cid:28) | +γk | (v -v | )+k   | (x +∆ | -x )     |     |     |         |
| --- | ---------- | --- | ----- | ----- | ----- | -------- | --- | --- | ------- |
|     |            | 0   | v 0   | i     | p 0   | i i      |     |     |         |
|     |            |     |       | (     |       |          |     | )   |         |
|     |            | +   | ∑ca   | (x -∆ | )-(x  | -∆ )+γ(v | -v  | )   | (2.106) |
|     |            |     | ij    | j     | j i   | i        | j   | i   |         |
j∈N
i

| 2.7   Second-Order Consensus  |     |     |     |     |     |     |     |     | 61  |
| ----------------------------- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
where c>0 is a stiffness gain and γ >0 is a damping gain. This protocol includes
leader’s velocity feedback with gain of γk >0, leader’s position feedback with gain
v
of k >0, and leader’s acceleration feedforward. The aim of this protocol is to en-
p
sure that all nodes reach consensus in position and speed and that x(t)→x (t)+∆,
|        |      |                    |     |     |     |     |     | i   | 0 i |
| ------ | ---- | ------------------ | --- | --- | --- | --- | --- | --- | --- |
| v(t)→v | (t), | ∀i asymptotically. |     |     |     |     |     |     |     |
i 0
Define  the  motion  errors  x = x −∆ −x ,  v =v −v   and  the  node  error
|                  |            |            |                                                   | i     | i i  | 0       | i i 0    |     |           |
| ---------------- | ---------- | ---------- | ------------------------------------------------- | ----- | ---- | ------- | -------- | --- | --------- |
|                  | T          | T T        | R2n. Then the closed-loop node error dynamics are |       |      |         |          |     |           |
| z i              | x v        |            |                                                   |       |      |         |          |     |           |
| ˜ =              | ˜i ˜i      | ∈          |                                                   |       |      |         |          |     |           |
|                 | (cid:31) 0 | (cid:30) I |  0                                             |       |      |         |          |     |           |
| (cid:28)(cid:27) |            | n          |                                                   | ∑     | (    |         |          |     | )         |
|  z =            |            |            |  z(cid:27) +                                    |  ca  | (x   | -∆ )-(x | -∆ )+γ(v | -v  | ) (2.107) |
| i                | -k I       | -γk I      | i I                                              |       | ij j | j       | i i      | j   | i         |
|                 | p n        | v          | n                                                | n    |      |         |          |     |           |
|                  |            |            |                                                   | j∈N i |      |         |          |     |           |
which yields the global error dynamics
(cid:28)(cid:27)=(I
|        |          |     | z      | ⊗A)-cL⊗BKz(cid:27)≡ |     |          | A z(cid:27) |     | (2.108) |
| ------ | -------- | --- | ------ | -------------------- | --- | -------- | ----------- | --- | ------- |
|        |          |     |        |  N                  |     |         | c           |     |         |
|        |          | T T |        | T T R2nN, K          |     | I        | γI          |     |         |
| with z | z        | z   | z      |                      |     | n        | n , and     |     |         |
|        | ˜ = ˜1   | ˜2  | ··· ˜N | ∈                    |     | =        |             |     |         |
|        | (cid:31) |     |        | (cid:30)             |     | (cid:31) | (cid:30)    |     |         |
|        |          |     |        |                     | 0   | I        |            |     |         |
n
|     |     |     |     | A= |     |       |    |     | (2.109) |
| --- | --- | --- | --- | --- | --- | ----- | --- | --- | ------- |
|     |     |     |     | -k  | I   | -γk I |     |     |         |
|     |     |     |     |    | p n | v n  |     |     |         |
We want to examine stability of the protocol and determine when x(t)→x (t)+∆ , v(t)→v (t), ∀i
|     |     |     |     |     |     |     |     | i   | 0 i i 0 |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | ------- |
x(t)→x (t)+∆ , v(t)→v (t), ∀i. Assume the graph has a spanning tree. To examine stability, ac-
i 0 i i 0
cording to the proof of Lemma 2.1, A  in (2.108) is equivalent to
c
|     |     |     | diag{A,(A-cλBK),(cid:31)(A-cλ |     |     |     | BK)} |     | (2.110) |
| --- | --- | --- | ----------------------------- | --- | --- | --- | ---- | --- | ------- |
|     |     |     |                               |     | 2   |     | N    |     |         |
with λ being the eigenvalues of Laplacian matrix L and Re{λ}>0,i=2,(cid:31),N.
|     | i   |     |     |     |     |     | i   |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
Without loss of generality, assume motion in 1-D and set n=1. Motion in other
coordinate directions will be the same as the motion along a line as analyzed here.
Matrix  A has the characteristic polynomial s2+γk s+k , which is stable for all
v p
k ,k >0. The characteristic polynomials of the other blocks are
p v
|                                         |     | sI-(A-cλBK) |     | =s2+γ(k |     | +cλ)s+(k | +cλ) |     | (2.111) |
| --------------------------------------- | --- | ----------- | --- | ------- | --- | -------- | ---- | --- | ------- |
|                                         |     |             |     | i       |     | v        | i p  | i   |         |
| Then the characteristic polynomial of A |     |             |     |         |  is |          |      |     |         |
c
N
=∏(s2+γ(k
|     |     | sI-A |     |     | +cλ | )s+(k | +cλ )) |     | (2.112) |
| --- | --- | ---- | --- | --- | --- | ----- | ------ | --- | ------- |
|     |     |      | c   |     | v   | i     | p i    |     |         |
i=1
| Therefore, the eigenvalues of A |     |     |     |  are given by |     |     |     |     |     |
| ------------------------------- | --- | --- | --- | ------------- | --- | --- | --- | --- | --- |
c

|     | 1(  |           |     |            |      |      | )       |     |         |
| --- | --- | --------- | --- | ---------- | ---- | ---- | ------- | --- | ------- |
| s=- |     | γ(k +cλ)± |     | γ2(k +cλ)2 | -4(k | +cλ) | , i=1,… | ,N  | (2.113) |
|     |     | v         | i   | v          | i    | p    | i       |     |         |
2

62 2 Algebraic Graph Theory and Cooperative Control Consensus
There are two eigenvalues of A (in each dimension of motion) for each eigenvalue
c
λ of L. Since the graph has a spanning tree we have λ =0 and λ >0,i=2,(cid:31),N.
i 1 i
Note that for λ =0, (2.111) is AS for k >0,k >0.
1 p v
For real λ the Routh test shows that (2.111) is AS for all cγ >0, α>0,
i
k >0,k >0. If λ is complex it is difficult to get a condition for stabilizing gains.
p v i
A complicated expression in the vein of (2.92) can be developed for stability. Sim-
pler expressions can be developed for special choices of gains.
Theorem 2.5 Consensus of Formation Protocol Consider the Newton’s law
motion dynamics at each node given by (2.104). The leader-following protocols
(2.106) guarantee that x(t)→x (t)+∆ , v(t)→v (t), ∀i asymptotically if the
i 0 i i 0
graph has a spanning tree and the gains c,γ,k p ,k v are selected to make (2.112) AS.
Proof Under the hypotheses, the polynomials in (2.112) are AS so that the error
dynamics (2.108) are AS. Therefore, x = x −∆ −x and v =v −v go to zero
i i i 0 i i 0
and the theorem follows. □
The proof of this result is far simpler than the proof of Theorem 2.4 because A
in (2.109) has stable eigenvalues, whereas matrix A in (2.83) has an eigenvalue at
µ 0 of geometric multiplicity one and algebraic multiplicity two. This requires
1
=
an analysis of the structure of the eigenspace for µ 0 in the proof of Theorem 2.4.
1
=
The following result has also been established.
Corollary 2.2 Let the graph have a spanning tree and all eigenvalues of the Lapla-
cian L be real. Then x(t)→x (t)+∆ , v(t)→v (t), ∀i asymptotically for any
i 0 i i 0
gains c,γ >0 k ,k >0.
p v
Proof The Routh test reveals that (2.111) is AS under the hypotheses. □
If the graph is undirected, then the Laplacian eigenvalues are real and this corollary
holds.
A disadvantage of protocol (2.106) is that all nodes must know the leader node’s
position x (t) and speed v (t). In realistic formations, each node only knows posi-
0 0
tion and speed information about a few neighbors. Only a few immediate followers
of the leader, his wingmen, can sense his motion, and other nodes follow these
wingmen, and so on. We shall show how to correct this deficiency in Chap. 3 and
the following chapters, when we discuss the cooperative tracking problem, also
known as pinning control.
2.8 Matrix Analysis of Graphs
We have studied basic concepts of consensus and cooperative control for dynamic
agents connected by a communication graph topology. It was seen that the graph
properties and the properties of the individual node dynamics interact in intriguing
ways that are not at all obvious to a casual inspection. The graph topology can have
beneficial effects on individual node and team behaviors, such as inducing consen-

| 2.8   Matrix Analysis of Graphs  |     |     |     |     | 63  |
| -------------------------------- | --- | --- | --- | --- | --- |
sus under certain conditions, or detrimental effects, such as destabilizing the overall
team dynamics though the individual node dynamics are stable.
Graph properties can be studied through the theory of certain matrix properties.
In this section, we introduce some concepts that are important for analysis of graphs
and cooperative control performance using matrix techniques. The main references
in this section are [6, 13, 23].
2.8.1   Irreducible Matrices and Frobenius Form
An arbitrary square matrix E is reducible if it can be brought by a row/column per-
mutation matrix T to lower block triangular form
* 0
|     |     | F =TETT | =  |     | (2.114) |
| --- | --- | ------- | --- | --- | ------- |

* *
Otherwise the matrix is irreducible. Two matrices that are similar using permu-
tation matrices are said to be cogredient. Note that, if T is a permutation matrix
then T−1 =TT.
The next result ties irreducible matrices to graph theory.
Theorem 2.6 A graph G is strongly connected if and only if its adjacency matrix A
is irreducible [13].
Lemma 2.2 A is irreducible if and only if D-A is irreducible for any diagonal
matrix D.
|             | 0                     |     |      | 0             |      |
| ----------- | --------------------- | --- | ---- | ------------- | ---- |
| Proof  TATT | ∗  if and only if T(D |     | A)TT | ∗  since TDTT |  is  |
|             | =                     |     | −    | =             |      |
(cid:31)∗ ∗(cid:30)
(cid:31)∗ ∗(cid:30)
| diagonal for all permutation matrices T.  |     |     |     |     | □   |
| ----------------------------------------- | --- | --- | --- | --- | --- |
According to these results, both the adjacency matrix A and Laplacian matrix
L= D−A of a graph G are irreducible if and only if the graph is strongly connected.
 Example 2.5 Irreducible Sets of Equations [21]
Consider the linear equations
|     |     |     | Ex=b |     | (2.115) |
| --- | --- | --- | ---- | --- | ------- |
with E being a matrix, and x and b vectors. If E is nonsingular, there is a unique
solution x. Yet, E may be singular and the system of equations can still enjoy some
important properties. Let T be a permutation matrix and write
|               | Ex=TTFTx=b,                                    |     | FTx=Tb, | Fx =b | (2.116) |
| ------------- | ---------------------------------------------- | --- | ------- | ----- | ------- |
| where x =Tx,b | =Tb. Suppose now that E is reducible and write |     |         |       |         |

64 2  Algebraic Graph Theory and Cooperative Control Consensus
|     | F  | 0 x  b      |     |         |
| --- | --- | ---------------- | --- | ------- |
|     | 11  | 1 = 1         |     |         |
|     |    |                |     | (2.117) |
|     | F  | F 22x 2 b 2 |     |         |
21
or
|     | F x =b, | F x =b −F   | x   | (2.118) |
| --- | ------- | ----------- | --- | ------- |
|     | 11 1    | 1 22 2 2 21 | 1   |         |
This means the equations can be solved by first solving a reduced set of equations
for x  and then solving for x . On the other hand, if E is irreducible, the equations
| 1   | 2   |     |     |     |
| --- | --- | --- | --- | --- |
must be solved simultaneously for all variables.
 Frobenius Form and Hierarchical Structure of Graphs
A reducible matrix E can be brought by a permutation matrix T to the lower block
triangular Frobenius canonical form [13, 23]
|     |     | F 0 (cid:31) | 0  |     |
| --- | --- | ------------- | --- | --- |
11
|     |       |                             |           |         |
| --- | ----- | ---------------------------- | ---------- | ------- |
|     |       | F F (cid:31)                 | 0          |         |
|     | =TETT |  21 22                      |           |         |
|     | F     | =                            |            | (2.119) |
|     |       |  (cid:29) (cid:29) (cid:30) | (cid:29)  |         |
|     |       |                             |           |         |
|     |       | F F (cid:31)                 | F          |         |
|     |       |  p1 p2                     | pp       |         |
where F  is square and irreducible. Note that if F  is a scalar and irreducible it is
| ii  |     | ii  |     |     |
| --- | --- | --- | --- | --- |
equal to 0. The degree of reducibility is defined as  p-1. The graph has p strongly
connected subgraphs corresponding to the graphs of the diagonal blocks.
The conversion to lower block triangular form can be done in linear time using
search algorithms.
The Frobenius form (2.119) is said to be lower triangularly complete if in every
block row i there exists at least one  j<i such that F ≠0. That is, every block row
ij
has at least one nonzero entry.
Theorem 2.7 A graph G has a spanning tree if and only if its adjacency matrix A
has a Frobenius form that is lower triangularly complete [13].
Diagonal matrix F  corresponds to a strongly connected leader group of root nodes
11
with no incoming edges from the remainder of the group. If the graph has a span-
ning tree, then the nodes having a directed path to all other nodes are roots of span-
ning trees and members of the leader group. These correspond to the graph of leader
block F  in Frobenius form.
11
The Frobenius form of a graph adjacency matrix exposes the hierarchical struc-
ture of a graph. Note that diagonal block F  corresponds to a strongly connected
11
leader group with no incoming edges from the remainder of the graph. It may be
a set of root nodes for certain blocks F  as determined by the nonzero entries in
ii
blocksF , j<i.
ij

2.8 Matrix Analysis of Graphs 65
Any diagonal block F that has no nonzero entries in its row blocks F , j<k
kk kj
has no incoming edges in the graph and is also a strongly connected leader group.
It may be a set of root nodes for a subgraph determined by the elements of the off
diagonal blocks.
Cyclic or Periodic Matrices
An important class of graphs are the cyclic or periodic graphs. A graph is a cycle
if all of its vertices are connected in a single closed path. A more general class of
periodic graphs are those which have groups of vertices, with the groups being con-
nected by a closed path. These graphs can be studied using Frobenius form.
The spectral radius of a square matrix E∈Rn×n is ρ(E)=maxλ , the maxi-
i
mum magnitude of the eigenvalues of E. i
Theorem 2.8 Perron–Frobenius Let a square matrix E∈Rn×n have nonnegative
elements. Then if E is irreducible and if p≥1 eigenvalues of E are of magnitude
ρ(E), they are distinct roots of polynomial equation λp -[ρ(E)]p =0 and there
exists a permutation matrix T such that E can be expressed in the cyclic form
 0 F 0 (cid:31) 0 
12
 
0 0 F (cid:31) 0
 23 
F =TETT = 0 (cid:29) (cid:29) (cid:30) (cid:29) 
 
 0 0 0 0 F (p-1)p
  F p1 0 0 0 0  
where the diagonal zero blocks are square. Then, matrix E is called p-cyclic or
p-periodic. The index of cyclicity or periodicity is p [6, 13, 23].
The cyclicity period p of E is the greatest common divisor of the lengths of all the
loops in the graph of E. Matrix E is acyclic or aperiodic if the cyclicity period is 1,
i.e., if E is 1-cyclic, p = 1.
If graph A is a cycle of length p, then Ap = I is the identity matrix.
2.8.2 Stochastic Matrices
Important in the study of graphs are the stochastic matrices. We say a matrix E
is nonnegative, E 0, if all its elements are nonnegative. Matrix E is positive,
(cid:31)
E0, if all its elem−ents are positive.
A matrix E 0 is row stochastic if all its row sums equal to 1. A matrix E 0
(cid:31) (cid:31)
is doubly stocha−stic if all its row sums and column sums equal to 1. The produc−t of
two row stochastic matrices E, F is row stochastic because EF1 E1 1.
= =
− − −

66 2 Algebraic Graph Theory and Cooperative Control Consensus
The maximum eigenvalue of a stochastic matrix is 1. A matrix E 0 is row
(cid:31)
stochastic if and only if 1 is an eigenvector for the eigenvalue 1. −
Let square n×n matrix E 0 have all row sums equal to a constant c>0.
(cid:31)
Then [16]: −
1. ρ(E) c and is an eigenvalue of E with eigenvector 1.
=
2. If e >0 for all i, then λ<c for all eigenvalues λ≠c.
ii
Let E be the adjacency matrix of a graph G. Then:
1. λ =ρ(E)=c is simple if and only if E has a spanning tree. Then rank(E)=n−1.
1
2. If E has a spanning tree and if e >0 for all i, then λ =ρ(E)=c is the unique
ii 1
eigenvalue of maximum magnitude.
2.8.3 M-Matrices
M-matrices are important in the analysis of graphs due to the fact that the graph
Laplacian matrix L= D−A is an M-matrix. This section reproduces some results
from [13].
Given an m×n matrix A, a k×k minor of A is the determinant of a k×k matrix
obtained by deleting m–k rows and n–k columns of A. Define a subset I of {1,...,m}
with k elements and a subset J of {1,...n} with k elements. Write [A] for the k×k
I,J
minor of A corresponding to the rows with index in I and the columns with index
in J. If I = J then [A] is called a principal minor. Those principal minors corre-
I,J
sponding to matrices that are square upper-left submatrices of A are called leading
principal minors.
A square matrix n×n is an M-matrix if all its off-diagonal elements are non-
positive and all its principal minors are nonnegative. It is a nonsingular M-matrix if
all its principal minors are positive. Pictorially,
 + ≤0
M = 
≤0 + 
Any M-matrix can be written as E=sI−A for some s>0, A 0.
(cid:31)
The following properties of M-matrices from [13] are importa−nt for the analysis
of graphs. Define a Z-matrix as one having nonpositive off-diagonal elements. A
vector v is positive, v>0, if all its elements are positive.
Theorem 2.9 Properties of nonsingular M-matrices Let E∈Z be an n×n
matrix. Then the following conditions are equivalent:
1. E is a nonsingular M-matrix.
2. The leading principal minors of E are all positive.
3. The eigenvalues of E have positive real parts.
4. E-1 exists and has nonnegative elements.
5. There exist vectors w,v>0 such that Ev,ETw are both positive.
6. There exists a positive diagonal matrix S such that ES+SET is positive definite.

2.9 Lyapunov Functions for Cooperative Control on Graphs 67
Theorem 2.10 Properties of singular M-matrices Let E∈Z be an n×n matrix.
Then the following conditions are equivalent:
1. E is a singular M-matrix.
2. The leading principal minors of E are all nonnegative.
3. The eigenvalues of E have nonnegative real parts.
4. (B+E)−1 exists and is nonnegative for all diagonal matrices B having all diago-
nal elements positive.
5. There exist vectors w,v>0 such that Ev,ETw are both nonnegative.
6. There exists a nonnegative diagonal matrix S such that ES+SET is positive
semidefinite.
Theorem 2.11 Properties of irreducible M-matrices Let E=sI−A be an n×n
irreducible M-matrix, that is, A 0 and is irreducible. Then:
(cid:31)
−
1. E has rank n-1.
2. There exists a vector v>0 such that Ev=0.
3. Ex≥0 implies Ex=0.
4. Each principal submatrix of order less than n is a nonsingular M-matrix.
5. (B+E)−1 exists and is nonnegative for all nonnegative diagonal matrices B with
at least one positive element.
6. There exists a positive diagonal matrix P such that PE+ETP is positive semi-
definite, that is, matrix −E is Lyapunov stable.
The next results verify some other properties of irreducible M-matrices [21].
Though singular, it is very easy to turn irreducible matrices into nonsingular matri-
ces by adding positive diagonal terms.
Corollary 2.3 Let E∈Z be a singular but irreducible M-matrix. Then
E = E+diag{0,0,(cid:31),ε} is a nonsingular M-matrix for any ε>0. Moreover, -E
is stable.
Corollary 2.4 Let E∈Z be a singular but irreducible M-matrix. Let ε i 0 and
≥
at least one of them be positive. Then E = E+diag{ε} is a nonsingular M-matrix.
i
Moreover, -E is stable.
2.9 Lyapunov Functions for Cooperative Control
on Graphs
The properties of M-matrices are extremely important in constructing Lyapunov
functions for analysis of dynamic systems on graphs. It is seen in this section that
Lyapunov functions for cooperative control systems depend on the communication
graph topology, specifically through the graph Laplacian matrix L. That is, stability
analysis for cooperative control systems must take into account the connectivity
properties of the graph, i.e., the way in which the individual systems communicate.

68 2 Algebraic Graph Theory and Cooperative Control Consensus
Recall that a system x = Fx is marginally stable if there exist symmetric matri-
ces P>0,Q≥0 such that
FTP+PF =−Q (2.120)
This equation is called a Lyapunov equation for system x = Fx. Moreover, if this
equation holds with Q>0, then the system is AS.
Recall that then,
V = xTPx>0 (2.121)
is a Lyapunov function, since one has V = xT(PF+FTP)x≤0 for marginal stabil-
ity and V = xT(PF+FTP)x<0 for asymptotic stability.
Consider a graph with adjacency matrix A and Laplacian matrix L= D−A. If
the graph is strongly connected, then A is irreducible and so is L. Then, L is an ir-
reducible M-matrix. Then, according to Theorem 2.11 item 6, one has
PL+LTP=Q≥0 (2.122)
for a symmetric matrix P>0. This is a Lyapunov equation that verifies the mar-
ginal stability of the consensus system
x =−Lx (2.123)
Let B be a diagonal matrix with nonnegative diagonal entries and at least one of
them positive. Then from Theorem 2.11 item 5 L+B is a nonsingular M-matrix.
Now according to Theorem 2.9 item 6 there exists a symmetric matrix P>0 such
that
P(L+B)+(L+B)TP=Q>0 (2.124)
This Lyapunov equation verifies the asymptotic stability of the system
x(cid:28)=−(L+B)x. (2.125)
This system is of importance in subsequent chapters where we study cooperative
tracker design.
Dependence of Lyapunov Functions on Graph Topology The next results show
specifically how to construct matrices P in Lyapunov function (2.121) that sat-
isfy Lyapunov equations (2.122) and (2.124). Matrix P is seen to depend on graph
Laplacian matrix L. Thus, these results tie the Lyapunov analysis of cooperative
control systems directly to the graph topology. The first lemma constructs matrix P
for the singular irreducible case in (2.122).

2.9 Lyapunov Functions for Cooperative Control on Graphs 69
Lemma 2.3 Lyapunov Equation for Irreducible Laplacian Matrix [13] Let the
graph be strongly connected so that the Laplacian matrix L is an irreducible singu-
lar M-matrix. Let w =[p p (cid:31) p ]T >0 be the left eigenvector of L associated
1 1 2 N
with eigenvalue λ =0, i.e., wTL=0. Define
1 1
P=diag{p}
i
Then P>0 and Q= PL+LTP≥0.
We present two methods for constructing a matrix P for Lyapunov function
(2.121) that satisfies the Lyapunov equation (2.124). Both depend on the graph
topology through the Laplacian matrix.
Lemma 2.4 Lyapunov Equation for Nonsingular Graph Matrix L + B [13] Let
the graph be strongly connected so that the Laplacian matrix L is an irreducible
singular M-matrix. Let B be a diagonal matrix with nonnegative diagonal entries
and at least one of them positive. Then L+B is a nonsingular M-matrix. Define
q [q
1
, ,q
N
]T (L B)− 11
= ··· = +
−
P=diag{p}=diag{1/q}
i i
Then P>0 and Q= P(L+B)+(L+B)TP>0.
Lemma 2.5 Lyapunov Equation for Nonsingular Graph Matrix L + B [13] Let
the graph be strongly connected so that the Laplacian matrix L is an irreducible sin-
gular M-matrix. Let B be a diagonal matrix with nonnegative diagonal entries and
at least one of them positive. Then L+B is a nonsingular M-matrix. Let p,q>0
be vectors such that
(L+B)q>0, pT(L+B)>0
Define
P=diag{p /q}
i i
Then P>0 and Q= P(L+B)+(L+B)TP>0.
Note that vectors p,q>0 exist according to Theorem 2.9 item 5.
It is seen from these results that Lyapunov functions for studying the stability
properties of cooperative control protocols depend on the graph topology. There-
fore, a given cooperative control protocol may be stable on one graph topology
but not on another. This reveals the close interactions between the performance of
locally designed control protocols and the manner in which the agents are allowed
to communicate.
In subsequent chapters, we shall rely heavily on the results of this section to
analyze the stability of cooperative control systems on graphs.

70 2 Algebraic Graph Theory and Cooperative Control Consensus
2.10 Conclusions and Setting for the Subsequent
Chapters
This chapter has roughly followed the development of cooperative control results
in the early literature since the first papers [7, 9, 10, 16, 22]. To understand the
relationships between the communication graph topology and the local design of
distributed feedback control protocols, it was natural to study first-order systems
and then second-order systems. Early applications were made to formation control
[13, 14, 16, 18]. These studies brought an understanding of the limitations and cave-
ats imposed by the graph communication restrictions and opened the way for many
well-known results from systems theory to be extended to the case of multi-agent
systems on graphs.
The relations discovered between the communication graph topology and the
design of distributed control protocols have resulted in new design techniques for
cooperative feedback control. New intriguing interactions have been discovered be-
tween graph topology and local control protocol design that reveal the richness of
the study of cooperative control on graphs, where new phenomena are seen that do
not occur in control of single-agent systems.
It has been seen that Lyapunov functions for studying the stability properties of
cooperative control protocols depend on the graph topology. In the remainder of
the book, we explore these relationships for optimal design and adaptive control
on graphs.
References
1. Brewer J (1978) Kronecker products and matrix calculus in system theory. IEEE Trans Cir-
cuits and Systems 25(9):772–781
2. Brogan WL (1990) Modern Control Theory, 3rd edn. Prentice-Hall, New Jersey
3. Diestel R (2000) Graph Theory. Springer-Verlag, New York
4. Fax JA, Murray RM (2004) Information flow and cooperative control of vehicle formations.
IEEE Trans Autom Control 49(9):1465–1476
5. Godsil C, Royle GF (2001) Algebraic Graph Theory. Springer-Verlag, New York
6. Horn RA, Johnson CR (1985) Matrix Analysis. Cambridge University Press, New York
7. Jadbabaie A, Lin J, Morse S (2003). Coordination of groups of mobile autonomous agents
using nearest neighbor rules. IEEE Trans Autom Control 48(6):988–1001
8. Lee D, Spong MW (2007) Stable flocking of multiple inertial agents on balanced graphs.
IEEE Trans Autom Control 52(8):1469–1475
9. Moreau L (2005) Stability of multiagent systems with time-dependent communication links.
IEEE Trans Autom Control 50(2):169–182
10. Olfati-Saber R, Murray RM (2004) Consensus problems in networks of agents with switch-
ing topology and time-delays. IEEE Trans Autom Control 49(9):1520–1533
11. Olfati-Saber R, Fax JA, Murray RM (2007) Consensus and cooperation in networked multi-
agent systems. Proc IEEE 95(1):215–233
12. Olshevsky A, Tsitsiklis JN (2009) Convergence speed in distributed consensus and averag-
ing. SIAM J Control Optim 48(1):33–55

References 71
13. Qu Z (2009) Cooperative Control of Dynamical Systems: Applications to Autonomous
Vehicles. Springer-Verlag, London
14. Ren W (2007) Consensus strategies for cooperative control of vehicle formations. IET Con-
trol Theor Appl 1(2):505–512
15. Ren W, Beard RW (2005) Consensus seeking in multiagent systems under dynamically
changing interaction topologies. IEEE Trans Autom Control 50(5):655–661
16. Ren W, Beard RW (2008) Distributed Consensus in Multi-Vehicle Cooperative Control
Springer-Verlag, London
17. Ren W, Beard R, Atkins E (2005) A survey of consensus problems in multi-agent coordina-
tion. In: Proc. Amer. Control Conf., Portland, OR, pp. 1859–1864
18. Ren W, Atkins E (2007) Distributed multi-vehicle coordinated control via local information
exchange. Int J Robust Nonlinear Control 17(10–11):1002–1033
19. Reynolds CW (1987) Flocks, herds, and schools: A distributed behavior model. Comput
Graphics 21(4):25–34
20. Shoham Y, Leyton-Brown K (2009) Multiagent Systems. Cambridge University Press, New
York
21. Taussky O (1949) A recurring theorem on determinants. Am Math Mon 56(10):672–676
22. Tsitsiklis J, Bertsekas D, Athans M (1986) Distributed asynchronous deterministic and sto-
chastic gradient optimization algorithms. IEEE Trans Autom Control 31(9):803–812
23. Wu CW (2007) Synchronization in Complex Networks of Nonlinear Dynamical Systems.
World Scientific, Singapore
24. Xie G, Wang L (2007) Consensus control for a class of networks of dynamic agents. Int J
Robust Nonlinear Control 17(10–11):941–959

Part I
Local Optimal Design for Cooperative
Control in Multi-Agent Systems on Graphs
Cooperative control studies the dynamics of multi-agent dynamical systems linked
to each other by a communication graph. The objective of cooperative control is
to devise control protocols for the individual agents that guarantee synchronized
behavior of the states of all the agents in some prescribed sense. In cooperative
systems, any control protocol must be distributed in the sense that it respects the
prescribed graph topology; that is, the control protocol for each agent is allowed to
depend only on information about that agent and its neighbors in the graph.
In Part I of the book, we will study local and global optimal control for coopera-
tive multi-agent systems linked to each other by a communication graph. In Chap. 3,
we study continuous-time systems, and we shall see that local optimal design at each
agent guarantees global synchronization of all agents to the same state values on any
suitably connected digraph. Chapter 4 considers discrete-time systems and shows
that an extra condition relating the local agent dynamics and the graph topology
must be satisfied to guarantee global synchronization using local optimal design.
In cooperative control systems on graphs, it turns out that local optimality for
each agent and global optimality for all the agents are not the same. The relations
between stability and optimality are well understood for single-agent systems.
However, there are more intriguing relations between stability and optimality in
cooperative control than which appear in the single-agent case, since local stability
and global team stability are not the same, and local agent optimality and global
team optimality are not the same. New phenomena appear that are not present for
single-agent systems. Moreover, throughout everything the synchronization of the
states of all agents must be guaranteed.
A common problem in optimal decentralized control is that global optimization
problems generally require global information from all the agents, which is not
available to distributed controllers. In Chap. 5, we shall see that globally optimal
controls of distributed form may not exist on a given graph. To obtain globally opti-
mal performance using distributed protocols that only depend on local agent infor-
mation in the graph, the global performance index must be selected to depend on the
graph properties in a certain way, specifically, through the graph Laplacian matrix.
In Chap. 6, we will define a different sort of global optimality for which distrib-
uted control solutions always exist on suitably connected graphs. There, we study
multi-agent graphical games and show that if each agent optimizes its own local
performance index, a Nash equilibrium is obtained.

Chapter 3
Riccati Design for Synchronization
of Continuous-Time Systems
This chapter studies cooperative tracking control of multi-agent dynamical systems
interconnected by a fixed communication graph topology. Each agent or node is
mathematically modeled by identical continuous linear time-invariant (LTI) sys-
tems, which includes the single-integrator and double-integrator as special cases.
The communication network among the agents is described by a directed graph.
A command generator or leader node generates the desired tracking trajectory to
which all agents should synchronize. Only a few nodes are aware of information
from the leader node. A locally optimal Riccati design approach is introduced here
to synthesize the distributed cooperative control protocols. A framework for coop-
erative tracking control is proposed, including full state feedback control protocols,
observer design, and dynamic output regulator control. The classical system theory
notion of duality is extended to networked cooperative systems on graphs. It is
shown that the local Riccati design method guarantees synchronization of multi-
agent systems regardless of graph topology, as long as certain connectivity prop-
erties hold. This is formalized through the notion of synchronization region. It is
shown that the Riccati design method yields unbounded synchronization regions
and so achieves synchronization on arbitrary digraphs containing a spanning tree.
The results in this chapter were first published in [21].
3.1 Duality, Stability, and Optimality for Cooperative Control
In system theory, the relations between state variable feedback (SVFB) design, ob-
server design, and output regulator design are well known and provide a beautiful
overall theory that reveals deep structural relations for dynamical systems in terms
of duality theory, the separation principle, and other well-developed notions. In
intercommunicating cooperative control systems, however, the design of feedback
control protocols is complicated by the fact that the communication graph topol-
ogy can severely restrict what can be accomplished by using distributed feedback
F. L. Lewis et al., Cooperative Control of Multi-Agent Systems, 75
Communications and Control Engineering, DOI 10.1007/978-1-4471-5574-4_3,
© Springer-Verlag London 2014

76 3 Riccati Design for Synchronization of Continuous-Time Systems
control protocols, where the control policy of each agent is allowed to depend only
on its own information and local information available from its neighbors in the
graph. In this chapter we show that ideas of state feedback, observer design, and
output regulator design can be extended to the case of cooperative control on graphs
naturally by using locally optimal design in terms of local Riccati equations.
The relations between stability and optimality have long been debated in the
community and are now for the most part understood for single-agent systems.
However, relations of stability and optimality in multi-agent cooperative control
systems are only now beginning to be clarified. There are more intriguing relations
between stability and optimality in cooperative control than those that appear in the
single-agent case, since local stability and global team stability are not the same,
and local optimality and global team optimality are not the same.
In this chapter we discuss the design of cooperative control protocols that are
distributed, in the sense that each agent is allowed to use only information from
itself and its neighbors in the prescribed communication graph topology. The objec-
tive is for the states of all agents to synchronize to the state of a leader node, which
can be viewed as a command generator exosystem that generates a desired trajec-
tory. Only a few agents have access to information from the leader node. First we
consider the case of cooperative control using full SVFB, then cooperative observer
design in the case of output feedback (OPFB) or incomplete state measurements,
later cooperative output regulator protocol design.
In Sect. 3.2 we assume that the full state of each agent is available for feed-
back control design by itself and its neighbors in the graph. Locally optimal design
in terms of solving local Riccati equations is shown to guarantee synchronization
on arbitrary graph topologies that have a spanning tree. The idea of synchroniza-
tion region is given in Sect. 3.3. In Sect. 3.4 we design cooperative state observ-
ers based on OPFB, or reduced state information. A duality theory for cooperative
control systems on graphs is given in Sect. 3.5, and it involves the reverse graph. In
Sect. 3.6 we show three methods for designing cooperative dynamic regulators that
guarantee synchronization using only OPFB. These three methods depend on differ-
ent methods of exchanging information between neighbors in the graph.
3.2 State Feedback Design of Cooperative Control Protocols
In this section we design cooperative controllers using SVFB, assuming that the
full state of each agent is available for feedback control design by itself and its
neighbors in the communication graph. We require that any control protocol be
distributed in the sense that the control for agent i depends only on its own informa-
tion and that from its neighbors in the graph. It is shown that locally optimal design
in terms of a local Riccati equation, along with selection of a suitable distributed
control protocol, guarantees synchronization on arbitrary communication graphs
that have a spanning tree.

3.2   State Feedback Design of Cooperative Control Protocols  77
3.2.1   Synchronization of Multi-Agent Systems on Graphs
Much attention was paid early on in the cooperative control literature to the leader-
less consensus problem of single-integrator and double-integrator dynamics [10],
[15], [17]. Under proper selection of a ‘local neighborhood voting protocol’, it was
shown that if the graph has a spanning tree all nodes reach a consensus value that is
a weighted average of the initial conditions of the agent dynamics. In this chapter,
we shall study the more general case where each agent has dynamics of a continu-
ous LTI system. LTI systems form an important class of systems; they include the
single-integrator, double-integrator, and higher-order-integrator dynamics as spe-
cial cases. A large class of engineering systems can be modeled by LTI systems,
such as mechanical systems (e.g., mass–spring–damper systems), electrical systems
(e.g., RLC circuits, op-amp circuits), and electromechanical systems (e.g., arma-
ture-controlled direct current servomotor with a load) [1], [16].
We call the case where consensus is sought among agents when there is no leader
node the cooperative regulator problem. Here, we consider the cooperative track-
ing problem, where there are N identical follower agents or nodes and one leader
node. Each follower node i has identical dynamics and is modeled by an LTI system

|     | x(cid:28) | = Ax +Bu | , y =Cx, | i∈ | (3.1) |
| --- | --------- | -------- | -------- | --- | ----- |
|     | i         | i        | i i      | i   |       |
where  x n is the state,  u m is the input,  y p is the measured out-
| i R |     | i   | R   | i R |     |
| --- | --- | --- | --- | --- | --- |
| ∈   |     | ∈   |     | ∈   |     |
put, and   ={1,2,…,N}. The triple ( A, B, C) is assumed to be stabilizable and
detectable. These follower nodes can communicate in a certain way, and the
communication network is represented by a graph  ,  with N nodes
G ={V E}
 ={v,v ,…,v }, and a set of edges or arcs E ⊂V×V. Let the associated adjacen-
1 2 N
cy matrix be  [a ] N N, where  a 0 is the weight for edge (v , v ).
|     | ij  | R × | ij  |     | j i |
| --- | --- | --- | --- | --- | --- |
| A=  | ∈   |     | ≥   |     |     |
If there is an edge from node j to node i (i.e., (v j ,v i ) ),  a ij >0. This means
∈E
that node j is a neighbor of node i, and node i can get information from node j. The
neighbor set of node i is denoted as N ={j|a >0}. We assume there is no self-
|     |     |     | i ij |     |     |
| --- | --- | --- | ---- | --- | --- |
loop, i.e., a =0.
ii
The dynamics of a leader or control node, labeled 0, is given by

|     |     | x  | = Ax , y =Cx | ,   |     |
| --- | --- | --- | ------------ | --- | --- |
(3.2)
|     |     | 0   | 0 0 | 0   |     |
| --- | --- | --- | --- | --- | --- |
where  x n is the state and  y p is the measured output. The leader node
| 0 R |     |     | 0 R |     |     |
| --- | --- | --- | --- | --- | --- |
| ∈   |     |     | ∈   |     |     |
can be considered as a command generator exosystem that generates the desired tar-
get trajectory. It is an autonomous system and is not affected by any follower node.
The objective of the cooperative tracking problem is to design local distribut-
ed controllers  u  for all follower nodes i ( i ), such that all follower nodes
| i   |     |     | ∀ ∈N |     |     |
| --- | --- | --- | ---- | --- | --- |
track the state trajectory of the leader node, i.e., lim (x(t)−x (t))=0, ∀i∈.
t→∞ i 0
Then we say that the states of all agents synchronize to the state of the command
generator.

78 3 Riccati Design for Synchronization of Continuous-Time Systems
F ig. 3.1 Graph topologies
Ieader
discussed in Remark 3.2
Remark 3.1 Though the leader dynamics (3.2) is autonomous and has no control
input, it can generate a large class of useful command trajectories. The interesting
cases are when matrix A is not stable. The types of trajectories that can be generated
by the leader include unit step (position command), the ramp (useful in velocity
tracking systems, e.g., satellite antenna pointing), sinusoidal waveforms (useful,
e.g., in hard-disk drive control), and more. In this chapter, A can be either stable,
marginally stable, or even unstable, as long as ( A, B) is stabilizable. ▋
Define the augmented graph as , , where  ={v ,v,…,v } is the node
G ={V E} 0 1 N
set, including the leader node and all follower nodes, and is the edge
E ⊆V ×V
set. Note that . For the cooperative tracking problem we need the following
E ⊂E
assumption on the graph topology.
Assumption 3.1 The augmented graph contains a spanning tree with the root
G
node being the leader node. In other words, there is a directed path (not necessarily
unique) from the leader node to every follower node.
Assumption 3.1 is a necessary condition for solving the cooperative tracking prob-
lem. This is illustrated in the following remark in an intuitive way.
Remark 3.2 Suppose Assumption 3.1 does not hold and there is a set of k
(1≤k < N) nodes in graph , i.e., S ={n,n ,…,n } and S ⊂ , which do not
G k 1 2 k k
have directed paths from the leader node 0. This further implies that the set of nodes
S k do not have access to information of the rest of the nodes S k ={0,N}\S k . It is
obvious that there must exist some node (nodes) in the set S k, which is (are) either
isolated (i.e., isolated single node or isolated subgroup), or has an edge (have edges)
to at least one node in S . These cases are depicted in Fig. 3.1. Obviously, in these
k
cases, synchronization to the leader node cannot be achieved. ▋
Remark 3.3 Assumption 3.1 includes the following classes of graph topologies
(see Fig. 3.2) as special cases.
a. Graph is strongly connected and at least one follower node in graph can get
G G
information from the leader node [4], [5].
b. Graph contains a spanning tree and at least the root node can get access to the
G
leader node [14], [21].

3.2   State Feedback Design of Cooperative Control Protocols  79
|   0 | 1   | 2 0 | 1   | 2   |
| --- | --- | --- | --- | --- |
| 5   | 4   | 3 5 | 43  |     |
| a   |     | b   |     |     |
| 0   | 1   | 2 0 | 1   | 2   |
| 5   | 4   | 3 5 | 43  |     |
| c   |     | d   |     |     |
|     | 0   | 1   | 2   |     |
|     | 5   | 43  |     |     |
e
Fig. 3.2  Five classes of graph topologies described in Remark 3.3
c. The augmented graph   is itself a spanning tree with the root being the leader
G
node [3].
| d. The augmented graph  |  has a hierarchical structure [6]. |     |     |     |
| ----------------------- | ---------------------------------- | --- | --- | --- |
G
e. The augmented graph   has a spanning tree, but graph   is disconnected and
|     | G   |     | G   |     |
| --- | --- | --- | --- | --- |
each separated subgroup either is a single node or contains a spanning tree.  ▋
The statement that a graph is a spanning tree (e.g., Fig. 3.2 (c)) is different from the
statement that a graph has (or contains) a spanning tree (e.g., Fig. 3.2 (a–e)). The
former is a special case of the latter. A graph is a spanning tree if it has a spanning
tree, and each node has exactly one parent node, except for the root node which does
not have a parent node.
3.2.2   Cooperative SVFB Control
In this section, we assume that full state variable of each node is measurable, and
design a cooperative SVFB control law of distributed form using a Riccati design
approach [13]. This is the case C = I in (3.1). The case when C I  and the meas-
(cid:31)=
ured output only contains reduced state information is addressed in Sects. 3.4–3.6.

80 3  Riccati Design for Synchronization of Continuous-Time Systems
We assume that the leader node can only be observed by a small subset of the
follower nodes. This is often the case in practice when follower nodes are sparsely
populated and limited sensing ability is taken into account. If node i observes the
leader, an edge (v ,v ) is said to exist with a weight g >0. The weights g  >ha0v.e
|     |     | 0   | i   |     |     |     | i   |     | i   |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
been called pinning gains in [20] and if g >0. then node i is said to be pinned to
i
the leader.
To make the controller fully distributed, the control law of each agent must re-
spect the graph topology and can only use the local neighborhood information of
that agent. Define the neighborhood tracking error of node i as [11]
|     |     |     |      | N   |            |     |      |     |       |
| --- | --- | --- | ---- | --- | ---------- | --- | ---- | --- | ----- |
|     |     |     | ε=∑a |     | (x −x)+g(x |     | −x). |     | (3.3) |
|     |     |     | i    | ij  | j i        | i 0 | i    |     |       |
j=1
This can also be written in the form

|     |     |     |       |       |  ∑N | a x  | +gx   |     |       |
| --- | --- | --- | ----- | ----- | ---- | ---- | ------ | --- | ----- |
|     |     |     |       |       |      | ij   | j i 0 |     |       |
|     |     |     | ε=−(d | +g)x | −    | j=1  |        |     | (3.4) |
|     |     |     | i     | i i   | i    |      |        |     |       |
|     |     |     |       |       |     | d +g |       |     |       |
|     |     |     |       |       |     | i    | i     |     |       |
|     | d   | N a |       |       |      |      |        |     |       |
w he r e   i j 1 i j   is   t h e  i n -d e gr e e   o f   n o d e   i .  W h i le   (3 . 3 )   ca n  b e  i n t e r p r e t e d   as
=  =of
a  w e i g h te d  sum   d i ff e r e n c e s  b e tw e e n   t h e   s ta t e s   of  n o d e  i   a n d  i ts  n e i g h b o r s ,   ( 3 .4 )
(cid:31)
describes the difference between the state of node i and the weighted average center
of its neighbors’ states.
Consider a static SVFB control protocol for each node i , given as
∈N

|     |     |     |     |     | u i cKε | i   |     |     | (3.5) |
| --- | --- | --- | --- | --- | ------- | --- | --- | --- | ----- |
=
with coupling gain  c>0 and feedback gain matrix K ∈m×n. These controllers
are distributed in the sense that they are implemented at each node using only the
neighborhood tracking error information  ε i. The task is to find suitable c and K
such that all agents synchronize to the leader node for the given graph topology.
The closed-loop system of node i is
|     |     |             |           |    | N    |        |        |     |     |
| --- | --- | ----------- | --------- | --- | ---- | ------ | ------- | --- | --- |
|     |     |             | = Ax +cBK | ∑a  | (x   | −x )+g | (x −x ) | .   |     |
|     |     | x(cid:31) i |           |    |      |        |        |     |     |
|     |     |             | i         |    | ij j | i      | i 0 i  |     |     |
j=1
For ease of analysis, write the overall global closed-loop dynamics as
|     |     | =(I | ⊗A−c(L+G)⊗BK)x+(c(L+G)⊗BK)x |     |     |     |     |     |     |
| --- | --- | --- | --------------------------- | --- | --- | --- | --- | --- | --- |
|     |     | x  |                             |     |     |     |     | ,   |     |
|     |     | N   |                             |     |     |     |     | 0   |     |
)∈nN is the columnwise concatenation
| where the global state x=col(x,x |     |     |     |     | ,…,x |     |     |     |     |
| -------------------------------- | --- | --- | --- | --- | ---- | --- | --- | --- | --- |
|                                  |     |     |     | 1 2 | N    |     |     |     |     |
of local state vectors x,…,x , and  x =col(x ,x ,…,x )∈nN. The Kronecker
|             |     |                            | 1   | N   | 0   | 0                 | 0 0 |     |       |
| ----------- | --- | -------------------------- | --- | --- | --- | ----------------- | --- | --- | ----- |
|             |     | . The identity matrix is I |     |     |     | N N  and G=diag(g |     |     | ,…,g  |
| product is  |     |                            |     |     | N   | R ×               |     | ,g  | ) is  |
|             | ⊗   |                            |     |     | ∈   |                   |     | 1 2 | N     |
the diagonal matrix of pinning gains which describes the connections between the
leader node and follower nodes. The Laplacian matrix associated with graph   is
G

3.2   State Feedback Design of Cooperative Control Protocols  81
defined by L=[l ]= D−A, with D=diag(d ,d ,…,d ) the diagonal matrix of
ij
|     |     |     | 1 2 | N   |     |
| --- | --- | --- | --- | --- | --- |
in-degrees. It is apparent that
|     |     | a          | ij , j    | i,  |     |
| --- | --- | ---------- | --------- | --- | --- |
|     |     | l −        | (cid:29)= |     |     |
|     |     | ij = N     | a , j     | i.  |     |
|     |     | k 1        | ik        |     |     |
|     |     | (cid:31) = | =         |     |     |
(cid:30)
Define the global system and control input matrices as
|     |     | A = I ⊗A−c(L+G)⊗BK, |     |     |     |
| --- | --- | ------------------- | --- | --- | --- |
|     |     | c N                 |     |     |     |
|     |     | B =c(L+G)⊗BK.       |     |     |     |
c
Matrix A c reflects the local agent closed-loop matrix A BK as modified on the
| graph structure L | G. Note that the graph structure L + G appears on the left-hand  |     |     | −   |     |
| ----------------- | ---------------------------------------------------------------- | --- | --- | --- | --- |
+
side of the Kronecker product, while the local state information appears on the right.
Denote the disagreement error with respect to the leader for each node as
| δ = x -x . Define the global disagreement vector [15] as |     |     |     |     |     |
| -------------------------------------------------------- | --- | --- | --- | --- | --- |
i i 0

∈(cid:25)nN.
|     | δ=col(δ,δ | ,…,δ | )= x-x |     | (3.6) |
| --- | --------- | ---- | ------ | --- | ----- |
|     |           | 1 2  | N      | 0   |       |
Then the cooperative tracking problem is solved if lim δ(t)=0. The global disa-
t→∞
greement error dynamics is given by


|     |     | δ = x-x | = Aδ. |     | (3.7) |
| --- | --- | --------- | ----- | --- | ----- |
|     |     |           | 0 c   |     |       |
Note that the disagreement error information δ = x -x  is not available to node i
|     |     |     | i   | i 0 |     |
| --- | --- | --- | --- | --- | --- |
unless it is pinned to the leader node (that is, g i 0), whereas the local neighbor-
(cid:31)=
hood tracking error (3.3) is known to each node i.
Before moving on, we need the following lemmas. In these lemmas, the nota-
tions A and  a  stand for a general matrix A and its entries, and are not related to
ij
the system matrix A or the graph adjacency matrix entries a .
ij
Lemma 3.1 Geršgorin Circle Criterion [9] Let a matrix A [a ] R n n. Then
|     |     |     |     | = ij ∈ | ×   |
| --- | --- | --- | --- | ------ | --- |
all eigenvalues of A reside in the union of the n disks
|                               | n                 |         | n       |        |     |
| ----------------------------- | ----------------- | --------- | ------- | -------- | --- |
|                               |                  | λ∈C |λ-a | |≤ ∑    | |a |.   |     |
|                               |                   |           | ii      | ij       |     |
|                               |                   |         |         |        |     |
|                               | i=1               |           | j=1;j≠i |          |     |
| Lemma 3.2 [18] Let a matrix A |                   | [a ]      | n n and |          |     |
|                               |                   | = ij      | ∈ R ×   |          |     |
|                               |                 |           | n       |        |     |
|                               | J =i∈{1,2,…,n}|a |           | |> ∑    | |a |≠∅. |     |
|                               |                 |           | ii      | ij     |     |
j=1;j≠i
If for each  i / J, there is a sequence of nonzero elements of A of the form
∈
| a ,a ,…,a  with j | J. Then A is nonsingular. |     |     |     |     |
| ----------------- | ------------------------- | --- | --- | --- | --- |
| ii1 i1i2 iij      | ∈                         |     |     |     |     |

82 3 Riccati Design for Synchronization of Continuous-Time Systems
Lemma 3.3 Under Assumption 3.1, the matrix L G is nonsingular. Moreover,
+
all its eigenvalues are located in the open right-half plane.
Proof Under Assumption 3.1, at least one node in can get information directly
G
from the leader node, i.e., g >0 for at least one i . Without loss of gener-
i
∈N
ality, we assume there are two nodes r 1 and r 2 such that g r1 >0 and g r2 >0.
Since
∑N
l =0, l ≥0 and l ≤0,|l
|=∑N
|l |. Then for matrix L G,
j=1 ij ii ij ii j=1;j≠i ij +
|l
ii
+g
i
|≥∑N
j=1;j≠i
|l
ij
| for alli
∈N
and strict inequality holds for i
∈{
r
1
,r
2 }
.
Assumption 3.1 implies that, for any other node i which does not have direct access
to the leader node (i.e., i r i ,r 2 ), there must be a direct path either origi-
∈N \{ }
nated from node r or node r . According to Lemma 3.2, L G is nonsingu-
1 2 +
lar. By Geršgorin circle criterion, all eigenvalues of L G lie within the union
+
{λ∈(cid:24)|Re(λ)>0}∪{0}. The fact that L G is nonsingular further implies all its
+
eigenvalues are located in the open right-half plane. □
The next result (cf. [8]) provides a necessary and sufficient condition for asymptotic
stability of the disagreement error dynamics (3.7).
Lemma 3.4 Let λ (i ) be the eigenvalues of L G, which may or may not
i ∈N +
be distinct. Then system (3.7) is asymptotically stable if and only if all the matrices
A-cλBK, i=1,2,…,N (3.8)
i
are asymptotically stable.
Proof The zero state of system (3.7) is asymptotically stable if and only if A c is
Hurwitz, i.e., all eigenvalues of A c lie in the open left-half plane. There exists a
nonsingular matrix S R N × N, such that
∈
J (λ) 

n1 1

 J (λ) 
S-1(L+G)S = J =

n2 2

,
(cid:30)
 
 J (λ)
 nk k 
where n 1 + n 2 + ... + n k = N and J n 1 , J n 2 ,…, J n k are the Jordan blocks of sizes
n,n ,…,n . Note that the eigenvalues λ of L + G need not be distinct. Similarity
1 2 k i
transformation of matrix A c gives a block triangular matrix
A =(S⊗I )−1A (S⊗I )
c n c n
=(S⊗I )−1(I ⊗A−c(L+G)⊗BK)(S⊗I )
n N n
= I ⊗A−cJ⊗⊗BK. (3.9)
N
Denote the diagonal entries of J as {λ,λ,…,λ }, i.e., [λ,λ,…,λ ]=
1 2 N 1 2 N
[ (cid:23) λ (cid:22)1 , (cid:21) … (cid:22) , (cid:20) λ 1 ,…,λ (cid:23)k(cid:22) ,… (cid:21) , (cid:22) λ (cid:20)k ]. Since the eigenvalues of a block triangular matrix are the
n n
1 k

3.2 State Feedback Design of Cooperative Control Protocols 83
union of the sets of eigenvalues of the diagonal blocks, A is Hurwitz if and only
c
if all the diagonal entries A-cλBK (i=1,2,…,N) are Hurwitz. Hence under this
i
condition A c is Hurwitz. This completes the proof. □
If matrix A is stable, then even with a coupling gain of c = 0 all nodes synchronize
to the zero state. If the command generator matrix A is not stable (see Remark 3.1),
then it is inferred from Lemma 3.4 that all eigenvalues λ of L + G must be nonzero.
i
By Lemma 3.3, if the graph has a spanning tree with the leader as the root node, then
all eigenvalues λ of L + G have positive real parts. Then, proper design of c, K to
i
satisfy condition (3.8) guarantees synchronization.
Lemma 3.4 implies that an arbitrary SVFB control gain K that stabilizes the
single-agent dynamics A BK may fail to stabilize the global dynamics A c for
−
a prescribed graph structure. That is, though individual agents may have stable dy-
namics in isolation, when they are connected together by a communication graph,
their stability may be destroyed. This is illustrated in Example 3.1 in Sect. 3.3. Con-
dition (3.8) is difficult to guarantee and has been a stumbling block to the design
of distributed control protocols that guarantee synchronization on a given graph
topology.
3.2.3 Local Riccati Design of Synchronizing Protocols
Our objective now is to overcome the coupling between the local agent feedback
control design and the graph topological properties that is displayed in Lemma 3.4,
and to provide a design method for feedback matrix K in protocol (3.5) that is
independent of the graph topology. That is, we wish to decouple the design of the
control protocol from the graph properties, and show how to design a protocol that
guarantees synchronization on any directed graph with suitable properties.
The next result shows how to select SVFB control gain K to guarantee stability
on arbitrary digraphs satisfying Assumption 3.1 by using a local Riccati design ap-
proach [13] and a proper choice of the coupling gain c.
Theorem 3.1 Consider local distributed control protocols (3.5). Suppose (A, B) is
stabilizable and let design matrices Q R n × n and R R m × m be positive definite.
∈ ∈
Design the SVFB control gain K as
K = R-1BTP, (3.10)
where P is the unique positive definite solution of the control algebraic Riccati
equation (ARE)
0= ATP+PA+Q-PBR-1BTP. (3.11)
Then under Assumption 3.1, the global disagreement error dynamics (3.7) is asymp-
totically stable if the coupling gain satisfies

84 3  Riccati Design for Synchronization of Continuous-Time Systems

1
| c≥  |     |     | (3.12) |
| --- | --- | --- | ------ |
2min Re(λ)
|     | i∈ | i   |     |
| --- | --- | --- | --- |
with λ (i ) the eigenvalues of L G. Then, all agents synchronize to the
i
| ∈N  | +   |     |     |
| --- | --- | --- | --- |
leader node state trajectory.
Proof Let the eigenvalues of L G be λ =α + jβ , where α ,β R. Then by
|     | i   | i i i i |     |
| --- | --- | ------- | --- |
| +   |     | ∈       |     |
Lemma 3.3, α i >0, ∀i∈. Considering (3.10) and (3.11), straightforward com-
putation gives the Lyapunov equation
| (A-cλBK)∗P+P(A-cλBK)=-Q-(2cα |     | -1)KTRK, |     |
| ---------------------------- | --- | -------- | --- |
| i                            | i   | i        |     |
where the superscript * denotes the conjugate transpose of a complex matrix. Since
P >0 and Q>0, by Lyapunov theory [2] matrix A-cλ BK is Hurwitz if c 1/2α i,
|     |     | i   | ≥   |
| --- | --- | --- | --- |
∀i∈. Then Lemma 3.4 completes the proof.  □
The importance of this result is that it decouples the local SVFB gain design at each
agent from the details of the interconnecting communication graph structure. The
SVFB gain is designed using the control ARE (3.11), and then the graph topology
comes into the choice of the coupling gain c through condition (3.12).
Note that the SVFB gain in Theorem 3.1 is the optimal gain [13] that minimizes
the local performance index
  1 ∞
|     | ( xTQx +uTRu | )   |        |
| --- | ------------ | --- | ------ |
| J = | ∫            |  dt | (3.13) |
| i 2 | i i i        | i   |        |
0
subject to the local agent dynamics (3.1). Therefore, the theorem shows that locally
optimal SVFB control design by each agent guarantees the synchronization of all
agents on any graph that has a spanning tree with the leader as the root node.
The locally optimal design method in Theorem 3.1 is scalable, since it only de-
pends on the local agent dynamics, which have state space of dimension n, and does
not depend on the size N of the graph.
It is stressed that the locally optimal design that minimizes the local agent per-
formance index (3.13) does not guarantee the global optimality of the motion of all
the agents as a team. Globally optimal design for multi-agent systems is discussed
in Chap. 5.
3.3   Region of Synchronization
From Lemma 3.4, one sees that without using Riccati design, one can still find
suitable coupling gain c and control gain K such that asymptotic tracking can be
achieved by determining a SVFB gain that stabilizes (3.8) for all eigenvalues λ of
i
L G. The Riccati design in Theorem 3.1 decouples the design of the local agent
+

3.3 Region of Synchronization 85
feedback protocols from the graph properties and so provides a simple way of find-
ing such a gain. This section shows another point of view of this issue by describing
the concept of synchronization region [7], [14]. This concept provides a natural
way to evaluate the performance of synchronization control laws by revealing how
synchronizability depends on structural parameters of the communication graph.
Definition 3.1 Synchronization Region Given system (A, B) and feedback
matrix K, the synchronization region is the region in the complex plane defined as
S={s∈(cid:24) A−sBK is Hurwitz}.
Our application of this definition is in regard to the distributed control protocol
(3.5). By Lemma 3.4 and Definition 3.1, synchronization is achieved if cλ fall
i
into the synchronization region for all i . Clearly, the synchronization region
∈N
depends on both the control matrix K and the coupling gain c. It is shown in [7]
that, for unsuitable choices of K the synchronization region may be disconnected. A
synchronization region that forms a connected unbounded right-half plane is a de-
sirable property of a consensus protocol [14], since, according to Lemma 3.3, such
a region contains all possible graph eigenvalues for appropriate choice of coupling
gain c. By Lemma 3.4, an unbounded synchronization region implies that the same
control gain K guarantees synchronization for any digraph containing a spanning
tree.
Corollary 3.1 For protocol (3.5) with the Riccati design-based control gain (3.10),
the synchronization region is unbounded. More specifically, a conservative estimate
for the synchronization region is S ={α+ jβ|α∈[1/2,∞),β∈(-∞,∞)}.
Proof Let s α jβ. Using the same development as in Theorem 3.1, we have
= +
(A sBK)∗ P P(A sBK) Q (2α 1)KTRK.
− + − =− − −
Since P >0,Q>0 and R>0,A sBK is Hurwitz if and only if
−
Q (2α 1)KTRK<0. A sufficient condition is α 1/2. This completes the
− − − ≥
proof. □
The following example shows that a random stabilizing control gain K may yield a
bounded synchronization region, while the Riccati design-based control gain (3.10)
renders an unbounded synchronization region.
Example 3.1 Consider the agent dynamics (3.1) with matrices [14]
-2 -1 1
A= ,B= .
 2 1 0
The feedback gain K [0.5,0.5] stabilizes A−BK. The synchronization region
=
for this gain matrix is S x jy x<2;x 1 x 2 1 x y2>0 , which
1 = + 2 − 2 − − 8
is shadowed in Fig. 3.3.
If, for a given graph, the (cid:31) eigenvalu(cid:30) (cid:30) es of L + (cid:29) G fal (cid:28) l wit (cid:29) hin the (cid:28) region (cid:27) S , syn-
(cid:30) 1
chronization occurs. However, this is a severe restriction on the allowable forms of

86 3 Riccati Design for Synchronization of Continuous-Time Systems
1
0.8
0.6
0.4
0.2
0
−0.2
−0.4
−0.6
−0.8
−1
−0.5 0 0.5 1 1.5 2 2.5
x
communication between the agents. Note in particular that if the communication
graph is a cycle, the eigenvalues of L are uniformly distributed about a circle in the
right-half plane (Chap. 2), and so would in likelihood not fall within this synchro-
nization region.
Now consider the Riccati design-based feedback gain K [1.544,1.8901]
=
provided by Theorem 3.1 with Q I and R 1. The synchronization region is
2
= =
S x jy 1 1.544x>0;(5.331x 1.5473)y2 2.2362(1 1.54x)2x>0 ,
2
= + + − + +
which is unbounded as shadowed in Fig. 3.4. Lemma 4 in [14] is used in computing
(cid:31) (cid:30) (cid:29)
the synchroniz(cid:30)ation region. Note that the region indicated in Fig. 3.4 is the actual
synchronization region determined from solving the inequality given above. The re-
gion given by Corollary 3.1 is the region {x+ jy|x∈[1/2,∞),y∈(-∞,∞)} which
is a conservative estimate of S .
2
3.4 Cooperative Observer Design
In Sect. 3.2, a cooperative tracking controller is designed by assuming that the full
state information of all nodes can be measured. Unfortunately, nature seldom coop-
erates so eagerly. In practice, only limited output information can be measured. In
this case, for single-agent systems it is well understood how to design a dynamical
output regulator that stabilizes a system or enforces a desired tracking behavior.
Some of these regulator designs are based on state observers [12], which take the
available output measurements and provide estimates of the full system state. In
this section, we investigate cooperative observer design for networked multi-agent
systems, where the graph topology interacts with the local agent observer design
[21]. In Sect. 3.6 we show how to use the state feedback protocols in Sect. 3.2 along
with these cooperative observers to design dynamic regulators that guarantee syn-
chronization using only the available output measurements.
y
F ig. 3.3 Bounded synchro-
nization region for a random
stabilizing SVFB gain
Synchronizaiton Region

| 3.4   Cooperative Observer Design  |     |     |     |     | 87  |
| ---------------------------------- | --- | --- | --- | --- | --- |
| F ig. 3.4  Unbounded               | 20  |     |     |     |     |
synchronization region for
| Riccati-based SVFB gain | 15  |     |     |     |     |
| ----------------------- | --- | --- | --- | --- | --- |
10
5
Synchronizaiton Region
y 0
−5
−10
−15
−20
|     | −0.2 | 0   | 0.2 0.29 | 0.6 | 0.8 1 |
| --- | ---- | --- | -------- | --- | ----- |
x
Consider system (3.1) for the i-th agent, that is

|     | x(cid:28) = Ax | +Bu, y =Cx, | i∈ |     | (3.14) |
| --- | -------------- | ----------- | --- | --- | ------ |
|     | i i            | i i         | i   |     |        |
Denote  x R n as the estimate of the state  x i,  y Cx i as the consequent esti-
| ˆ i ∈ |     |     | ˆ i = ˆ |     |     |
| ----- | --- | --- | ------- | --- | --- |
mate of the output y. Define the state estimation error x x x  and the output
|                    | i                |     | i   | i i |     |
| ------------------ | ---------------- | --- | --- | --- | --- |
|                    |                  |     | ˜ = | − ˆ |     |
| estimation error y | y y  for node i. |     |     |     |     |
˜ i = i − ˆ i
Standard observer design for a single system often uses the output estimation
error information y y y. Similarly, for cooperative observer design, taking the
˜ = − ˆ
graph topology into account, we define the neighborhood output estimation error
for node i as
|     | N   |              |               |     |        |
| --- | --- | ------------ | ------------- | --- | ------ |
|     | ζ   | a (y y )     | g (y y )      |     | (3.15) |
|     | i = | ij ˜ j − ˜ i | + i ˜ 0 − ˜ i |     |        |
(cid:31)= j 1
which depends on the output estimation errors of node i and its neighbors. The co-
operative observer for each node i (i ) is designed in the form
∈N
|     | xˆ(cid:28) | Axˆ   |       |     |        |
| --- | ---------- | ----- | ----- | --- | ------ |
|     |            | = +Bu | -cFζ, |     | (3.16) |
|     | i          | i i   | i     |     |        |
where  c>0 is the coupling gain and F n p is the observer gain. These ob-
R ×
∈
servers are completely distributed in the sense that each observer only requires its
own output estimation error information and that of its neighbors.
The cooperative observer design problem is to select the coupling gain c and the
observer gain F so that the state estimation errors  x x x iof all agents go to
|     |     |     | ˜ i = i − | ˆ   |     |
| --- | --- | --- | --------- | --- | --- |
zero.
Since the leader node 0 acts as a command generator, it is reasonable to assume
that the leader node knows its own state, i.e., x x  and y 0. Then the global
|     |     |     | 0 0   | 0   |     |
| --- | --- | --- | ----- | --- | --- |
|     |     |     | ˆ = ˜ | =   |     |
cooperative observer dynamics is

88 3  Riccati Design for Synchronization of Continuous-Time Systems
|     | xˆ(cid:31) | xˆ+(I             |     |     |     |
| --- | ---------- | ----------------- | --- | --- | --- |
|     | = A        | ⊗B)u+c[(L+G)⊗F]y, |     |     |     |
o N
where x col(x ,x ,... ,x ), y col(y ,y ,... ,y ), u col(u ,u ,... ,u )
|     | 1 2 | N   | 1 2 N | 1   | 2 N |
| --- | --- | --- | ----- | --- | --- |
| ˆ = | ˆ ˆ | ˆ = |       | =   |     |
and
|     |     | A = I ⊗A−c(L+G)⊗FC. |     |     |     |
| --- | --- | ------------------- | --- | --- | --- |
o N
 reflects the local agent observer matrix A FC as modified by the
Matrix  A
| o   |     |     | −   |     |     |
| --- | --- | --- | --- | --- | --- |
graph structure L G. Note that graph topology information appears on the left-
+
hand side of the Kronecker product while local agent information appears on the
right.
Let the global state estimation error be
|     |     | x(cid:30)= | x−x(cid:30). |     | (3.17) |
| --- | --- | ---------- | ------------ | --- | ------ |

Then straightforward computation gives the dynamics of the state estimation error
|     |     | (cid:31)x(cid:30) | (cid:31)x. |     |        |
| --- | --- | ----------------- | ---------- | --- | ------ |
|     |     |                   | = A        |     | (3.18) |
|     |     |                   | o          |     |        |
Now the task for cooperative observer design is to find a suitable coupling gain c
and observer gain F, such that the matrix A
 is Hurwitz. Then the state estimation
o
error goes to zero. The next result is dual to Lemma 3.4 and provides a necessary
and sufficient condition for asymptotical stability of the global cooperative observer
dynamics.
Lemma 3.5 Let λ (i ) be the eigenvalues of (L G). Then the state estima-
i
|     | ∈N  |     | +   |     |     |
| --- | --- | --- | --- | --- | --- |
tion error dynamics (3.18) is asymptotically stable if and only if all the matrices
|     |     | A−cλFC,∀i∈, |     |     | (3.19) |
| --- | --- | ------------ | --- | --- | ------ |
i
are Hurwitz, i.e., asymptotically stable.
| Proof See the proof of Lemma 3.4.  |     |     |     |     | □   |
| ---------------------------------- | --- | --- | --- | --- | --- |
If the command generator matrix A is not stable (see Remark 3.1), then it is inferred
from Lemma 3.5 that all eigenvalues λ of L + G must be nonzero. By Lemma 3.3,
i
if the graph has a spanning tree with the leader as the root node, then all eigenvalues
λ of L + G have positive real parts. Then, proper design of c, F to satisfy condition
i
(3.19) guarantees that all state estimation errors converge to zero using the coopera-
tive observers (3.16).
Lemma 3.5 shows how the graph topology interferes with the design of the local
agent observers. This is undesirable. We now wish to devise a design method that
decouples the local agent observer design from the graph properties.
Similar to Theorem 3.1, the next result shows how to select the observer gain
F to guarantee that (3.19) is satisfied on arbitrary digraphs satisfying Assumption
3.1 by using a local Riccati design approach [12] and proper choice of the coupling
gain c.

| 3.5   Duality for Cooperative Systems on Graphs  |     |     |     |     |     | 89  |
| ------------------------------------------------ | --- | --- | --- | --- | --- | --- |
Theorem 3.2 Suppose (A, C) is detectable and let design matrices Q n n and
R ×
| p p be positive definite. Design the observer gain F as |     |     |     |     | ∈   |     |
| ------------------------------------------------------- | --- | --- | --- | --- | --- | --- |
R R ×
∈
PCTR−1
|     |     |     | F = |     |     | (3.20) |
| --- | --- | --- | --- | --- | --- | ------ |
where P is the unique positive definite solution of the observer ARE
|     |     | 0= AP+PAT | +Q−PCTR−1CP. |     |     | (3.21) |
| --- | --- | --------- | ------------ | --- | --- | ------ |
Then the estimation error dynamics (3.18) are asymptotically stable if the coupling
gain satisfies
1
|           |                            |     | c≥   |       |     | (3.22) |
| --------- | -------------------------- | --- | ---- | ----- | --- | ------ |
|           |                            |     | 2min | Re(λ) |     |        |
|           |                            |     |      | i∈ i |     |        |
| with λ (i | ) be the eigenvalues of (L |     |      | G).   |     |        |
| i         | ∈N                         |     |      | +     |     |        |
Proof The development is the same as in Theorem 3.1. Except that here we have
|     | (A−cλFC)P+P(A−cλFC)* |     |     |          | −1)FRFT. |     |
| --- | -------------------- | --- | --- | -------- | -------- | --- |
|     |                      |     |     | =−Q−(2cα |          | □   |
|     |                      | i   | i   |          | i        |     |
The importance of this theorem is that it decouples the local observer gain design at
each agent from the details of the interconnecting communication graph structure.
The observer gain is designed using the observer ARE (3.21) [12], and then the graph
topology comes into the choice of the coupling gain c through condition (3.22).
The local Riccati design method in Theorem 3.2 is scalable, since it only de-
pends on the local agent dynamics, which have state space of dimension n, and does
not depend on the size N of the graph.
3.5   Duality for Cooperative Systems on Graphs
As is well known in classical control theory, controller design and observer de-
sign are dual problems [2]. One outcome of duality is that these two problems are
equivalent to the same algebraic problem. Formally, given systems (3.1) and (3.14),
which we denote as (A, B, C), the dual system is defined to be
|     |     |             | ATx +CTu, | BTx, |     |        |
| --- | --- | ----------- | --------- | ---- | --- | ------ |
|     |     | x(cid:31) = |           | y =  |     | (3.23) |
|     |     | i           | i         | i i  | i   |        |
which we denote as (AT,CT,BT). A standard result is that system (3.14) is reach-
able (which depends on the properties of the input-coupling pair (A, B)) if and only
if system (3.23) is detectable (which depends on the properties of the output-cou-
pling pair (AT,BT)). Moreover, replacing (A, B) in (3.11) by (AT,CT) results in
(3.21), so that the control ARE (3.11) is dual to the observer ARE (3.21). Therefore,

90 3 Riccati Design for Synchronization of Continuous-Time Systems
the observer gain F in Theorem 3.2 can be found by computing the SVFB gain K
in Theorem 3.1, with (A,B) replaced by (AT, CT) and then setting F KT [12].
=
Another remarkable insight provided by duality theory for standard single sys-
tems is that control design is dual to observer design and estimation if the time
is reversed. Thus, optimal control is fundamentally a backwards-in-time problem
[13], as captured by the idea of dynamic programming, which proceeds backwards
from a desired goal state. On the other hand, optimal estimation is fundamentally
a forwards-in-time problem [12]. A complete theory of duality is provided in the
theory of electric circuits, where such notions are formally captured.
Unfortunately, in inter-communicating cooperative multi-agent systems, the de-
sign of cooperative feedback control protocols and cooperative observers is compli-
cated by the fact that the communication graph topology can severely restrict what
can be accomplished by using distributed protocols, where the policy of each agent
is allowed to depend only on its own information and local information available
from its neighbors in the graph. Therefore, the theory of duality has not been fully
developed for cooperative control systems.
In this section, we extend the important concept of duality to networked coop-
erative linear systems. We show that cooperative SVFB controller design and coop-
erative observer design are also dual problems under suitable definitions. The next
definition captures the notion of time reversal in cooperative systems on graphs.
Definition 3.2 Reverse Digraph Given a digraph , the reverse digraph ′ is the
G
graph with the same nodes as digraph , and with the directions of all edges reversed.
G
Thus, if the adjacency matrix of digraph is [a ij ], then the adjacency ma-
trix of its reverse digraph ′ is T [a j G i ]. Th A is = means that the row sums in the
A =
reverse graph correspond to column sums in the original graph, so that the roles of
in-neighbors and out-neighbors are exchanged.
Lemma 3.6 If the digraph is balanced, then the transpose of its Laplacian matrix
G
L is the same as the Laplacian matrix L′ of its reverse digraph ′, i.e., LT = L′.
Theorem 3.3 Duality of cooperative systems on graphs Consider a networked
system of N identical linear dynamics (A,B,C) on a balanced communication
graph . Suppose the SVFB gain K stabilizes the synchronization error dynamics
(3.7). T G hen the observer gain KT stabilizes the state estimation error dynamics
(3.18) for a networked dual system of N identical linear dynamics (AT,CT,BT) on
the reverse graph ′.
Proof Consider the networked system with (A,B,C) and graph . Under SVFB
G
gain K, the synchronization error dynamics (3.7) is
δ(cid:28) =[I ⊗A-c(L+G)⊗BK]δ= Aδ. (3.24)
N c
For the networked dual system with (AT,CT,BT) and reverse graph ′, under the
observer gain KT, the state estimation error dynamics (3.18) is
(cid:31)x(cid:30) =(I ⊗AT)−c(L′ +G)⊗(KTBT)x(cid:31)= A′x(cid:31).
 N  o

3.6 Cooperative Dynamic Regulators for Synchronization 91
Since G diag(g ), it is follows that A′ =(A )T. This proves the duality. □
= i o c
The equivalence between these dual problems is summarized as follows
A↔ AT
B↔CT
C↔ BT
 ↔ ′
L↔ L′
Duality of SVFB control and OPFB control is shown in [19] for leaderless consen-
sus on the same graph. This is different from the duality presented in Theorem 3.3,
i.e., duality of SVFB control design and observer design for cooperative tracking
problems on reverse graphs. Theorem 3.3 extends the classical concept of duality in
control theory [2] to networked systems on graphs.
3.6 Cooperative Dynamic Regulators for Synchronization
One approach for the design of controllers based on reduced state or OPFB is to inte-
grate an observer with a state feedback controller. Then, the controller employs state
estimate information instead of actual measured state information. Since this state es-
timate information is generated by an observer, which is a dynamical system using
only system input and output information, this integrated controller is called a dynamic
OPFB regulator or tracker. The dynamics of the regulator are provided by the observer.
In this section, we propose three cooperative dynamic output regulators to solve
the cooperative tracking problem. The Riccati design-based control gain (3.10) and
Riccati design-based observer gain (3.20) or both are used in these three dynamic
OPFB tracking controllers, all of which yield unbounded synchronization regions.
This highlights the importance of local Riccati design approach in cooperative con-
trol of networked systems. It also highlights the increased richness of structure in-
herent in cooperative control on graphs, which admit three natural structures of
regulators instead of the single standard regulator based on SVFB and full observer
design in the single-system case.
The work in this section comes from [21]. Various papers have designed variants
of the three regulators described in this section, including [14].
3.6.1 Neighborhood Controller and Neighborhood Observer
Recall the full SVFB cooperative control protocol (3.5), that is, u cKε. Recall
i i
=
the neighborhood output estimation error (3.15) for node i, rewritten here as
N
ζ i a ij (y j y i ) g i (y 0 y i ). (3.25)
= ˜ − ˜ + ˜ − ˜
j 1
(cid:31)=

92 3  Riccati Design for Synchronization of Continuous-Time Systems
Define the neighborhood state estimation tracking error as
|     |     | εˆ  | ∑a  |             |           |      |        |
| --- | --- | --- | --- | ----------- | --------- | ---- | ------ |
|     |     | =   | (xˆ | j −xˆ i )+g | (xˆ 0 −xˆ | i ). | (3.26) |
|     |     | i   | ij  |             | i         |      |        |
j∈Ni
These two neighborhood errors represent the complete information available to
node i based on measured output information from itself and its neighbors in the
graph.
In the first regulator protocol, both controller and observer are designed using
this complete available neighborhood information. This cooperative regulator is de-
signed using OPFB as
|     |     |     | u      | cKε     | ,       |     | (3.27) |
| --- | --- | --- | ------ | ------- | ------- | --- | ------ |
|     |     |     |        | i = ˆ i |         |     |        |
|     |     |     | x i Ax | i Bu i  | cFζ i . |     | (3.28) |
|     |     |     | ˙ˆ = ˆ | +       | −       |     |        |

| Then, the closed-loop dynamics of node i (i |     |     |     |     | ) is |     |     |
| ------------------------------------------- | --- | --- | --- | --- | ---- | --- | --- |
∈N
|     |                |       |    |         |         |         |     |
| --- | -------------- | ----- | --- | ------- | ------- | -------- | --- |
|     | x(cid:31) = Ax | +cBK | ∑ a | (xˆ −xˆ | )+g (xˆ | −xˆ ) , |     |
|     | i              | i     |     | ij j i  | i       | 0 i      |     |
|     |                |       |    |         |         |         |     |
j∈Ni
|     |                  |     |     |                |                |                           |     |
| --- | ---------------- | --- | ---- | -------------- | -------------- | -------------------------- | --- |
|     | xˆ(cid:31) = Axˆ | +Bu | −cF | ∑ a (y(cid:30) | −y(cid:30) )+g | (y(cid:30) −y(cid:30) ) . |     |
|     | i                | i   | i    | ij             | j i            | i 0 i                      |     |
|     |                  |     |     |                |                |                           |     |
j∈Ni
Assume  x x  for the leader node. Considering the identity (L BK)x 0
| ˆ 0 | = 0 |     |     |     |     | ⊗   | 0 = |
| --- | --- | --- | --- | --- | --- | --- | --- |
which roots in the fact L1 =0, with 1  the N-vector of ones, the global closed-
|     |     | N   |     | N   |     |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- |
loop dynamics can be written as
|     | x  | =(I | ⊗A)x−c[(L+G)⊗BK](xˆ−x |     |     | ),  | (3.29) |
| --- | --- | --- | --------------------- | --- | --- | --- | ------ |
|     |     | N   |                       |     |     | 0   |        |
(cid:31)ˆ=[I
|     | x   | ⊗A−c(L+G)⊗FC]xˆ+c[(L+G)⊗F]y |     |     |     |     |     |
| --- | --- | --------------------------- | --- | --- | --- | --- | --- |
N
|     | =−c[(L+G)⊗BK](xˆ−x |     |     | ).  |     |     | (3.30) |
| --- | ------------------ | --- | --- | --- | --- | --- | ------ |
0
Theorem 3.4 Let (A, B, C) be stabilizable and detectable and the augmented
graph   has a spanning tree with the leader node as the root. Let the cooperative
dynamic OPFB tracking control law be (3.27) and (3.28). Design the SVFB gain K  G
and coupling gain c according to Theorem 3.1 and the observer gain F according to
Theorem 3.2. Then all nodes i=1,2,…,N  synchronize to the leader node 0 asymp-
totically and the state estimation error x in (3.17) approaches zero asymptotically.
˜
Proof Equation (3.29) can be written as
|     |     |     | x(cid:31)= A | x+B (x(cid:30)−x | ).  |     |     |
| --- | --- | --- | ------------ | ---------------- | --- | --- | --- |
|     |     |     | c            | c                | 0   |     |     |
Further computation gives
|     |     |     | δ (cid:31) = | Aδ+B | x(cid:30). |     |     |
| --- | --- | --- | ------------ | ---- | ---------- | --- | --- |
|     |     |     |              | c    | c          |     |     |

| 3.6   Cooperative Dynamic Regulators for Synchronization  |     |     |     |     |     | 93  |
| --------------------------------------------------------- | --- | --- | --- | --- | --- | --- |
The global state estimation error dynamics (3.18) is
|     | x x   | x [I A | c(L G) | FC]x | A x. |     |
| --- | ----- | ------ | ------ | ---- | ---- | --- |
|     | ˙˜    | ˙ˆ N   |        |      | o    |     |
|     | = ˙ − | = ⊗ −  | + ⊗    | ˜ =  | ˜    |     |
Then one has
|     |     |  δ (cid:31)  A     | B   δ      |     |     |     |
| --- | --- | --------------------- | ------------- | --- | --- | --- |
|     |     |                      | c c          |     |     |     |
|     |     |   =                 |   .         |     |     |     |
|     |     | x(cid:31)(cid:30)  0 | A  x(cid:30) |     |     |     |
|     |     |                   | o         |     |     |     |
The eigenvalues of a block triangular matrix are the combined eigenvalues of its
diagonal blocks. Theorem 3.1 and Theorem 3.2 guarantee A c and A o are Hurwitz,
| respectively. This completes the proof.  |     |     |     |     |     | □   |
| ---------------------------------------- | --- | --- | --- | --- | --- | --- |
Next, we analyze the performance of this proposed OPFB cooperative regulator
using the concept of synchronization region. The synchronization region for this
dynamic OPFB control law can be defined as follows.
Definition 3.3 Consider the OPFB cooperative regulator (3.27) and (3.28). The
synchronization region is the complex region defined as
| S    | s C A    | sBK       | s     | C A sFC |           | .   |
| ---- | -------- | --------- | ----- | ------- | --------- | --- |
| OPFB | (cid:31) | isHurwitz |       |         | isHurwitz |     |
|      | { ∈ |    | −         | }∩{ ∈ | | −     |           | }   |
Corollary 3.2 Consider the OPFB cooperative regulator (3.27) and (3.28). When
the control gain K and observer gain F are designed as in Theorem 3.1 and Theorem
3.2, the synchronization region is an unbounded right-half plane. More specifically, a
conservative synchronization region is S ={α+ jβ|α∈[1/2, ∞),β∈(−∞,∞)}.
OPFB
Proof Let s α jβ. Using the same development as in Theorem 3.1 and Theo-
|     | = + |     |     |     |     |     |
| --- | --- | --- | --- | --- | --- | --- |
rem 3.2, we have
(A−sBK)*P+P(A−sBK)=−Q−(2α−1)KTRK,
|     | (A−sFC)P+P(A−sFC)* |     | =−Q−(2α−1)FRFT. |     |     |     |
| --- | ------------------ | --- | --------------- | --- | --- | --- |
Therefore, P >0, Q>0, and R>0;  α 1/2 guarantees that both A sBK
|                         |     |     | ≥   |     |     | −   |
| ----------------------- | --- | --- | --- | --- | --- | --- |
| and A sFC are Hurwitz.  |     |     |     |     |     | □   |
−
3.6.2   Neighborhood Controller and Local Observer
The OPFB cooperative regulator just presented uses the complete neighborhood
information available for both the controller design (3.27) and the observer design
(3.28). In cooperative multi-agent systems on graphs, to achieve synchronization it is
not necessary to use neighbor information in both the control protocol and the observ-

94 3  Riccati Design for Synchronization of Continuous-Time Systems
er protocol, as long as one or the other contains neighbor information. This reveals a
richness of structure not appearing in the case of standard single-agent systems.
The OPFB cooperative regulator designed in this section uses the neighborhood
estimate tracking error information  ε i for the controller design and only the local
ˆ
agent output estimation error information  y  for the observer design. Here by
˜i
“local”, we mean the information only about node i itself.
For node i, the controller uses complete neighbor information and is designed as
|     |     |       |      |         |         |            |        |
| --- | --- | ----- | ----- | ------- | ------- | ----------- | ------ |
|     | u   | =cKεˆ | =cK  | ∑ a (xˆ | -xˆ )+g | (xˆ -xˆ ), |        |
|     | i   |       | i     | ij      | j i     | i 0 i       | (3.31) |
|     |     |       | j∈Ni |         |         |            |        |
whereas the observer uses only local agent information and is designed as
xˆ(cid:28)
|                                       |     |     | =   | Axˆ +Bu | -cFy(cid:27) | .   | (3.32) |
| ------------------------------------- | --- | --- | --- | ------- | ------------ | --- | ------ |
|                                       |     |     | i   | i i     | i            |     |        |
| The closed-loop dynamics of node i (i |     |     |     |         | ) is         |     |        |
∈N
|     |           |       |          |         |         |             |     |
| --- | --------- | ----- | --------- | ------- | ------- | ------------ | --- |
|     | x(cid:28) | = Ax  | +cBK     | ∑ a (xˆ | -xˆ )+g | (xˆ -xˆi ), |     |
|     | i         | i     |           | ij      | j i     | i 0          |     |
|     |           |       | j∈Ni     |         |         |             |     |
|     | (cid:28)ˆ | = Axˆ | +Bu -cF(y | -yˆ     | ).      |              |     |
|     | x         | i     | i         | i       | i       |              |     |
i
Here, the second equation is that of a local agent observer not coupled to informa-
tion from any neighbors. The global closed-loop dynamics can be written as
| x(cid:28)=(I | ⊗A)x-c[(L+G)⊗BK](xˆ-x |     |     |     | ),  |     |     |
| ------------ | --------------------- | --- | --- | --- | --- | --- | --- |
N
0
xˆ(cid:28)
| =[I | ⊗(A+cFC)]xˆ-c[(L+G)⊗BK](xˆ-x |     |     |     |     | )-(I ⊗cFC)x. |     |
| --- | ---------------------------- | --- | --- | --- | --- | ------------ | --- |
|     | N                            |     |     |     |     | 0 N          |     |
It can be shown that
|     |     | (cid:28)         |     |       |        |              |        |
| --- | --- | ----------------- | --- | ----- | ------ | ------------ | ------ |
|     |     |  δ               |  A | B     |        |   δ       |        |
|     |     |                   | = c |       | c      | .           | (3.33) |
|     |     |                  |   |       |        |            |        |
|     |     | x(cid:28)(cid:27) |  0 | I ⊗(A | +cFC) |  x(cid:27) |        |
|     |     |                  |    | N     |        |              |        |
Theorem 3.5 Let (A, B,C) be stabilizable and detectable and the augmented graph
 has a spanning tree with the leader node as the root. Let the OPFB coopera-
G
tive dynamic tracking control law be (3.31) and (3.32). Design the SVFB gain K
and coupling gain c according to Theorem 3.1. Design the observer gain F such
that the local agent observer (A cFC) is Hurwitz. Then all nodes i=1,2,…,N
+
synchronize to the leader node 0 asymptotically and the state estimation error  x
˜
approaches zero asymptotically.
| Proof Similar to Theorem 3.4, thus omitted.  |     |     |     |     |     |     | □   |
| -------------------------------------------- | --- | --- | --- | --- | --- | --- | --- |

| 3.6  |  Cooperative Dynamic Regulators for Synchronization  |     |     |     |     |     |     |     | 95  |
| ---- | ---------------------------------------------------- | --- | --- | --- | --- | --- | --- | --- | --- |
Since (A,C) is detectable, an F can be selected such that (A cFC) is Hurwitz.
+
Also, F can be designed using the local Riccati equation as in Theorem 3.2, except that
F =−PCTR−1.
A similar synchronization region analysis for this OPFB cooperative regulator can
be carried out as that in Sect. 3.6.1.
3.6.3   Local Controller and Neighborhood Observer
This third OPFB cooperative regulator design uses only the local agent “state es-
timate” for controller design and the complete neighborhood information for “ob-
server” design. For node i, the controller portion is designed using local agent feed-
back based on a sort of ‘estimate’ of the leader’s state
|     |     |     |     | u   | = K(xˆ    | −xˆ ), |     |     |        |
| --- | --- | --- | --- | --- | --------- | ------ | --- | --- | ------ |
|     |     |     |     | i   | i         | 0i     |     |     | (3.34) |
|     |     |     |     | xˆ |           |        |     |     |        |
|     |     |     |     |     | =(A+BK)xˆ |        |     |     | (3.35) |
|     |     |     |     | 0i  |           | 0i     |     |     |        |
and using complete neighbor information in the ‘observer’ dynamics
|     |     |                      |     |       |              |                |         |               |        |
| --- | --- | -------------------- | --- | ------ | ------------ | -------------- | ------- | -------------- | ------ |
|     |     | xˆ(cid:30) =(A+BK)xˆ |     | −cF ∑ | a (y(cid:29) | −y(cid:29) )+g | (y −Cxˆ | −y(cid:29) ). |        |
|     |     |                      |     | i      | ij           |                | i 0 0i  |                | (3.36) |
|     |     | i                    |     |       |              | j i            |         | i             |        |
j∈Ni
This third design is somewhat surprising since the controller uses no information
about the neighbors, yet the following result shows that synchronization is reached
using this rather odd OPFB cooperative regulator.
Theorem 3.6 Let (A, B,C) be stabilizable and detectable and the augmented graph
 has a spanning tree with the leader node as the root. Let the cooperative dynamic
G
OPFB tracking control law be (3.34), (3.35), and (3.36). Design the SVFB gain K
such that A BK is Hurwitz. Design the “observer” gain F and the coupling gain
+
c according to Theorem 3.2. Then all nodes i=1,2,…,N  synchronize to the leader
node 0 asymptotically.
Proof Define  µ=col(µ,µ,…,µ )  with µ = x −x , η=col(η,η,…,η )
|     |     |     |     | 1 2 | N   | i   | i 0 | 1   | 2 N |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
with  η x x 0i, and  θ col(µ,η). Then asymptotic stability of  θ implies
|     | i = | ˆ i − ˆ |     | =   |     |     |     |     |     |
| --- | --- | ------- | --- | --- | --- | --- | --- | --- | --- |
that  lim (x (t) x (t)) 0 and  lim (x (t) x (t)) 0,  i . Let
|     | t   | i   | 0   |     | t   | i     | 0i  |     |     |
| --- | --- | --- | --- | --- | --- | ----- | --- | --- | --- |
|     | →x  | ∞   | −   | =   |     | → ∞ ˆ | − ˆ | = ∀ | ∈ N |
x 0i (t 0 ) 0j (t 0 ). T hen x 0i (t) x 0j (t),  i, j  a nd   t t . Stra igh tf orward
| ˆ   | =   | ˆ   | ˆ   | = ˆ | ∀   | ∈ N | ∀ ≥ | 0   |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
computation yields the dynamics of θ as
|     |     |     |          | I A    |     | I BK |          |      |        |
| --- | --- | --- | -------- | ------ | --- | ---- | -------- | ---- | ------ |
|     |     | θ   |          | N ⊗    |     | N ⊗  | θ        | A θ. | (3.37) |
|     |     | ˙ = | c(L      | G ) FC | I   | B K  | A =      | θ    |        |
|     |     |     |          |        | N   |      | o        |      |        |
|     |     |     | (cid:31) | + ⊗    |     | ⊗ +  | (cid:30) |      |        |

96 3  Riccati Design for Synchronization of Continuous-Time Systems
Matrix A θ is similar to the matrix
|            |     |          | I        | (A BK) | I   | BK        |          |       |             |
| ---------- | --- | -------- | -------- | ------ | --- | --------- | -------- | ----- | ----------- |
|            |     |          | N        |        |     | N .       |          |       |             |
|            |     |          | ⊗        | +      |     | ⊗         |          |       |             |
|            |     |          |          | 0      |     | A o       |          |       |             |
|            |     |          | (cid:31) |        |     | (cid:30)  |          |       |             |
|            |     | I N      | (A       | BK)    | I N | BK        |          | I n N | 0           |
| In fact, T | 1A  | T        | ⊗ +      |        | ⊗   | , where T |          |       |  and        |
|            | −   | θ =      | 0        |        | A   |           | =        | I I   |             |
|            |     | (cid:31) |          |        | o   | (cid:30)  | (cid:31) | n N   | nN (cid:30) |
I 0
| T 1 | nN        |          |     |     |     |     |     |     |     |
| --- | --------- | -------- | --- | --- | --- | --- | --- | --- | --- |
| −   | I         | I .      |     |     |     |     |     |     |     |
|     | =         | nN nN    |     |     |     |     |     |     |     |
|     | (cid:31)− | (cid:30) |     |     |     |     |     |     |     |
Therefore,  θ is asymptotically stable if and only if both  I (A BK)
|     |     |     |     |     |     |     |     | N ⊗ | +       |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | ------- |
|     |     |     |     |     |     |     |     | A   | BK and  |
and  A  are Hurwitz, which are equivalent to the conditions that
|     | o   |     |     |     |     |     |     | +   |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
A-cλFC,  i  are Hurwitz (see Lemma 3.5). Theorem 3.2 guarantees stabil-
|     | i   | ∀ ∈N |     |     |     |     |     |     |     |
| --- | --- | ---- | --- | --- | --- | --- | --- | --- | --- |
ity of A-cλFC. A suitable K can be selected since (A,B) is stabilizable.  □
i
Similar synchronization region analysis can be carried out as in Sect. 3.6.1.
Note  that  the  derivation  of  (3.37)  requires  the  conditions
x (t ) x (t ), i,j . A special case is when  x (t ) 0, i . Then
| ˆ 0i 0 | = ˆ 0j | 0 ∀ ∈N |     |     |     | ˆ 0i | 0 = | ∀ ∈N |     |
| ------ | ------ | ------ | --- | --- | --- | ---- | --- | ---- | --- |
x (t) 0,  i , t t  and the control law (3.34) and (3.36) are simplified as
| 0i  |     |        | 0   |     |     |     |     |     |     |
| --- | --- | ------ | --- | --- | --- | --- | --- | --- | --- |
| ˆ   | =   | ∀ ∈N ≥ |     |     |     |     |     |     |     |
u = Kxˆ,
i
i
|     |     |                     |     |       |              |                   |              |     |     |
| --- | --- | ------------------- | --- | ------ | ------------ | ----------------- | ------------- | --- | --- |
|     |     | (cid:28)ˆ =(A+BK)xˆ |     | -cF ∑ | a (y(cid:27) | -y(cid:27) )+g (y | -y(cid:27) ) | .   |     |
|     |     | x                   | i   |        |              |                   |               |     |     |
|     |     | i                   |     |       | ij           | j i i             | 0 i          |     |     |
j∈Ni
Remark 3.4 The “observer” (3.36) was proposed in [14]. It is not a true observer,
in the sense that  lim (x x ) 0 and  lim (x x ) 0. The variables
|     |     | t   | i   | i         |     | t 0i    | 0          |     |     |
| --- | --- | --- | --- | --------- | --- | ------- | ---------- | --- | --- |
|     |     | → ∞ | ˆ − | (cid:27)= |     | → ∞ ˆ − | (cid:27) = |     |     |
x i and x 0i only take r ol es  of  interm ediate variabl es  in  the  contr o ller design.  ▋
ˆ ˆ
3.7   Simulation Examples
A large scope of industrial applications can be modeled as the mass–spring system,
including vibration in mechanical systems, animation of deformable objects, etc. In
this example, we consider a cooperative tracking problem with one leader node and
6 follower nodes. Each node is a two-mass–spring system with a single force input,
except for the leader node, which is unforced. The system is shown in Fig. 3.5,
where  m  and  m  are masses,  k  and  k  are spring constants,  u i is the force
|                         | 1   | 2         |     | 1   | 2   |     |     |     |     |
| ----------------------- | --- | --------- | --- | --- | --- | --- | --- | --- | --- |
| input for mass 1, and y |     | i,1 and y |     |     |     |     |     |     |     |
i,2 are the displacements of the two masses.
|     |     |     |     |     |     |     | ]T  |     | ]T  |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
Define the state vector for node i as x =[x ,x ,x ,x =[y ,y(cid:28) ,y ,y(cid:28)
|     |     |     |     | i   | i,1 | i,2 i,3 i,4 | i,1 | i,1 | i,2 i,2 |
| --- | --- | --- | --- | --- | --- | ----------- | --- | --- | ------- |
and the measured output information as  y [y ,y ]T. Then, this two-mass–
|     |     |     |     |     | i = | i,1 i,2 |     |     |     |
| --- | --- | --- | --- | --- | --- | ------- | --- | --- | --- |
spring system can be modeled by
|     |     |     |     | x(cid:28) = | Ax +Bu |     |     |     | (3.38) |
| --- | --- | --- | --- | ----------- | ------ | --- | --- | --- | ------ |
|     |     |     |     | i           | i      | i   |     |     |        |

| 3.7                         |  Simulation Examples  |     |     |     |     |     |     |     | 97  |
| --------------------------- | --------------------- | --- | --- | --- | --- | --- | --- | --- | --- |
| F ig. 3.5  Two-mass–spring  |                       |     |     |     |     | y   |     | y   |     |
|                             |                       |     |     |     |     | i,1 |     |     | i,2 |
system
u
i
|     |     |     |     | k   |     |     | k   |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
|     |     |     |     | 1   |     |     | 2   |     |     |
|     |     |     |     |     |     | m   |     | m   |     |
|     |     |     |     |     |     | 1   |     | 2   |     |
F ig. 3.6  Communication
0
graph topology
1
|     |     |     |     |     |     |     | 2   | 6   |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
|     |     |     |     |     |     | 1   |     | 2   | 3   |
1
|     |     |     |     |     |     |     | 3   | 1   |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
|     |     |     |     |     |     | 6   |     | 5   | 4   |
y Cx
|     |     |     |     |     | i = | i   |     |     | (3.39) |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | ------ |

|      |     | 0     | 1       | 0 0  |     | 0          |     |          |          |
| ---- | --- | ----- | ------- | ---- | --- | ---------- | --- | -------- | -------- |
|      |     | k 1−  | k2 0 k2 | 0    |     | 1          |     |          |          |
|      |     | −     |         |      |     |            |     | 1 0      | 0 0      |
| with | A   |  m 1 | m       | 1 , | B   | m 1, and | C   |          | .        |
|      | =   | 0     | 0       | 0 1  | =   | 0          | =   | 0 0      | 1 0      |
|      |     |       |         |      |     |            |     | (cid:25) | (cid:24) |
|      |     | k2    |         | k    |     |            |     |          |          |
|      |     |      | 0 −m    | 2 0 |     |  0       |     |          |          |
|      |     |  m 2 |         | 2   |     |          |     |          |          |
|      |     |      |         |     |     |          |     |          |          |
Let the command generator leader node consist of an unforced two-mass–spring
system, producing a desired state trajectory. Six two-mass–spring systems act as
follower nodes and these nodes receive state or output information from their neigh-
bors, according to the communication graph topology described in Fig. 3.6. The
edge weights of the links are shown in the figure.
The objective of the cooperative tracking control problem is to design distrib-
uted controllers  u for the follower nodes, such that the displacements of both
i
masses synchronize to that of the leader node, i.e.,  lim t (y i,1 y 0,1 ) 0 and
|     |     |     |     |     |     |     | → ∞y | − = |     |
| --- | --- | --- | --- | --- | --- | --- | ---- | --- | --- |
lim (y y ) 0 for i=1,…,6. The displacemen t   o f mass  2 is dif-
| t   | i,2 | − 0,2 | =   |     |     |     | i,2 |     |     |
| --- | --- | ----- | --- | --- | --- | --- | --- | --- | --- |
ficult to control using only the force input to mass 1. →∞
In the following, we shall verify the proposed cooperative control algorithms,
namely, the SVFB control law from Theorem 3.1 and the three types of dy-
|     |     |     |     |     |     |     |     | m   | 1.1kg,  |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | ------- |
namic OPFB cooperative trackers in Sect. 3.6. In the simulations,  1
=
m 0.9kg,  k 1.5N/m, and  k 1N/m. The coupling gain  c 2, which
| 2 = |     | 1 = |     | 2   | =   |     |     | =   |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |

98 3 Riccati Design for Synchronization of Continuous-Time Systems
2.5
2
1.5
1
0.5
0
−0.5
−1
−1.5
−2
−2.5
0 5 10 15 20 25
time (second)
satisfies conditions (3.12) and (3.22) for this graph topology. The initial values
x i (i=0,1,…,6) are random and are generated by the Matlab function randn.
a. SVFB Cooperative tracker
First, we assume full SVFB, so that the displacements and velocities of both mass
1 and mass 2 are measurable for all agents. The distributed control law is (3.5) with
c, K found for each agent by using the Riccati equation design method from Theo-
rem 3.1. The tracking performances are depicted in Figs. 3.7–3.8. These figures
show that displacements y i,1 ,y i,2 (i=1,…,6) synchronize to the displacements
y 0,1 ,y 0,2 of the leader node within a few seconds. Velocity tracking is also achieved
and the figures are omitted here to avoid redundancy.
b. OPFB Dynamic Cooperative Trackers
When the velocities of mass 1 and mass 2 are not measurable, but only position
feedback is possible, we design three types of dynamic OPFB cooperative control-
lers. We use the three design methods for dynamic cooperative trackers given in
Sect. 3.6. For convenience, we label the three cases as
• Case 1: OPFB with neighborhood controller and neighborhood observer
(Sect. 3.6.1).
• Case 2: OPFB with neighborhood controller and local observer (Sect. 3.6.2).
• Case 3: OPFB with local controller and neighborhood observer (Sect. 3.6.3).
1
ssam
fo
stnemecalpsid
fo
seirotcejarT
node 0
node 1
node 2
node 3
node 4
node 5
node 6
Fig. 3.7 Cooperative control using SVFB and local Riccati design. Profiles of the displacements
y (i=0,…,6) of mass 1
i,1

3.7 Simulation Examples 99
2.5
2
1.5
1
0.5
0
−0.5
−1
−1.5
−2
0 5 10 15 20 25
time (second)
−1.2124 −0.1259
 
−0.2428 −0.0944
In the simulation, for Case 2, the observer gain is taken as F = ,
−0.1259 −1.4329
 
−0.2386 −0.5345
which makes A cFC Hurwitz. For Case 3, the control gain is taken as
+
K =[−0.9907 −1.7831 0.4292 −0.9807], which makes A BK Hurwitz.
+
Using these types of dynamic OPFB cooperative trackers, the displacement
tracking performance and estimation performance are illustrated, in Figs. 3.9–3.17.
Note that Fig. 3.17 shows that, for Case 3, x i is not a true observer for x i, nor x 0i an
ˆ ˆ
observer for x . These variables simply act as intermediate variables in the control
0
protocol and are part of the dynamics of the OPFB cooperative tracker.
2
ssam
fo
stnemecalpsid
fo
seirotcejarT
node 0
node 1
node 2
node 3
node 4
node 5
node 6
Fig. 3.8 Cooperative control using SVFB and local Riccati design. Profiles of the displacements
y (i=0,…,6) of mass 2
i,2

100 3 Riccati Design for Synchronization of Continuous-Time Systems
4
3
2
1
0
−1
−2
−3
0 5 10 15 20 25
time (second)
1
ssam
fo
stnemecalpsid
fo
seirotcejarT
node 0
node 1
node 2
node 3
node 4
node 5
node 6
Fig. 3.9 Dynamic OPFB cooperative tracker of Case 1. Profiles of the displacements y i,1
(i=0,…,6) of mass 1
4
3
2
1
0
−1
−2
−3
0 5 10 15 20 25
time (second)
2
ssam
fo
stnemecalpsid
fo
seirotcejarT
node 0
node 1
node 2
node 3
node 4
node 5
node 6
Fig. 3.10 Dynamic OPFB cooperative tracker of Case 1. Profiles of the displacements y i,2
(i=0,…,6) of mass 2

101
4
3
2
1
0
−1
−2
−3
0 5 10 15 20 25
time (second)
srorre
noitamitse
etatS
Fig. 3.11 Dynamic OPFB cooperative tracker of Case 1. Profiles of the state estimation errors
x i,j (i=1,…,6; j=1,…,4)
˜
4
3
2
1
0
−1
−2
−3
0 5 10 15 20 25
time (second)
1
ssam
fo
stnemecalpsid
fo
seirotcejarT
3.7 Simulation Examples
node 0
node 1
node 2
node 3
node 4
node 5
node 6
Fig. 3.12 Dynamic OPFB cooperative tracker of Case 2. Profiles of the displacements y i,1
(i=0,…,6) of mass 1

102 3 Riccati Design for Synchronization of Continuous-Time Systems
3
2
1
0
−1
−2
−3
−4
0 5 10 15 20 25
time (second)
2
ssam
fo
stnemecalpsid
fo
seirotcejarT
node 0
node 1
node 2
node 3
node 4
node 5
node 6
Fig. 3.13 Dynamic OPFB cooperative tracker of Case 2. Profiles of the displacements y i,2
(i=0,…,6) of mass 2
5
4
3
2
1
0
−1
−2
0 5 10 15 20 25
time (second)
srorre
noitamitse
etatS
Fig. 3.14 Dynamic OPFB cooperative tracker of Case 2. Profiles of the state estimation errors
x i,j (i=1,…,6; j=1,…,4)
˜

103
4
3
2
1
0
−1
−2
−3
0 5 10 15 20 25
time (second)
1
ssam
fo
stnemecalpsid
fo
seirotcejarT
node 0
node 1
node 2
node 3
node 4
node 5
node 6
Fig. 3.15 Dynamic OPFB cooperative tracker of Case 3. Profiles of the displacements y i,1
(i=0,…,6) of mass 1
5
4
3
2
1
0
−1
−2
−3
0 5 10 15 20 25
time (second)
2
ssam
fo
stnemecalpsid
fo
seirotcejarT
3.7 Simulation Examples
node 0
node 1
node 2
node 3
node 4
node 5
node 6
Fig. 3.16 Dynamic OPFB cooperative tracker of Case 3. Profiles of the displacements y i,2
(i=0,…,6) of mass 2

104 3 Riccati Design for Synchronization of Continuous-Time Systems
F ig. 3.17 Dynamic OPFB 4
cooperative tracker
2
of Case 3. Profiles of
a x n i d ,j −x i,j x ˆ i,j, x 0 x i 0 , , j j - xˆ 0i,j ,, 0
ˆ − ˆ −2
(i=1,…,6; j=1,…,4)
−4
−6
0 5 10 15 20 25
time (second)
4
2
0
−2
−4
0 5 10 15 20 25
time (second)
4
2
0
−2
−4
0 5 10 15 20 25
time (second)
References
1. Antsaklis PJ, Michel AN (2007) A Linear Systems Primer. Birkhauser, Boston
2. Chen CT (1984) Linear System Theory and Design. Holt, Rinehart and Winston, New York
3. Chen G, Lewis FL, Xie L (2011) Finite-time distributed consensus via binary control protocols.
Automatica 47(9):1962–19685
4. Das A, Lewis FL (2010) Distributed adaptive control for synchronization of unknown nonlin-
ear networked systems. Automatica 46(12):2014–2021
5. Das A, Lewis FL (2011) Cooperative adaptive control for synchronization of second-order
systems with unknown nonlinearities. Int J Robust Nonlinear Control 21(13):1509–1524
6. Du H, Li S, Qian C (2011) Finite-time attitude tracking control of spacecraft with application
to attitude synchronization. IEEE Trans Autom Control 56(11):2711–2717
7. Duan Z, Chen G, Huang L (2009) Disconnected synchronized regions of complex dynamical
networks. IEEE Trans Autom Control 54(4):845–849
8. Fax JA, Murray RM (2004) Information flow and cooperative control of vehicle formations.
IEEE Trans Autom Control 49(9):1465–1476
9. Horn RA, Johnson CR (1990) Matrix Analysis. Cambridge University Press, Cambridge

References 105
10. Jadbabaie A, Lin J, Morse A (2003) Coordination of groups of mobile autonomous agents
using nearest neighbor rules. IEEE Trans Autom Control 48(6):988–1001
11. Khoo S, Xie L, Man Z (2009) Robust finite-time consensus tracking algorithm for multirobot
systems. IEEE Trans Mechatron 14(2):219–228
12. Lewis FL, Xie L, Popa D (2007) Optimal & Robust Estimation: With an Introduction to
Stochastic Control Theory, 2nd edn. CRC Press, Boca Raton
13. Lewis FL, Vrabie D, Syrmos VL (2012) Optimal Control, 3rd edn. Wiley, New York
14. Li Z, Duan Z, Chen G, Huang L (2010) Consensus of multiagent systems and synchroni-
tion of complex networks: a unified viewpoint. IEEE Trans. Circuits Syst I, Reg Papers
57(1):213–224
15. Olfati-Saber R, Murray RM (2004) Consensus problems in networks of agents with switch-
ing topology and time-delays. IEEE Trans Autom Control 49(9):1520–1533
16. Qiu L, Zhou K (2010) Introduction to Feedback Control. Prentice Hall, Upper Saddle River
17. Ren W, Beard RW, Atkins EM (2005) A survey of consensus problems in multi-agent coordi-
nation. In: Proc. Amer. Control Conf., Portland, OR, pp. 1859–1864
18. Shivakumar PN, Chew KH (1974) A sufficient condition for nonvanishing of determinants.
Proc Amer Math Soc 43(1):63–66
19. Tuna SE (2008) LQR-based coupling gain for synchronization of linear systems. Arxiv pre-
print arXiv: 0801.3390
20. Wang X, Chen G (2002) Pinning control of scale-free dynamical networks. Physica A
310(3):521–531
21. Zhang H, Lewis FL, Das A (2011) Optimal design for synchronization of cooperative sys-
tems: state feedback, observer and output feedback. IEEE Trans Autom Control 56(8):1948–
1952

Chapter 4
Riccati Design for Synchronization
of Discrete-Time Systems
In this chapter, design methods are given for synchronization control of discrete-
time multi-agent systems on directed communication graphs. The graph is assumed
to have fixed topology and contain a spanning tree. The graph properties complicate
the design of synchronization controllers due to the interplay between the eigen-
values of the graph Laplacian matrix and the required stabilizing gains. A method
is given that decouples the design of the synchronizing feedback gains from the
detailed graph properties. It is based on computation of the agent feedback gains
using a local Riccati equation design. Conditions are given for synchronization
based on the relation of the graph eigenvalues to a bounded circular region in the
complex plane that depends on the agent dynamics and the Riccati solution. The no-
tion of ‘synchronization region’ is used. Convergence to consensus and robustness
properties are investigated. This chapter also investigates the design of distributed
observers for identical agents using a local Riccati design. A cooperative observer
design guaranteeing convergence of the estimates of all agents to their actual states
is proposed. The notion of a convergence region for distributed observers on graphs
is introduced.
The feedback control synchronization region and the observer convergence re-
gion for discrete-time systems are inherently bounded, so that the conditions for
state synchronization and observer convergence are stricter than the results for the
continuous-time counterparts given in Chap. 3. This is, in part, remedied by using
weighting by different feedback coupling gains for every agent based on its in-
degree.
A duality principle that involves the notion of reverse graph is shown for state
feedbacks and observers for distributed discrete-time systems on balanced graph
topologies. Three different cooperative controller/observer architectures are pro-
posed for dynamic output feedback regulator design, and all are shown to guarantee
convergence of the estimate to the true state as well as synchronization of all the
agents’ states to the command state trajectory. This provides design methods for
cooperative regulators based on a separation principle. Examples show the effec-
tiveness of these design methods for guaranteeing synchronization in cooperative
discrete-time systems.
The results in this chapter were first published in [4].
F. L. Lewis et al., Cooperative Control of Multi-Agent Systems, 107
Communications and Control Engineering, DOI 10.1007/978-1-4471-5574-4_4,
© Springer-Verlag London 2014

108 4 Riccati Design for Synchronization of Discrete-Time Systems
4.1 Graph Properties
The information flow between agents is modeled here as a communication graph.
Consider a graph G =(V,E) with a nonempty finite set of N vertices or nodes
 ={v,,v } and a set of edges or arcs E ⊆V×V. It is assumed that the graph
1 N
is simple, i.e., there are no repeated edges or self-loops, (v,v)∉,∀i. General di-
i i
rected graphs (digraphs) are considered and it is taken that information propagates
through the graph along directed arcs. Denote the connectivity or adjacency matrix
as E = [e ] with e >0 if (v ,v)∈ and e =0 otherwise. Note that diagonal
ij ij j i ij
elements satisfy e =0 because the graph is simple. The set of neighbors of node
ii
v is denoted as N ={v :(v ,v)∈E}, i.e., the set of nodes with arcs incoming
i i j j i
into v. Define the in-degree matrix as a diagonal matrix D=diag(d …d ) with
i 1 N
d =∑e , the (weighted) in-degree of node i ( i.e. the ith row sum of E). Define
i ij
j
the graph Laplacian matrix as L= D−E, which has all row sums equal to zero.
A directed path from node v to node v is a sequence of edges
(v v ),(v v ),…(v ,v ), with (v i , 1 v )∈ for j ik ∈{2,…,k}. The graph is said
i1, i2 i2, i3 ik−1 ik ij−1 ij
to contain a (directed) spanning tree if there exists a vertex such that every other
vertex in  can be connected by a directed path starting from that vertex. Such a
special vertex is then called a root.
Given the graph G =(V,E), the reverse graph ′ is a graph having the same set
of vertices ′= and the set of edges with the property E′=[e′ ij]= ET =[eji].
That is, the edges of  are reversed in ′.
We denote real numbers by , positive real numbers by +, and complex num-
bers by . For any matrix A, σ (A),σ (A) are the minimal and maximal singu-
min max
lar values of A, respectively. C(O,r) denotes an open circle in the complex plane
with its center at O∈ and radius r. The corresponding closed circle is denoted
as C(O,r). For any square matrix A, the spectral radius ρ(A)=max eig(A) is the
maximal magnitude of the eigenvalues of A.
4.2 State Feedback Design of Discrete-Time
Cooperative Controls
In this section, we design cooperative controllers for discrete-time (DT) multi-agent
systems using state variable feedback (SVFB), that is, assuming that the full state
of each agent is available for feedback control design by itself and its out-neighbors
in the communication graph. We require that any control protocol be distributed in
the sense that the control for agent i depends only on its own information and that
from its (in-)neighbors in the graph. It is shown that locally optimal design in terms
of a local DT Riccati equation, along with selection of a suitable distributed control
protocol, guarantees synchronization on arbitrary communication graphs that have
a spanning tree.

4.2 State Feedback Design of Discrete-Time Cooperative Controls 109
4.2.1 Synchronization of Discrete-Time Multi-Agent
Systems on Graphs
The starting point for consideration are the dynamics of the multi-agent system
which are now specified. Given a communication graph G(V,E) that describes the
topology of the agent interactions, let each of its N nodes be endowed with a state
vector x ∈n and a control input u ∈m, and consider at each node the discrete-
i i
time linear time-invariant dynamics
x(k+1)= Ax(k)+Bu (k) (4.1)
i i i
Assume that (A,B) is stabilizable and B has full column rank m. This assumption
is necessary for the subsequent feedback design.
A leader node, control node, or command generator has the autonomous drift
dynamics with no input
x (k+1)= Ax (k) (4.2)
0 0
with x ∈n.
0
Although the leader dynamics (4.2) is autonomous and has no control input, it
can generate a large class of useful command trajectories. The interesting cases are
when matrix A is not stable. The types of trajectories that can be generated by the
leader include the unit step (position command), the ramp (useful in velocity track-
ing systems, e.g., satellite antenna pointing), sinusoidal waveforms (useful, e.g., in
hard disk drive control), and more. In this chapter, A can be either stable, marginally
stable, or even unstable, as long as ( A, B) is stabilizable.
The cooperative tracker or synchronization problem is to select the control sig-
nals u, using only measurements from the neighbors of node i, such that all nodes
i
synchronize to the state of the control node, that is, lim x(k)−x (k) =0,∀i.
i 0
k→∞
These requirements should be fulfilled for all initial conditions x(0). If the trajec-
i
tory x (k) approaches a fixed point, this is normally called the consensus problem.
0
To achieve synchronization, define the local neighborhood tracking errors:
ε = ∑e (x −x)+g (x −x) (4.3)
i ij j i i 0 i
j∈Ni
where the pinning gain g ≥0 is nonzero if node v can directly sense the state of
i i
the control node. The intent is that only a small percentage of nodes have the control
node as a neighbor with g >0, yet all nodes should synchronize to the trajectory
i
of the control node using local neighborhood control protocols. It is assumed that
at least one pinning gain is nonzero, with pinning into a root node. Note that the lo-
cal neighborhood tracking error represents the information available to agent i for
control purposes.

110 4  Riccati Design for Synchronization of Discrete-Time Systems
Choose the input of agent i as the weighted local control protocol:

|     |     | u =c(1+d | +g )−1Kε, |     | (4.4) |
| --- | --- | -------- | --------- | --- | ----- |
|     |     | i        | i i i     |     |       |
where c is a coupling gain to be detailed later. By ‘weighted’, we mean that the pro-
tocol is multiplied by the weighting factor (1+d +g )−1, which captures the local
i i
properties of the graph with respect to node i. Then, the closed-loop dynamics of the
individual agents are given by
|     |          |              | )-1 |         |       |
| --- | -------- | ------------ | --- | ------- | ----- |
|     | x (k+1)= | Ax (k)+c(1+d | +g  | BKε(k). | (4.5) |
|     | i        | i            | i i | i       |       |
Defining global tracking error and state vectors as ε=εT…εT T ∈(cid:25)nN
|     |     |     |     |    | , and  |
| --- | --- | --- | --- | --- | ------ |
 1 N
| x=xT…xT  | T ∈(cid:25)nN, one writes the global error as |              |     |       |       |
| ---------- | --------------------------------------------- | ------------ | --- | ----- | ----- |
|  1 N     |                                               |              |     |       |       |
|            | ε(k)=−(L+G)⊗I                                 |              |     |       |       |
|            |                                               | x(k)+(L+G)⊗I |     | x (k) | (4.6) |
|            |                                               | n            |     | n 0   |       |
where  G=diag(g ,…,g )  is  the  diagonal  matrix  of  pinning  gains  and
1 N
x (k)=1⊗x (k) where 1∈N is the vector of ones. The Kronecker product is ⊗.
| 0 0                          |     |                            |     |     |     |
| ---------------------------- | --- | -------------------------- | --- | --- | --- |
| The global dynamics of the N |     | -agent system is given by  |     |     |     |
|                              |     | ⊗A−c(I+D+G)−1(L+G)⊗BKx(k) |     |     |     |
x(k+1)=I
|     |  N |     |     |    |     |
| --- | --- | --- | --- | --- | --- |
+ c(I+D+G)−1(L+G)⊗BKxx
|     |     |     |     | (k). | (4.7) |
| --- | --- | --- | --- | ---- | ----- |
0
Define the global disagreement error δ(k)= x(k)-x (k), which has the global dis-
0
agreement error dynamics
|     |     | δ(k+1)= | Aδ(k) |     | (4.8) |
| --- | --- | ------- | ----- | --- | ----- |
c
where the closed-loop system matrix is
|     | A =[I | ⊗A-c(I+D+G)-1(L+G)⊗BK]. |     |     | (4.9) |
| --- | ----- | ----------------------- | --- | --- | ----- |
|     | c N   |                         |     |     |       |
Matrix  A  reflects the local agent closed-loop matrix  A-BK  as modified on the
c
graph structure L+G. Note that the graph structure L + G appears on the left-hand
side of the Kronecker product, while the local state information appears on the right.
We refer to the matrix
|     |     | Γ=(I+D+G)−1(L+G) |     |     |     |
| --- | --- | ---------------- | --- | --- | --- |
(4.10)
as the (weighted) graph matrix. Its eigenvalues Λ , k =1,...,N are important in the
k
upcoming discussion, and we refer to them as the graph matrix eigenvalues.
Assumption 4.1 Assume the graph contains a directed spanning tree and has at
| least one nonzero pinning gain g |     |  into a root node i. |     |     |     |
| -------------------------------- | --- | -------------------- | --- | --- | --- |
i

4.2  State Feedback Design of Discrete-Time Cooperative Controls   111
Under this assumption, the graph matrix Γ is nonsingular, since L+G is non-
singular.
The importance of using weighting of (I+D+G)−1 in protocol (4.4) is demon-
strated by the following result, which shows that all the graph eigenvalues of Γ are
restricted to a closed circle of radius 1 in the right-half complex plane.
Γ
Lemma  4.1 Given  the  control  protocol  (4.4),  the  eigenvalues  of  satisfy
| Λ ⊆C(1,1), k =1...N, for any graph. |     |     |     |     |
| ----------------------------------- | --- | --- | --- | --- |
k
Proof Follows  directly  from  the  Geršgorin  circle  criterion  applied  to
| Γ=(I+D+G)−1(L+G), which has Geršgorin circles  |     |     | ( di+gi | di )     |
| ---------------------------------------------- | --- | --- | ------- | -------- |
|                                                |     |     | C ,     | . These  |
1+di+gi 1+di+gi
| are all contained in C(1,1).  |     |     |     | □   |
| ----------------------------- | --- | --- | --- | --- |
Lemma 4.1 reveals that weighting restricts the possible positions of the graph ma-
trix eigenvalues to the bounded known circular region C(1,1). The non-weighted
protocol u =cKε  yields graph eigenvalues in the region C(d +g ,d ), which
| i   | i   |     | i   | i i |
| --- | --- | --- | --- | --- |
i
is larger than C(1,1). The importance of using this weighting is further shown in
Example 4.1.
Under Assumption 4.1, the graph eigenvalues are inside the circle C(1,1), and all
have positive real parts. The next result was presaged in [1].
Lemma  4.2 The  multi-agent  systems  (4.5)  synchronize  if  and  only  if
ρ(A−cΛ BK)<1 for all eigenvalues Λ , k =1...N, of the graph matrix (4.10).
| k   |     | k   |     |     |
| --- | --- | --- | --- | --- |
Proof Let  J  be the Jordan form of  Γ, i.e., there exists a nonsingular matrix
| R∈N×N such that RΓR−1 | = J. From (4.9), it follows that |     |     |     |
| ---------------------- | -------------------------------- | --- | --- | --- |

|     |     | A−cΛ | BK × | ×  |
| --- | --- | ----- | ---- | --- |
1
| (R−1⊗I  |               |      |        |      |
| ------- | ------------- | ----- | ------ | ----- |
| (R⊗I )A | )= I ⊗A−cJ⊗BK | =  0 |       | ×  , |
| n c     | n N           |       |        |       |
|         |               |      |        |     |
|         |               |  0   | 0 A−cΛ | BK   |
N
(4.11)
where ‘×’ denotes possibly nonzero elements. By (4.11), one has ρ(A
)<1 if and
c
only if ρ(A−cΛ BK)<1 for all Λ . From (4.8), the multi-agent systems (4.5) syn-
|     | k k |     |     |     |
| --- | --- | --- | --- | --- |
chronize if and only if ρ(A )<1. Thus, the multi-agent systems (4.5) synchronize if
c
| and only if ρ(A−cΛ | BK)<1 for all Λ | .   |     | □   |
| ------------------ | --------------- | --- | --- | --- |
|                    | k               | k   |     |     |
For synchronization, one requires the asymptotic stability of the error dynamics
(4.8). It is assumed that (A,B) is stabilizable. If the matrix A is unstable or mar-
ginally stable, then Lemma 4.2 requires that Λ ≠0,k =1...N which is guaranteed
k
if the interaction graph contains a spanning tree with at least one nonzero pinning
gain into a root node.

112 4 Riccati Design for Synchronization of Discrete-Time Systems
4.3 Synchronization Region
Building on Lemma 4.2, we introduce the notion of the synchronization region,
which allows the analysis of the cooperative stability of the global multi-agent sys-
tem by considering the robust stability of a single agent. The following definitions
are required.
Definition 4.1 For a matrix pencil A-sBK, s∈ the synchronization region is a
subset S ⊆ such that S ={s∈ρ(A−sBK)<1}.
c c
Given the choice of K, the synchronization region S of the matrix pencil A-sBK
c
is determined. The synchronization region was discussed in [8], [10], [1], and [6]. A
concept related to synchronization region, yet of a more special form, is introduced
in the following definition.
Definition 4.2 Given a system (A,B), the complex gain margin region U ⊆ for
a given stabilizing feedback matrix K is a connected region containing 1 such that
ρ(A−sBK)<1,∀s∈U.
The distinction between the more general synchronization region and the complex
gain margin region is that the latter is connected, whereas the former may not be
[7]. This means that the complex gain margin region can more easily be determined
via, e.g., Lyapunov stability analysis. Clearly, the complex gain margin region is
contained in the synchronization region.
Lemma 4.3 Matrices A−cΛ BK are stable for all eigenvalues Λ if and only if
k k
they satisfy cΛ ∈S ,∀k∈{1,…,N}.
k c
According to this result, the cooperative stability of the entire multi-agent system is
reduced to a robust stabilization problem of the single-agent system (A,B).
4.4 Local Riccati Design of Synchronizing Protocols
Given a single-agent system (A,B), the synchronization region depends on the lo-
cal feedback matrix K. Therefore, the distributed control design problem is to find
a local feedback matrix K that yields a guaranteed synchronization region or a
complex gain margin region. It will now be shown that selecting the local feedback
matrix K as a locally optimal feedback, derived from a local algebraic Riccati
equation, gives a guaranteed gain margin region. Then, it remains to check the rela-
tion of the graph matrix eigenvalues to the guaranteed synchronization region. Suf-
ficient conditions for synchronization are given in the next theorem.
Theorem 4.1 Suppose (A,B) is stabilizable. Assume that the interaction graph
contains a spanning tree with at least one pinning gain nonzero that connects into
the root node. Let P>0 be a solution of the discrete-time Riccati-like equation
ATPA−P+Q−ATPB(BTPB)−1BTPA=0 (4.12)

| 4.4  Local Riccati Design of Synchronizing Protocols  |     |     |     | 113 |
| ----------------------------------------------------- | --- | --- | --- | --- |
          Fig. 4.1  Riccati design circle
C(1,r) and covering circle
C(C,r) of graph matrix
0 0
eigenvalues
r
0
r
|     |     | 1   | c   |     |
| --- | --- | --- | --- | --- |
0
| for some prescribed Q=QT | >0. Define |     |     |     |
| ------------------------ | ---------- | --- | --- | --- |
-1/2
|     | r:= σ (Q-T/2ATPB(BTPB)-1BTPAQ-1/2) |     | .   |        |
| --- | ------------------------------------ | --- | --- | ------ |
|     |  max                                |     |    | (4.13) |

Then, protocol (4.4) guarantees synchronization of multi-agent systems (4.5) for
some K if there exists a covering circle C(c ,r ) of the graph matrix eigenvalues
0 0
| Λ , k =1…N  such that |     |     |     |     |
| --------------------- | --- | --- | --- | --- |
k
r
|     |     | 0 <r.  |     | (4.14) |
| --- | --- | ------ | --- | ------ |
c
0
Moreover, if condition (4.14) is satisfied then the choice of feedback matrix
|     | K =(BTPB)−1BTPA |     |     | (4.15) |
| --- | --------------- | --- | --- | ------ |
and coupling gain
|     |     | 1   |     |        |
| --- | --- | --- | --- | ------ |
|     |     | c=  |     | (4.16) |
c
0
guarantee synchronization.
The above reasoning is motivated by geometrical considerations as shown in
Fig. 4.1. Condition (4.14) means that the covering circle C(c ,r ) of the graph
0 0
eigenvalues can be projected by radial scaling from the origin into a circle concen-
tric with and contained in the interior of C(1,r). It will be shown in Lemma 4.4 that
the synchronization region of the local Riccati feedback gain selected as in Theorem
4.1 contains C(1,r). Therefore, synchronization is guaranteed by any value of c
radially projecting C(c ,r ) into the interior of C(1,r). One such value is given by
0 0
(4.16). If C(c ,r ) can be projected by radial scaling from the origin into C(1,r),
0 0
| then C(c ,r ) is said to be homothetic to C(1,r). |     |     |     |     |
| ------------------------------------------------- | --- | --- | --- | --- |
| 0 0                                               |     |     |     |     |

114 4 Riccati Design for Synchronization of Discrete-Time Systems
The importance of Theorem 4.1 is that it decouples the local SVFB gain design
at each agent from the details of the interconnecting communication graph struc-
ture. The SVFB gain is designed by each agent using the local Riccati equation
(4.12), and then the graph topology comes into the choice of the coupling gain c
through condition (4.16). Unlike the continuous-time case discussed in Chap. 3, it
is not always possible to select K and c to guarantee synchronization on any graph
with a spanning tree. Indeed, condition (4.14) must be satisfied. It will be seen that
this condition is a relation between the properties of the communication graph and
the instability properties of the local agent dynamics.
The theorem shows that local Riccati SVFB control design by each agent guar-
antees the synchronization of all agents on any graph satisfying condition (4.14).
Note that the SVFB gain in Theorem 4.1 is related to the optimal gain [5] that mini-
mizes the local performance index
1 ∞
J = ∑xT(k)Qx(k)+uT(k)Rρu (k) (4.17)
i 2 i i i i
k=0
subject to the local agent dynamics (4.1), in the limit as ρ→0.
The local Riccati design method in Theorem 4.1 is scalable, since it only de-
pends on the local agent dynamics, which have state space of dimension n, and does
not depend on the size N of the graph.
The following technical lemmas are needed for the proof of Theorem 4.1.
Lemma 4.4 The synchronization region for the choice of K given earlier contains
the open circle C(1,r).
Proof By choosing the state feedback matrix as (4.15) with P>0 a solution of
equation (4.12), one has
ATPA−P+Q−KT(BTPB)K =0 (4.18)
From this equation, one obtains by completing the squares
ATPA-P+Q-KTBTPBK =(A-BK)T P(A-BK)-P+Q=0. (4.19)
Therefore, given the quadratic Lyapunov function V(y)= yTPy, y∈n, the choice
of feedback gain stabilizes the system (A,B). At least a part of the synchronization
region S can be found as
(A−sBK)*P(A−sBK)=(A−ResBK)TP(A−ResBK)+Im2s(BK)TPBK <P,
(4.20)
where * denotes a complex conjugate transpose (Hermitian adjoint), s∈. There-
fore, from equations (4.18) and (4.20) one has

| 4.4  Local Riccati Design of Synchronizing Protocols  |     |     | 115 |
| ----------------------------------------------------- | --- | --- | --- |

(A−sBK)*P(A−sBK)−P
= ATPA−P−s *KTBTPA−sATPBK+s*sKTBTPBK
2
| = ATPA−PP−2ResKTBTPBK+ |            | s KTBTPBK |     |
| ---------------------- | ---------- | --------- | --- |
| ATPA−P−(2Res−          | 2 )KTBTPBK |           |     |
= s
= ATPA−P−(1−− s−1 2 )(BK)TPBK
(4.21)
Inserting (4.19) into (4.21) yields
| (A−sBK)*P(A−sBK)−P=−Q+KTBTPBK−(1− |     | s−12)KTBTPBK |     |
| --------------------------------- | --- | ------------ | --- |
=−Q+ s−12KTBTPBBK.
This is the condition of stability if
s−12KTBTPBK
|     | Q−  | >0, | (4.22) |
| --- | --- | --- | ------ |
which gives a simple bounded complex region, more precisely a part of the complex
gain margin region U,
| s-12KTBTPBK | s-12σ ( | Q-T/2(BK)TP(BK)Q-1/2) |          |
| ----------- | ------- | --------------------- | -------- |
|   Q>        | ⇒1>     |                       | . (4.23) |
max
This is an open circle C(1,r) specified by
|     | 1       |     |        |
| --- | ------- | --- | ------ |
|     | s-1 2 < | .   | (4.24) |
( Q-T/2KTBTPBKQ-1/2)
σ
max
Furthermore, expressing K  as the H  Riccati equation state feedback completes
2
| the proof.  |     |     | □   |
| ----------- | --- | --- | --- |
Lemma 4.5 Given the circle C(1,r) in the complex plane, which is contained in
the synchronization region S for the Riccati choice of gain (4.15), the system is
guaranteed to synchronize for some value of c>0 if the graph matrix eigenvalues
Λ , k =1...N, are located in such a way that
k
|     | <r,∀k.  |     |     |
| --- | ------- | --- | --- |
cΛ −1 (4.25)
k
for that particular c in (4.16).
| Proof Follows from Lemmas 4.2, 4.3, and 4.4.  |     |     | □   |
| --------------------------------------------- | --- | --- | --- |
Based on these constructions, the proof of Theorem 4.1 can now be given.
Proof of Theorem 4.1 Given C(1,r) contained in the synchronization region S  of
c
matrix pencil  A-sBK, and the properties of dilation (homothety), and assuming

116 4  Riccati Design for Synchronization of Discrete-Time Systems
there exists a directed spanning tree in the graph with a nonzero pinning gain into
the root node, it follows that synchronization is guaranteed if all eigenvalues Λ  are
k
contained in a circle C(c ,r ) similar with respect to homothety to a circle concen-
0 0
tric with and contained within C(1,r).
The center of the covering circle c  can be taken on the real axis due to symme-
0
try and the radius equals r =maxΛ −c . Taking these as given, one should have
|     |     | 0   | k   | 0   |     |     |
| --- | --- | --- | --- | --- | --- | --- |
k

r r
|     |     |     |     | 0 < . |     | (4.26) |
| --- | --- | --- | --- | ----- | --- | ------ |
c 1
0
If this equation is satisfied, then choosing c=1/c
0  maps with homothety the cover-
ing circle of all eigenvalues C(c ,r ) into a circle C(1,r /c ) concentric with and,
|     |     |     | 0 0 |     | 0 0 |     |
| --- | --- | --- | --- | --- | --- | --- |
for r>r /c , contained in the interior of the circle C(1,r).  □
|     | 0 0 |     |     |     |     |     |
| --- | --- | --- | --- | --- | --- | --- |
If there exists a solution  P>0 to the Riccati equation (4.12), B must have full
column rank. Assuming B has full column rank, there exists a positive definite solu-
tion P to (4.12) only if (A, B) is stabilizable. This is a necessary condition for the
applicability of Theorem 4.1.
4.5  Robustness Property of Local Riccati Design
The following lemma is motivated by the conjecture that if the conditions of Theo-
rem 4.1 hold, there is in fact an open interval of admissible values for the coupling
constant c. This has the interpretation of robustness for the local Riccati design in
the sense that synchronization is still guaranteed under small perturbations of c
from the value given by (4.16).
Lemma 4.6 Taking α :=arccos 1−r2 ≥0  and denoting the angle of an eigen-
max
value of the graph matrix Γ by φ :=argΛ , a necessary condition for the existence
|     |     |     | k   | k   |     |     |
| --- | --- | --- | --- | --- | --- | --- |
of at least one admissible value of c is given by
ReΛ
|     |     |     | k > | 1−r2, ∀k, |     | (4.27) |
| --- | --- | --- | --- | --------- | --- | ------ |
Λ
k
which is equivalent to
|     |     |     | φ   | <α , ∀k. |     | (4.28) |
| --- | --- | --- | --- | -------- | --- | ------ |
k max
Furthermore, the interval of admissible values of c, if nonempty, is an open interval
given as a solution to a set of inequalities:
|     | cosφ − cos2φ | −cos2α |         | cosφ + cos2φ | −cos2α     |        |
| --- | ------------ | ------ | ------- | ------------ | ---------- | ------ |
|     | k            | k      | max <c< | k            | k max ,∀k. | (4.29) |
|     |              | Λ      |         |              | Λ          |        |
|     |              | k      |         |              | k          |        |

| 4.5  | Robustness Property of Local Riccati Design  |     |     |     |     |     |     |     | 117 |
| ---- | -------------------------------------------- | --- | --- | --- | --- | --- | --- | --- | --- |
Finally if (4.14) holds, then the solution set of (4.29) is nonempty and contains the
value (4.16).
Proof If solution c exists, the equations
|     |     |     |          |     | 2      |       |     |     |        |
| --- | --- | --- | -------- | --- | ------ | ----- | --- | --- | ------ |
|     |     | cΛ  | −1 <r⇒c2 | Λ   | −2cReΛ | +1−r2 | <0  |     | (4.30) |
|     |     | k   |          | k   |        | k     |     |     |        |
are satisfied simultaneously for every k for at least one value of c. Therefore, ∀k
(4.30) has an interval of real solutions for c. From that, and the discriminant of
(4.30), relation (4.27) follows.
ReΛ
One  therefore  has  cosφ = k > 1−r2 =cosα ,  meaning  φ <α .
|     |     |     | k   |     |     |     | max | k   | max |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
Λ
k
Bearing that in mind, expression (4.30) can further be equivalently expressed as
2
|     |     |     | c2 Λ | −2c Λ | cosφ +cos2α |     | <0. |     |     |
| --- | --- | --- | ---- | ----- | ----------- | --- | --- | --- | --- |
|     |     |     | k    | k     | k           | max |     |     |     |
Solving this equation for c Λ  yields  N  intervals in (4.29). The intersection of
k
these N  open intervals is either an open interval or an empty set.
| Now given that Λ |     |     | ∈C(c ,r | ) one finds that |     |     |     |     |     |
| ---------------- | --- | --- | ------- | ---------------- | --- | --- | --- | --- | --- |
|                  |     | k   | 0       | 0                |     |     |     |     |     |

|     |     | cosφ − | cos2φ  | −cos2α | cosφ | − cos2φ | −cos2α |     |     |
| --- | --- | ------ | ------ | ------ | ---- | ------- | ------ | --- | --- |
|     |     | k      | k      | max    | <    | k       | k max  |     |     |
|     |     |        | Λ      |        |      |         | Λ      |     |     |
|     |     |        | k      |        |      |         | k min  |     |     |
|     |     | cosφ + | coss2φ | −cos2α | cosφ | + cos2φ | −cos2α |     |     |
|     |     | k      | k      | max    | <    | k       | k max  |     |     |
(4.31)
|     |     |     | Λ     |     |     |     | Λ   |     |     |
| --- | --- | --- | ----- | --- | --- | --- | --- | --- | --- |
|     |     |     | k max |     |     |     | k   |     |     |
where  Λ , Λ  are extremal values for fixed φ , as determined by C(c ,r ).
|              | k min | k max |          |     |     | k   |     |     | 0 0 |
| ------------ | ----- | ----- | -------- | --- | --- | --- | --- | --- | --- |
| Namely, for  |       | Λ , Λ |  one has |     |     |     |     |     |     |
|              |       | k     | k        |     |     |     |     |     |     |
|              |       | min   | max      |     |     |     |     |     |     |
2
|     |     |      |     | Λ     | Λ    |          | r2   |     |     |
| --- | --- | ---- | --- | ----- | ---- | -------- | ---- | --- | --- |
|     |     | Λ −c | =r  | ⇒ k   | −2 k | cosφ +1− | 0 =0 |     |     |
|     |     | k    | 0 0 | c2    | c    | k        | c2   |     |     |
|     |     |      |     | 0     | 0    |          | 0    |     |     |
|     |     |      |    |       |     | r2     |      |     |     |
|     |     |      |     | cos2φ |      | 0        |      |     |     |
which gives Λ =c cosφ ± − 1−  . If (4.14) is satisfied, then
|     |     | k max,min | 0   | k   | k   | c2  |     |     |     |
| --- | --- | --------- | --- | --- | ----- | ----- | --- | --- | --- |
|     |     |           |   |     |       | 0     |   |     |     |
r2
| cos2α |     | 0   |     |     |     |     |     |     |     |
| ----- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
<1− , used in (4.31) together with the expression for  Λ , Λ  im-
|     | max | c2  |     |     |     |     | k min | k max |     |
| --- | --- | --- | --- | --- | --- | --- | ----- | ----- | --- |
0
plies the nonemptiness of the interval solution of (4.29) and guarantees that c=1/c
0
is a member of that interval. Furthermore, if the assumptions of Theorem 4.1 were
satisfied with equality, then the lower and higher limit of every subinterval (4.31)
| would in fact become equal to 1/c |     |     |     | .   |     |     |     |     | □   |
| --------------------------------- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
0
Condition (4.28) means that the graph matrix eigenvalues Λ  must be inside the
k
cone in the complex plane shown in Fig. 4.1. It is evident from the geometry of the
problem that eigenvalues Λ  located outside the cone determined by (4.27), (4.28)
k

118 4  Riccati Design for Synchronization of Discrete-Time Systems
cannot be made to fit into the region C(1,r) by scaling with real values of c. It
should be noted that condition (4.14) is stronger than condition (4.28) and condition
(4.29) has also been derived in [11].
4.6   Application to Real Graph Matrix Eigenvalues and
Single-Input Systems
In this section, condition (4.14) of Theorem 4.1 is studied in several, special, simpli-
fied cases and it is shown how this condition relates to known results.
4.6.1  Case of Real Graph Eigenvalues
The special case of real eigenvalues of Γ and single-input systems at each node al-
lows one to obtain the necessary and sufficient condition for synchronization.
Corollary 4.1 Let graph G(V,E) have a spanning tree with pinning into the root
node, and all eigenvalues of  Γ be real and positive, that is,  Λ >0 for all  k.
k
Define 0<Λ ≤≤Λ ≤≤Λ . A covering circle for Λ  that also minimizes
| min k | max |     | k   |     |
| ----- | --- | --- | --- | --- |
r/c  is C(c ,r ) with
0 0 0 0
  r Λ −Λ
|     | 0 = max | min. |     | (4.32) |
| --- | ------- | ---- | --- | ------ |
c Λ +Λ
|     | 0 max | min |     |     |
| --- | ----- | --- | --- | --- |
Then, condition (4.14) in Theorem 4.1 becomes
Λ −Λ
|     | max | min <r. |     |     |
| --- | --- | ------- | --- | --- |
(4.33)
  Λ +Λ
max min
Moreover, given that this condition is satisfied, the coupling gain choice (4.16) re-
duces to
  2
|     | c=  | .   |     | (4.34) |
| --- | --- | --- | --- | ------ |
Λ +Λ
|     | min | max |     |     |
| --- | --- | --- | --- | --- |
Proof For graphs having a spanning tree with pinning into the root node, and all
eigenvalues of Γ real, one has 0<Λ . Note that in that case φ =0 ∀k and
|     | min |     | k   |     |
| --- | --- | --- | --- | --- |
cos2α =1−r2 so that the necessary condition (4.28) is satisfied. Furthermore,
max
inequalities (4.29) become
|     | 1−r | 1+r |     |     |
| --- | --- | --- | --- | --- |
|     | <c< | .   |     |     |
|     | Λ   | Λ   |     |     |
|     | k   | k   |     |     |

4.6  Application to Real Graph Matrix Eigenvalues and Single-Input Systems  119
From this, a necessary and sufficient condition for the existence of a nonempty
| intersection of these N    |  intervals is |       |           |       |                   |       |
| -------------------------- | ------------- | ----- | --------- | ----- | ----------------- | ----- |
|                            |               | 1−r   | 1+r       |       |                   |       |
|                            |               |       | <         | ,     |                   |       |
|                            |               | Λ     | Λ         |       |                   |       |
|                            |               | min   | max       |       |                   |       |
| where the extremal values  |               | Λ = Λ | ,Λ        | = Λ   |   Λ = Λ           |  are  |
|                            |               | min   | k min max | k max | min,max k min,max |       |
the same for every k and are determined as in the proof of Lemma 4.6.
1-r 1+r
The sought interval is given as c∈ , . From this interval, one finds
|     |     |     | Λmin | Λmax |     |     |
| --- | --- | --- | ---- | ---- | --- | --- |
condition (4.33). Therefore, the sufficient condition (4.14) is equivalent to (4.33).
Examining the positions of eigenvalues on the real axis, it is found that for the mini-
| mal covering circle C(r | ,c  | ) one has |     |     |     |     |
| ----------------------- | --- | --------- | --- | --- | --- | --- |
0 0
|     |     |     | Λ +Λ |        |     |     |
| --- | --- | --- | ---- | ------ | --- | --- |
|     |     | c = | min  | max ,  |     |     |
0
2
where
|     |      |       |       | Λ −Λ  |      |     |
| --- | ---- | ----- | ----- | ----- | ---- | --- |
|     | r =Λ | −c =c | −Λ    | = max | min. |     |
|     | 0    | max 0 | 0 min |       |      |     |
2
Hence,
|     |     | Λ −Λ | r     |       |     |     |
| --- | --- | ---- | ----- | ----- | --- | --- |
|     |     | max  | min = | 0 <r. |     |     |
c
|     |     | Λ +Λ |     |     |     |     |
| --- | --- | ---- | --- | --- | --- | --- |
|     |     | max  | min | 0   |     |     |
Note that in the case of real eigenvalues Λ , their minimal covering circle has also
k
the minimal ratio r/c  of all covering circles C(c ,r ). This shows that (4.33) ex-
|     | 0 0 |     |     | 0 0 |     |     |
| --- | --- | --- | --- | --- | --- | --- |
presses the sufficient condition (4.14) specialized to Γ having all real eigenvalues.
| Theorem 4.1 then also gives the choice of c (4.34).  |     |     |     |     |     | □   |
| ---------------------------------------------------- | --- | --- | --- | --- | --- | --- |
This special case when the eigenvalues of the graph matrix Γ are real bears strong
resemblance to the case presented and studied in [11] concerning undirected graphs.
For, note that if one uses the non-weighted protocol u =cKε  instead of (4.4), then
i i
the eigenvalues Λ  used in the analysis of this chapter are those of (L+G), not Γ
k
in (4.10). However, the condition that the eigenvalues of (L+G) be real is equiva-
lent to the graph being undirected. It is noted that, even if all eigenvalues of (L+G)
are real, the eigenvalues of Γ may be complex and vice versa. The importance of
weighting is discussed in Lemma 4.1.
4.6.2  Case of Single-Input Agent Dynamics
The radius r in (4.13) for the Riccati-based design is important since it is instru-
mental in determining the sufficient condition (4.14) in Theorem 4.1 as well as the
condition in Lemma 4.6. In the case of single-input agent systems, the expression
(4.13) simplifies.

120 4  Riccati Design for Synchronization of Discrete-Time Systems
Remark 4.1 If the node dynamics (4.1) are single-input, define r by (4.13) with the
P*−ATP*A+ATP*BBTP*A, where P*
| choice of Q= |     | >0 is a positive definite solu- |     |
| ------------ | --- | ------------------------------- | --- |
BTP*B
tion of the Riccati equation
ATP*BBTP*A
P*-ATP*A+
|     |     | =0. | (4.35) |
| --- | --- | --- | ------ |
BTP*B+1
| Then, |        | 1   |        |
| ----- | ------ | --- | ------ |
|       | r =    | .   |        |
|       | ∏λu(A) |     | (4.36) |
|       | u      |     |        |
where λu(A) are the unstable eigenvalues of the system matrix A indexed by u.
▋
This follows from Theorem 2.2 of [2]. Namely, putting Q as defined into (4.12)
yields the solution P= P*. In case of single-input systems, B∈n and u is a scalar,
so the result in [2] applies. Note that if the solution to (4.35) is only positive semi-
definite, a regularizing term must be added to (4.35) as is done in [2].
Note that P* defined as a solution to Riccati equation (4.35) becomes the solu-
tion of (4.12) for the choice of Q given in Remark 4.1. This means, in the context of
this chapter, that the H  Riccati feedback gain for that specific choice of Q, applied
2
to single-input systems, maximizes the value of r considered here to be the radius
of C(1,r) in the complex plane, rather than just the real interval [2]. The following
remark combines the above results.
Remark 4.2 If systems (4.1) are single input and the  Γ matrix of the graph
G(V,E) has all eigenvalues real, then selecting Q as in Remark 4.1 gives the condi-
tion (4.14) in the form
Λ +Λ
|     | ∏λu(A) | < max min. | (4.37) |
| --- | ------ | ---------- | ------ |
Λ -Λ
|     | u   | max min |     |
| --- | --- | ------- | --- |
Moreover, this condition is necessary and sufficient for synchronization for any
choice of the feedback matrix K if all the eigenvalues of A lie on or outside the unit
circle. Sufficiency follows by Corollary 4.1 and Remark 4.1, assuming the condi-
| tions of Theorem 4.1 hold. Necessity follows from [11].  |     |     | ▋   |
| -------------------------------------------------------- | --- | --- | --- |
4.6.3   Mahler Measure, Graph Condition Number,
and Graph Channel Capacity
The term appearing in Remark 4.2 involving the product of unstable eigenvalues
|     | M(A)=∏ | λu(A) | (4.38) |
| --- | ------ | ----- | ------ |

i i

| 4.7  Cooperative Observer Design  |     |     | 121 |
| --------------------------------- | --- | --- | --- |
deserves further attention. M (A) is known as the Mahler measure of the respective
characteristic polynomial of A. It is related to the intrinsic entropy rate of a system
∑ log λu(A) describing the minimum data rate in a networked control system
2 i
i
that enables stabilization of an unstable system [11].
It is well recognized that intrinsic entropy is of importance in the stability analy-
sis of Kalman filtering with intermittent observations [9] and in the quadratic stabi-
lization of an uncertain linear system (cf. Theorem 2.1 of [3]).
We define the graph condition number as
Λ
|     | κ(Γ)= max |     | (4.39) |
| --- | --------- | --- | ------ |
Λ
min
In terms of the graph condition number, condition (4.37) is written as
-1
1+κ
M(A)<
|     |     | -1  | (4.40) |
| --- | --- | --- | ------ |
|     | 1-κ |     |        |
The topological entropy of a system is defined as
|     | h(A)=log(M(A)) |     | (4.41) |
| --- | -------------- | --- | ------ |
Motivated by this, we define the graph channel capacity as

1+κ-1
|     | C(Γ)=log |     | (4.42) |
| --- | -------- | --- | ------ |
1-κ-1
4.7  Cooperative Observer Design
In this section, we define cooperative observers that have a distributed structure on
the interaction graph G =(V,E). That is, the observer dynamics for each agent are
distributed in the sense that they respect the communication structure imposed by
the graph and can only use information from their neighbors. We provide a local
Riccati design method for the observer gains that guarantees convergence of the ob-
server errors to zero if a certain condition holds. Pinning control is used to provide
a fixed reference in terms of a node 0 to some of the agents. All other, non-pinned,
agent observers rely only on the relative output information of the neighbors.
N agents are assumed coupled on a graph G =(V,E) and have identical dynam-
ics given as the discrete-time systems
|     | x (k+1)= Ax (k)+Bu | (k) |        |
| --- | ------------------ | --- | ------ |
|     | i i                | i   |        |
|     | y (k)=Cx (k)       |     | (4.43) |
|     | i i                |     |        |

122 4  Riccati Design for Synchronization of Discrete-Time Systems
It is assumed that (A,C) is detectable and that C has full row rank. A control or
leader node 0 has the command generator dynamics
|     |     |     | x (k+1)= | Ax (k)      |     |     |        |
| --- | --- | --- | -------- | ----------- | --- | --- | ------ |
|     |     |     | 0        | 0           |     |     |        |
|     |     |     | y        | (k)=Cx (k). |     |     |        |
|     |     |     | 0        | 0           |     |     | (4.44) |
The state, input, and output vectors are x,x ∈n,u ∈m, y,y ∈p. Note that
|     |     |     |     | i 0 | i   | i 0 |     |
| --- | --- | --- | --- | --- | --- | --- | --- |
matrix A may not be stable. The autonomous command generator describes many
reference trajectories of interest including periodic trajectories, ramp-type trajecto-
ries, etc.
4.7.1  Distributed Neighborhood Observer Dynamics
It is desired to design cooperative observers that estimate the states  x(k), given
i
only measurements of the outputs  y (k) of the agent i itself and of its neighbors.
j
| Given an estimated output y(cid:19) |     |     | =Cx(cid:19) |     |     |     |     |
| ----------------------------------- | --- | --- | ----------- | --- | --- | --- | --- |
 at node i, define the local output estimation
i i
error as
|     |     |     | y  | = y −y(cid:19) . |     |     |     |
| --- | --- | --- | --- | ---------------- | --- | --- | --- |
|     |     |     | i   | i i              |     |     |     |
To construct an observer that takes into account information from the neighbors of
node i, define the local neighborhood output disagreement as

|     |     | εo =∑e |     |             |        |     |        |
| --- | --- | ------ | --- | ----------- | ------ | --- | ------ |
|     |     |        | (y | -y )+g (y | -y ), |     | (4.45) |
|     |     | i      | ij  | j i i       | 0 i    |     |        |
j
where the observer pinning gains are g ≥0, with g >0 only for a small percent-
|     |     |     |     | i   | i   |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- |
age of nodes that have direct measurements of the output error  y  of the control
0
node. With the global state vector defined as x=xT (cid:31)xT T ∈(cid:30)nN and global out-
|     |     |     |     |    | N  |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- |
1
put y= y T(cid:31)yT  T ∈(cid:30)pN, the global output disagreement error εo(k)∈pN is
|    |    |     |     |     |     |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- |
1 N
εo(k)=−(L+G)⊗I
|     |     |     | y(k)+(L+G)⊗I |     | (1⊗y | (k)). | (4.46) |
| --- | --- | --- | ------------- | --- | ----- | ----- | ------ |
|     |     |     | m             |     | m     | 0     |        |
Throughout this chapter it is assumed that x = xˆ , implying y ≡0, i.e., the control
|     |     |     |     | 0 0 |     | 0   |     |
| --- | --- | --- | --- | --- | --- | --- | --- |
node state is accurately known to its neighbors. This means that pinned nodes have
a fixed reference of 0, while others use relative information only. Then, define the
distributed neighborhood observer dynamics as
|     |                  |                   |     |            | )-1Fεo(k), |     |        |
| --- | ---------------- | ----------------- | --- | ---------- | ---------- | --- | ------ |
|     | x(cid:19) (k+1)= | Ax(cid:19) (k)+Bu |     | (k)-c (1+d | +g         |     | (4.47) |
|     | i                | i                 |     | i 1        | i i        | i   |        |
where F is an observer gain matrix and c  is a coupling gain. This algorithm has
1
)−1. The im-
local neighborhood output disagreement (4.45) weighted by (1+d +g
i i

| 4.7  | Cooperative Observer Design  |     |     |     |     |     | 123 |
| ---- | ---------------------------- | --- | --- | --- | --- | --- | --- |
portance of using this weighting is shown in Lemma 4.1 and illustrated in Example
4.1. The global distributed observer dynamics then has the form
(I+D+G)−1(L+G)⊗Fy(k)
|     | x(cid:19)(k+1)= | I ⊗Ax(cid:19)(k)+I |     | ⊗Bu(k)+c |     |     |     |
| --- | --------------- | ------------------ | --- | -------- | --- | --- | --- |
|     |                 | N                  |     | N        | 1   |     |     |
(I+D+G)−1(L+G)⊗FC](cid:19)x(k)+I
|     | x(cid:19)(k+1)=[I | ⊗A−c                      |     |     |     | ⊗Bu(k) |     |
| --- | ----------------- | ------------------------- | --- | --- | --- | ------ | --- |
|     |                   | N                         | 1   |     |     | N      |     |
|     |                   | +c (I+D+G)−−1(L+G)⊗Fy(k), |     |     |     |        |     |
1
where G=diag(g ,…,g ) is the diagonal matrix of pinning gains.
1 N
Define the ith state observer error as
|     |     |     |     | η (k)= x(k)−x(cid:19) | (k) |     |     |
| --- | --- | --- | --- | --------------------- | --- | --- | --- |
|     |     |     |     | i i                   | i   |     |     |
Then, the global observer error η=ηT (cid:31)ηT T ∈(cid:30)nN has the dynamics
|     |     |     |     |    | N  |     |     |
| --- | --- | --- | --- | --- | ---- | --- | --- |
1

(I+D+G)-1(L+G)⊗FC]η(k).
|     | η(k+1)=[I |     | ⊗A-c |     |     |     | (4.48) |
| --- | --------- | --- | ---- | --- | --- | --- | ------ |
|     |           |     | N    | 1   |     |     |        |
Denote the global observer system matrix as
.

|     |     | A   | = I ⊗A−c | (I+D+G)−1(L+G)⊗FC |     |     | (4.49) |
| --- | --- | --- | -------- | ----------------- | --- | --- | ------ |
|     |     | o   | N        | 1                 |     |     |        |
The weighted graph matrix is
Γ=(I+D+G)−1(L+G)
(4.50)

Lemma 4.7 If there exists a spanning tree in the communication graph  with pin-
ning into a root node, then L+G, and, hence, Γ is nonsingular, and both have all
their eigenvalues in the open right-half plane.
It is now desired to design the observer gains F to guarantee stability of the observer
errors, hence convergence of the estimates x(cid:19) (k) to the true states x(k). Unfortu-
|     |     |     |     |     | i   | i   |     |
| --- | --- | --- | --- | --- | --- | --- | --- |
nately, the stability of the observer error dynamics depends on the graph topology
through the eigenvalues Λ ,k =1...N  of graph matrix Γ as shown by the follow-
k
ing result.
Lemma 4.8 The global observer error dynamics (4.48) are asymptotically stable
if and only if ρ(A−cΛ
|     |     |     | FC)<1 for all eigenvalues Λ |     | , k =1...N of the graph  |     |     |
| --- | --- | --- | --------------------------- | --- | ------------------------ | --- | --- |
1 k k
eigenvalue matrix Γ=(I+D+G)−1(L+G).
Proof Perform on (4.48) a state-space transformation zo )η, where T
|     |     |     |     |     | =(T⊗I |     |  is  |
| --- | --- | --- | --- | --- | ----- | --- | ---- |
n
a matrix satisfying T−1ΓT =Λ with Λ being a block triangular matrix. The trans-
formed global observer error system is
|     |     |     | zo(k+1)=[I | ⊗A-cΛ⊗FC]zo(k) |     |     | (4.51) |
| --- | --- | --- | ---------- | -------------- | --- | --- | ------ |
|     |     |     |            | N              | 1   |     |        |

124 4 Riccati Design for Synchronization of Discrete-Time Systems
Therefore, (4.48) is stable if and only if I ⊗A−cΛ⊗FC is stable. This is equiv-
N 1
alent to matrices A−cΛ FC being stable for every k since Λ are the diagonal
1 k k
elements of matrix Λ. □
A necessary condition for the stability of (4.48) is detectability of (A,C). According
to Lemma 4.7, stability of A−cΛ FC implies detectability of (A,C) under the
1 k
Assumption 4.1, and Lemma 4.7.
4.7.2 Convergence Region
The concept of the synchronization region introduced in Sect. 4.2.2 has proven im-
portant for the design of state feedback gains for continuous-time and discrete-time
multi-agent systems that guarantee stability on arbitrary graph topologies. The next
definition provides a dual concept for observer design.
Definition 4.3 For a matrix pencil A−sFC, s∈, the convergence region is a
subset S ⊆ such that S ={s∈ρ(A−sFC)<1} .
o o
The convergence region may not be connected, but it is intimately related to the
complex gain margin region defined next.
Definition 4.4 The complex gain margin region U ⊆ for some stabiliz-
o
ing observer gain F, given a system (A,C), is a simply connected region in ,
U ={s∈ρ(A−sFC)<1} containing s=1.
o
Note that for a stabilizing observer gain F, one has the relation U ⊆S . The next
o o
result ties together Lemma 4.8 and the concepts introduced here.
Lemma 4.9 Matrices A−cΛ FC are stable for all eigenvalues Λ if and only
1 k k
if cΛ ∈S ,∀k.
1 k o
4.7.3 Local Riccati Cooperative Observer Design
Given a single-agent system (A,C), the convergence region depends on the local
observer gain matrix F. Therefore, the distributed observer design problem is to find
an F that yields a guaranteed convergence region or a complex gain margin region.
It will now be shown that selecting the local observer matrix F based on a local al-
gebraic Riccati equation gives a guaranteed gain margin region. Then, it remains to
check the relation of the graph matrix eigenvalues to the guaranteed gain margin re-
gion. Sufficient conditions for stable observer design are given in the next theorem.
Theorem 4.2 Given multi-agent systems (4.43) with (A,C) detectable, assume
that the interaction graph contains a spanning tree with at least one pinning gain
nonzero that connects into the root node. Let P>0 be a solution of the discrete-
time observer Riccati equation

| 4.7  Cooperative Observer Design                  |                            |               |     | 125    |
| ------------------------------------------------- | -------------------------- | ------------- | --- | ------ |
|                                                   | APAT −P+Q−APCT(CPCT)−1CPAT |               | =0, | (4.52) |
| where Q=QT >0. Choose the observer gain matrix as |                            |               |     |        |
|                                                   |                            | APCT(CPCT)−1. |     | (4.53) |
F =
Define
|     | (Q-T/2APCT(CPCT)-1CPATQ-1/2)]-1/2. |     |     |        |
| --- | ---------------------------------- | --- | --- | ------ |
| r   | :=[σ                               |     |     | (4.54) |
obs max
Then, the observer error dynamics (4.48) are stable if there exists a covering circle
C(c ,r ) of the graph matrix eigenvalues Λ , k =1...N such that
| 0 0 |     | k   |     |     |
| --- | --- | --- | --- | --- |
r
|     |     | 0 <r . |     | (4.55) |
| --- | --- | ------ | --- | ------ |
c obs
0
If (4.55) is satisfied, then taking the coupling gain
1
|     |     | c = |     | (4.56) |
| --- | --- | --- | --- | ------ |
1 c
0
makes the observer dynamics (4.48) stable.
The importance of Theorem 4.2 is that it decouples the local observer gain design at
each agent from the details of the interconnecting communication graph structure.
The observer gain is designed by each agent using the local Riccati equation (4.52),
and then the graph topology comes into the choice of the coupling gain through con-
dition (4.55). Unlike the continuous-time case discussed in Chap. 3, it is not always
possible to select F and c  to guarantee observer convergence on any graph with a
1
spanning tree. Indeed, condition (4.55) must be satisfied. This condition is a relation
between the properties of the communication graph and the instability properties of
the local agent dynamics.
The local Riccati design method in Theorem 4.2 is scalable, since it only de-
pends on the local-agent dynamics, which have state space of dimension n, and does
not depend on the size N of the graph.
The next technical lemma is needed in the proof of Theorem 4.2.
Lemma 4.10 The convergence region S  for the observer gain F given in Theorem
o
| 4.2 contains the circle C(1,r | ).  |     |     |     |
| ----------------------------- | --- | --- | --- | --- |
obs
Proof The observer Riccati equation (4.52) can be written as

|     | APAT −P+Q−F(CPCT)−1FT |     | =0. | (4.57) |
| --- | --------------------- | --- | --- | ------ |

126 4  Riccati Design for Synchronization of Discrete-Time Systems
Select any symmetric matrix P>0. Then
|   (AT −sCTFT)*P(AT | −sCTFT)−P            |     |     |
| ------------------ | -------------------- | --- | --- |
| APAT −P−s*FCPAT    | −sAPCTFT +s*sFCPCTFT |     |     |
=
| == APAT −P−2ResAPCT(CPCT)−1CPAT | +            | s2 APCT(CPCT)−1CPAT |        |
| ------------------------------- | ------------ | ------------------- | ------ |
| APAT                            | s2)FCPCTFT   |                     |        |
| = −P−(2RRes−                    |              |                     |        |
| = APAT −P−(1−                   | s−12)FCPCTFT |                     | (4.58) |
A sufficient condition for the stability of (A-sFC) is that this be less than zero.
Inserting (4.57) this is equivalent to
|     | −Q+ s−12FCPCTFT | <0  | (4.59) |
| --- | --------------- | --- | ------ |
This equation furnishes the bound
1
s−12
|     | <                       |     | (4.60) |
| --- | ----------------------- | --- | ------ |
|     | σ (Q−T/2F(CPCT)FTQ−1/2) |     |        |
max
Furthermore, expressing F as (4.53) one obtains
| s−12 | 1   |     |        |
| ---- | --- | --- | ------ |
|      | <   | =r2 | (4.61) |
σ (Q−T/2APCT(CPCT)−1CPATQ−1/2) obs
max
This is an open circle C(1,r ), and for s in that circle, ρ(AT −sCTFT)<1, but this
obs
also means that ρ(A−sFC)<1 since transposition does not change the eigenvalues
| of a matrix.  |     |     | □   |
| ------------- | --- | --- | --- |
The guaranteed circle of convergence  C(1,r ), being simply connected in the
obs
complex plane and containing s=1, is contained within the observer gain margin
region U .
o
Proof of Theorem 4.2. Given C(1,r ) contained in the convergence region S  of
obs o
matrix pencil A-sFC, and the properties of dilation (homothety), assuming there
exists a directed spanning tree in the graph with a nonzero pinning gain into the
root node, it is clear that synchronization is guaranteed if all eigenvalues Λ  are
k
contained in a circle C(c ,r ) similar with respect to homothety to a circle concen-
0 0
tric with and contained within C(1,r ). Homothety, as understood here, refers to a
obs
radial projection with respect to the origin, i.e., zero in the complex plane. That is,
it must be possible to bring C(c ,r ) into C(1,r ) by scaling the radii of all graph
0 0 obs
eigenvalues by the same constant multiplier.
The center of the covering circle c  can be taken on the real axis due to symmetry
0
and the radius equals r =maxΛ −c . Taking these as given, it is straightforward
0 k 0
| that one should have | k   |     |     |
| -------------------- | --- | --- | --- |
r r
0 < obs .
c 1
0

| 4.7  Cooperative Observer Design  |     |     |     |     |     | 127 |
| --------------------------------- | --- | --- | --- | --- | --- | --- |
If this equation is satisfied, then choosing c=1/c  maps with homothety the cover-
0
ing circle of all eigenvalues C(c ,r ) into a circle C(1,r/c ) concentric with and,
|     |     |     | 0 0 | 0   | 0   |     |
| --- | --- | --- | --- | --- | --- | --- |
for r>r/c, contained in the interior of the circle C(1,r ).  □
|     | 0 0 |     |     | obs |     |     |
| --- | --- | --- | --- | --- | --- | --- |
Note that in (4.52) there is a condition P>0, and so one must have C of full row
rank. A necessary condition for the existence of a solution P>0 to (4.52) is the
detectability of (A,C). Also, it should be remarked that if condition (4.55) is satis-
fied then the coupling gain has a robustness property just as detailed in Lemma 4.6.
For the sake of computational simplicity, the covering circle C(c ,r ) is used
0 0
to prove sufficiency. If, however, this covering circle is found not to satisfy (4.55),
there could be other covering circles satisfying this condition, e.g. those having
smaller r/c ratios.
|     | 0 0 |     |     |     |     |     |
| --- | --- | --- | --- | --- | --- | --- |
4.7.4  Duality on Graphs for Discrete-Time Cooperative Systems
In this section, a duality property is given for cooperative controllers and coopera-
tive observers on communication graphs, where c =c. In this discussion, it is nec-
1
essary to consider non-weighted controller and observer protocols given by

|     |     |     |    |     |    |     |
| --- | --- | --- | --- | --- | --- | --- |
Ax(k)+cBK∑e
|     | x(k+1)= |     | (x    | −x)+g (x | −x)(k), | (4.62) |
| --- | ------- | --- | ----- | -------- | -------- | ------ |
|     | i       | i   | ij    | j i i    | 0 i      |        |
|     |         |     | j∈Ni |          |         |        |

|     |     |     |    |     |    |     |
| --- | --- | --- | --- | --- | --- | --- |
xˆ (k+1)= Axˆ (k)+Bu (k)-c F∑e ( y(cid:27) -y(cid:27) ) +g (y(cid:27) -y(cid:27) )(k). (4.63)
|     | i   | i i | 1   | ij j i | i 0 i |     |
| --- | --- | --- | --- | ------ | ----- | --- |
|     |     |     |    |        |      |     |
|     |     |     |  j |        |      |     |
The next result details the duality property for the distributed controllers (4.62)
and observers (4.63). For this result, it is required that the interaction graph of the
observer be the same as the interaction graph for the control design, as assumed
throughout this chapter. Recall that the reverse graph ′ has the same nodes and
edges as , but with all edge arrows reversed.
Theorem 4.3 Consider a networked system of N  identical linear agents on a com-
munication graph  with dynamics (A,B,C) given by (4.43). Let the graph  be
balanced. Suppose that the feedback gain K  in protocol (4.62) stabilizes the global
tracking error dynamics having a closed-loop system matrix:
|     |     |       |              | .   |     |        |
| --- | --- | ----- | ------------ | --- | --- | ------ |
|     |     | A = I | ⊗A−c(L+G)⊗BK |     |     | (4.64) |
c N
Then the observer gain F = KT in protocol (4.63) stabilizes the global observer
error dynamics (4.48) with the closed-loop observer matrix
|     |     |       | ⊗AT −c(L+G)T | ⊗FBT, |     |        |
| --- | --- | ----- | ------------ | ----- | --- | ------ |
|     |     | A = I |              |       |     | (4.65) |
o N

128 4 Riccati Design for Synchronization of Discrete-Time Systems
for a networked dual system of N identical linear agents (AT,CT,BT) on the
reverse communication graph ′.
Proof Similar to the proof given in Sect. 3.5 for continuous-time systems. □
Although the duality result requires that weighting of (1+d +g )−1 is not used in
i i
this section, the importance of weighting is illustrated in Example 4.1.
4.8 Cooperative Dynamic Regulators for Synchronization
This section introduces cooperative dynamic regulators that guarantee state syn-
chronization by using knowledge of the local neighborhood output disagreement.
Complete state information is not assumed, and observation, either distributed
neighborhood or local, is used to estimate the local neighborhood state tracking er-
rors (4.3). Three different observer–controller architectures at node i are presented,
each of which yields a cooperative dynamic output feedback regulator that guaran-
tees cooperative tracking.
The observer graph and the controller graph do not need to be the same. In the
case that the observer and controller graph are not the same, the sufficient condi-
tions of Theorems 4.1 and 4.2 apply separately to the respective graphs. The follow-
ing results are derived under a reasonable simplifying assumption of having those
two graphs equal, but apply similarly to the more general case. The development
of this section is a discrete-time version of the continuous-time results in Sect. 3.6,
which were first published in [12]. The cooperative regulators should have an ob-
server at each node and a control law at each node based on the observer outputs.
In addition, the separation principle should hold. This is the case for the following
three system architectures.
4.8.1 Neighborhood Controller and Neighborhood Observer
In this architecture, the controller uses a distributed neighborhood feedback law
u =c(1+d +g )-1Kεˆ , (4.66)
i i i i
where
ε(cid:19) i =∑e ij (x(cid:19) j −x(cid:19) i )+g i (x(cid:19) 0 −x(cid:19) i ) (4.67)
j
is the estimated local neighborhood tracking error. The observer is also a distrib-
uted neighborhood observer of the form (4.47). Thus, both the controller and the
observer depend on the neighbor nodes.
The global state and estimate dynamics are given as

4.8  Cooperative Dynamic Regulators for Synchronization  129
  x(k+1)=(I ⊗A)x(k)−c (I+D+G)−1(L+G)⊗BK(x(cid:31)−x )(k) (4.68)
|     |     | N   | 2   |     | 0   |
| --- | --- | --- | --- | --- | --- |
x(cid:31)(k+1)=I ⊗A−c(I+D+G)−1(L+G)⊗FCx(cid:31)(k)+c(I+D+G)−1(L+G)⊗⊗Fy(k)
|     |  N | 1   |     |  1 |     |
| --- | --- | --- | --- | --- | --- |
(I+D+G)−1(L+G)⊗BK(x(cid:31)
|     | −c  |     | −x  | )(k) | (4.69) |
| --- | --- | --- | --- | ---- | ------ |
|     | 2   |     |     | 0    |        |
Note that the assumption  x(cid:31) = x  was used in (4.68). The global state error then
|     |     | 0   | 0   |     |     |
| --- | --- | --- | --- | --- | --- |
follows from
|     | x(k+1)=I | ⊗A−c                      | (I+D+G)−1(L+G)⊗BKx(k) |       |     |
| --- | --------- | ------------------------- | ---------------------- | ----- | --- |
|     |           |  N                       | 2                      |      |     |
|     |           | +c (I+D+G)−1(L+G)⊗BKK(h+x |                        | )(k), |     |
|     |           | 2                         |                        | 0     |     |
which yields the global error dynamics
(I+D+G)−1(L+G)⊗BK)δ(k)
|     | δ(k+1)=(I | ⊗A−c                     |     |     |     |
| --- | --------- | ------------------------ | --- | --- | --- |
|     |           | N                        | 2   |     |     |
|     |           | +c (I+D+G)−1(L+G)⊗BKη(k) |     |     |     |
2
|     |     | = Aδ(k)+Bη(k), |     |     | (4.70) |
| --- | --- | -------------- | --- | --- | ------ |
|     |     | c              | c   |     |        |
and
|     |           |      | (I+D+G)−1(L+G)⊗FC)η(k) |     |        |
| --- | --------- | ---- | ---------------------- | --- | ------ |
|     | η(k+1)=(I | ⊗A−c |                        |     |        |
|     |           | N    | 1                      |     | (4.71) |
= Aη(k).
o
The entire error system is then
|     |     | δ        | A  | B δ    |        |
| --- | --- | ---------- | --- | --------- | ------ |
|     |     |            | c   | c         |        |
|     |     |  (k+1)= |     |  (k).  | (4.72) |
|     |     | η        | 0  | A oη   |        |
This system is asymptotically stable, implying δ,η→0 asymptotically, under the
conditions detailed in Theorems 4.1 and 4.2. This guarantees synchronization of all
agents to the control node state.
4.8.2  Neighborhood Controller and Local Observer
In this architecture, the controller is of the distributed neighborhood form (4.66),
(4.67). On the other hand, the observers are now local, depending only on the local
agent dynamics according to
|     |     | x(cid:31) i (k+1)=Ax(cid:31) | i (k)+Bu | (k)+Fy (k) | (4.73) |
| --- | --- | ---------------------------- | -------- | ----------- | ------ |
i i

130 4  Riccati Design for Synchronization of Discrete-Time Systems
and do not use information from the neighbors. Then, the state observation error
| η   | = x −x(cid:19)  dynamics is |     |     |     |     |     |     |     |
| --- | --------------------------- | --- | --- | --- | --- | --- | --- | --- |
i i i
|     |     |     |     | η (k+1)=(A−FC)η |     |     | (k), |     |
| --- | --- | --- | --- | --------------- | --- | --- | ---- | --- |
|     |     |     |     | i               |     |     | i    |     |
or globally
|     |     |     | η(k+1)= |     | ⊗(A-FC)η(k). |     |     |     |
| --- | --- | --- | ------- | --- | ------------ | --- | --- | --- |
I
|     |     |     |     |     | N   |     |     | (4.74) |
| --- | --- | --- | --- | --- | --- | --- | --- | ------ |

Then, the overall error dynamics are
|     |     |     | δ     | A  | c     | B c       | δ   |        |
| --- | --- | --- | ------- | --- | ----- | --------- | ------ | ------ |
|     |     |     | (k+1)= |     |       |           | (k).   | (4.75) |
|     |     |     |       |     |       | ⊗(A -FC) |      |        |
|     |     |     |  η    |    | 0 I N |           |  η  |        |
Now, the observer gain F is simply selected using, for instance, Riccati design so that
(A-FC) is asymptotically stable. The feedback gain is selected by Theorem 4.1.
Then, under the hypotheses of Theorem 4.1, synchronization is guaranteed.
4.8.3  Local Controller and Neighborhood Observer
In this architecture, the controller is local of the form
|     |     |     |     |     | u =−Kx(cid:19) |     |     | (4.76) |
| --- | --- | --- | --- | --- | -------------- | --- | --- | ------ |
|     |     |     |     |     | i              | i   |     |        |
which does not depend on the neighbors. On the other hand, the observer is distrib-
uted and given by protocol (4.47), with
|     |     |     | εo=∑e |     | (y −y | )+g (y | −y ). |     |
| --- | --- | --- | ----- | --- | ------- | ------ | ------ | --- |
|     |     |     | i     |     | ij j    | i i    | 0 i    |     |
j
Note that instead of y  in (4.45), which is assumed identically equal to zero, here
0
one uses the control node output y . In global form this yields
0

|     | x(k+1)= |     | I ⊗Ax(k)−I |     | ⊗BKx(cid:19)(k) |     |     |     |
| --- | ------- | --- | ---------- | --- | --------------- | --- | --- | --- |
|     |         |     | N          |     | N               |     |     |     |
x(cid:19)(k+1)= I ⊗(A−BK)x(cid:19)(k)+cΓ⊗FCη(k))−c Γ⊗FCx (k). (4.77)
|                        |        |               | N                    |            |     | 1                 | 1            | 0      |
| ---------------------- | ------ | ------------- | -------------------- | ---------- | --- | ----------------- | ------------ | ------ |
| Expressing x,x(cid:19) |        |  through x,η= |                      | x-xˆ gives |     |                   |              |        |
|                        | x(k+1) | =             | I ⊗(A-BK)x(k)+I      |            |     | ⊗BKη(k)           |              |        |
|                        |        |               | N                    |            | N   |                   |              |        |
|                        | η(k+1) | =             | I ⊗(A-BK)x(k)+I      |            |     | ⊗BKη(k)-I         | ⊗(A-BK)xˆ(k) |        |
|                        |        |               | N                    |            | N   |                   | N            |        |
|                        |        |               | -cΓ⊗FCη(k)+cΓ⊗FCx    |            |     |                   | (k)          |        |
|                        |        |               | 1                    |            | 1   |                   | 0            |        |
|                        |        | =             | I ⊗(A-BK)η(k)+I      |            |     | ⊗BKη(k)-cΓ⊗FC(η-x |              | )(k)   |
|                        |        |               | N                    |            | N   |                   | 1            | 0      |
|                        |        | =(I           | ⊗A-cΓ⊗FC)η(k)+cΓ⊗FCx |            |     |                   | (k)          |        |
|                        |        |               | N                    | 1          |     | 1                 | 0            |        |
|                        |        | =             | Aη(k)+cΓ⊗FCx         |            | (k) |                   |              | (4.78) |
|                        |        |               | o                    | 1          | 0   |                   |              |        |

| 4.8  Cooperative Dynamic Regulators for Synchronization  |     |     |     |     |     |     |     | 131 |
| -------------------------------------------------------- | --- | --- | --- | --- | --- | --- | --- | --- |
Global tracking error dynamics now follows as

|     |     | δ(k+1)=(I |     | ⊗A)δ(k)-(I | ⊗BK)x(cid:19)(k). |     |     |     |
| --- | --- | --------- | --- | ---------- | ----------------- | --- | --- | --- |
(4.79)
|           |         |     |                | N       | N            |     |       |        |
| --------- | ------- | --- | -------------- | ------- | ------------ | --- | ----- | ------ |
| Using xˆ= | x-η=    | x-x | -η+x           | =δ-(η-x | ), one finds |     |       |        |
|           |         | 0   | 0              |         | 0            |     |       |        |
|           | δ(k+1)= |     | ⊗(A-BK)δ(k)+(I |         | ⊗BK)(η(k)-x  |     |       | (4.80) |
|           |         | I   |                |         |              |     | (k)). |        |
|           |         | N   |                |         | N            |     | 0     |        |
Neither (4.78) nor (4.80) are autonomous systems since an exogenous input
is present in the form of the control node state  x (k). However, if one looks at
0
|     |     |     |     |     |     |     | ϑ(k+1)= | ϑ(k)  |
| --- | --- | --- | --- | --- | --- | --- | ------- | ----- |
the  dynamics  of  ϑ(k)=η(k)-x (k),  it  follows  that  A and
|     |     |     |     | 0   |     |     | o   |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
δ(k+1)= I ⊗(A-BK)δ(k)+(I ⊗BK)ϑ(k). Or, more clearly written in matrix
|     | N   |     |     | N   |     |     |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
form
|     |     | δ     | I  | ⊗(A-BK) | I ⊗BKδ |      |      |        |
| --- | --- | ------- | --- | ------- | --------- | ---- | ---- | ------ |
|     |     |         | N   |         | N         |      |      |        |
|     |     | (k+1)=  |    |         |           |    | (k). | (4.81) |
|     |     |  ϑ  |     | 0       | A         | ϑ |     |        |
|     |     |         |    |         |           | o    |      |        |
The control gain K is simply selected using, e.g., Riccati design, so that (A-BK)
is asymptotically stable. The observer gain is selected by Theorem 4.2. Then, under
the hypotheses of Theorem 4.2, the synchronization δ→0 is guaranteed.
Note  that  the  observer  in  (4.77)  is  biased  since ϑ→0  implies  η→x .
0
Thus,  the  observers  effectively  estimate  the  tracking  errors,  converging  to
| x(cid:19)(k)= x(k)-x |     | (k)=δ(k). |     |     |     |     |     |     |
| -------------------- | --- | --------- | --- | --- | --- | --- | --- | --- |
| i                    | i   | 0 i       |     |     |     |     |     |     |
Remark 4.3 The three proposed observer–controller architectures differ in the
amount of information that must be exchanged between neighbors for observation
and control. When both the observer and the controller are distributed, each agent
requires a significant amount of computation and communication to produce the
estimate of its own state, since neighbor outputs need to be measured and state,
i.e., output, estimates need to be communicated between neighbors. In addition, the
control input requires all the estimated neighbor states. The local observers and the
distributed controller architecture require less computations and communication,
since the state of each agent is estimated using only its own inputs and outputs, and
only the state estimates need to be communicated between neighbors. The third
architecture using distributed estimation and local controllers is interesting because,
for control purposes, the agents do not need to communicate from their neighbor-
hoods, though communication is needed for distributed estimation. The specific
eigenvalues of  A-BK, A-FC, and  A ,A  that appear in the augmented state
o c
equations (4.72), (4.75), and (4.81) determine the time constants in each of the three
| architectures.  |     |     |     |     |     |     |     | ▋   |
| --------------- | --- | --- | --- | --- | --- | --- | --- | --- |

132 4  Riccati Design for Synchronization of Discrete-Time Systems
4.9  Simulation Examples
This section gives numerical examples that confirm the validity of the proposed
control laws for distributed synchronization and observer convergence. A multi-
agent system consisting of five identical discrete-time, linear, time-invariant agents
is considered. For these systems, feedback gains guaranteeing cooperative synchro-
nization control and observer gains for state observation convergence are designed.
The performance of the three proposed, distributed, dynamic compensator archi-
tectures in Sect. 4.7 is also investigated, with performance comparisons provided.
4.9.1   Example 4.1. Importance of Weighting in Control and
Observer Protocols
This example shows the importance of using the weighting (1+d +g )−1 in control
i i
law (4.4) and observer algorithm (4.47). Consider a set of five agents with dynamics
given by (4.43) with (A,B,C) in controllable canonical form
|  0    | 1 0       |  0        |           |
| ------ | --------- | ------------ | --------- |
|       |           |           |           |
| A= 0   | 0 1       | ,B= 0 ,C | =[0 0 1]. |
|       |           |           |           |
| −0.2 | 0.2 1.1 | 1        |           |
The control node has the dynamics (4.44). The control node is pinned into two of
the nodes, and the graph structure is given by G=diag(30,0,0,0,30) and
|     | 3      | −1 −1   | −1 0   |
| --- | ------- | ------- | ------- |
|     |        |         |        |
|     |         | −1 3 −1 | −1 0    |
|     |        |         |        |
| L=  | D−E=−1 | −1 3    | 0 −1   |
|     |        |         |        |
|     |        | 0 0 −1  | 2 −1  |
|     | 0      |         |        |
|     |        | −1 0    | −1 2   |
Figure 4.2a shows the non-weighted graph eigenvalues, that is, the eigenvalues
of  (L+G), along with their covering circle. Figure 4.2b shows the magnified
part of Fig. 4.2a containing the weighted counterparts, that is, the eigenvalues of
Γ=(I+D+G)−1(L+G), their covering circle. It also shows the observer conver-
gence region C(1,r ) displayed in dashes. Dashed lines marking a sector in com-
obs
plex plane depict the region wherein the eigenvalue covering circles should lie
so that they be scalable (homothetic) to the observer convergence region. It can
be verified that the non-weighted eigenvalues in Fig. 4.2a do not satisfy the suf-
ficient condition (4.14) given in Theorem 4.1, while the weighted eigenvalues in
Fig. 4.2b do.

4.9 Simulation Examples 133
Fig. 4.2 a Non-weighted graph eigenvalues and their covering circle b Weighted graph matrix
eigenvalues, their covering circle, and convergence region of the observer (dashed circle)

134 4 Riccati Design for Synchronization of Discrete-Time Systems
It is interesting that the non-weighted eigenvalues are real, while the weighted
eigenvalues here are complex.
4.9.2 Example 4.2. Three Cooperative Dynamic
Regulator Designs
This example gives a set of simulations for the cooperative tracker using the three
different controller–observer architectures in Sect. 4.7. The dynamics and the com-
munication graph used are the same as in Example 4.1.
Example 4.2a. Cooperative Tracker with SVFB
In this simulation, it is assumed that perfect state measurements are available. That
is, the control law (4.4) is used assuming full SVFB and the design of c, K is done
using a local Riccati design as in Theorem 4.1. The Q matrix is chosen as Q=0.2I .
3
This provides a baseline for comparison for the performance of the three dynamic
regulator designs given in Sect. 4.7. Figure 4.3 shows the state components of the
five nodes and the leader control node. Figure 4.4 shows the first components of the
state tracking errors. All nodes synchronize to the state of the leader.
Example 4.2b. Distributed Neighborhood Controllers and Observers
This simulation is for the case of distributed neighborhood controllers and observ-
ers given as in Sect. 4.7.1. Figure 4.5 depicts the first state components of all five
agents and the control node, as well as the first components of the tracking errors
δ and the first components of the observer errors η. Synchronization is achieved.
Example 4.2c. Neighborhood Controllers and Local Observers
This simulation is for the case of neighborhood controllers and local observers giv-
en in Sect. 4.7.2. Figure 4.6 depicts the first state components of all five agents and
the control node, as well as the first components of the tracking errors δ and the first
components of the observer errors η. Synchronization is achieved.
Example 4.2d. Local Controllers and Neighborhood Observers
This simulation is for the case of local controllers and neighborhood observers giv-
en in Sect. 4.7.3. Figure 4.7 depicts the first state components of all five agents and
the control node, as well as the first components of the tracking errors δ and the first
components of the observer errors η. Synchronization is achieved.

4.9 Simulation Examples 135
Fig. 4.3 States of the nodes First state component-perfect state measurements
and the control node with
perfect state measurements 1
a First state components,
0.8
b Second state components,
0.6
c Third state components
0.4
0.2
0
-0.2
-0.4
-0.6
-0.8
-1
a 0 5 10 15
Second state component-perfect state measurements
1
0.8
0.6
0.4
0.2
0
-0.2
-0.4
b 0 5 10 15
Third state component-perfect state measurements
1
0.9
0.8
0.7
0.6
0.5
0.4
0.3
0.2
0.1
0
c 0 1 2 3 4 5 6 7 8 9 10

136 4 Riccati Design for Synchronization of Discrete-Time Systems
Fig. 4.4 First state tracking Tracking error
error component with perfect 0.8
state measurements
0.6
0.4
0.2
0
-0.2
-0.4
-0.6
0 5 10 15
Note that the observer errors in Fig. 4.7c do not converge to zero since the observ-
ers estimate the tracking errors, and so converge to xˆ (k)= x (k)-x (k)=δ(k).
i i 0 i
Remark 4.4 It is interesting to compare the time constants of state synchronization
and estimate convergence for the three dynamic regulator architectures. These are
in accordance with Remark 4.3. Compared to perfect state measurement, distrib-
uted observers and controllers take almost twice as long for state synchronization
and almost that same for estimate convergence alone. The case of a neighborhood
controller and a local observer required the shortest time for state synchronization,
shorter even than in the case of a local controller and a neighborhood observer. For
the system considered, it appears to be more advantageous to make observation faster
by using a local observer, than to simplify the control law. Depending on the specific
eigenvalues generated from the choice of K and F, perhaps for some other system it
would be profitable to use a local controller with a distributed observer. ▋
4.10 Conclusion
This chapter provides conditions for achieving synchronization of identical dis-
crete-time state-space agents on a directed communication graph structure based on
a local agent Riccati equation design. The concept of the discrete-time synchroniza-
tion region in the z-plane is used. The result is expressed in terms of a radius com-
puted easily from the local H type Riccati equation solution given in Theorem 4.1.
2
It is shown in the single-input case that this approach yields known results in terms
of the Mahler measure and the graph condition number. In addition, local Riccati
design algorithms that do not depend on the topological properties of the graph were
given in Theorem 4.2 to design observer gains for cooperative systems on com-
munication graphs. A Riccati design for the controllers and observers guarantees

4.10 Conclusion 137
Fig. 4.5 Neighborhood First state component-distributed observer and controller
controllers and observers. 1.5
a First state components,
showing synchronization,
b First tracking error compo- 1
nents, c First observer error
components
0.5
0
-0.5
a 0 5 10 15
First tracking error component-distributed observer and controller
0.8
0.6
0.4
0.2
0
-0.2
-0.4
-0.6
0 5 10 15 20 25
b
First observer error component-distributed observer and controller
0.6
0.4
0.2
0
-0.2
-0.4
-0.6
-0.8
c 0 5 10 15

138 4 Riccati Design for Synchronization of Discrete-Time Systems
Fig. 4.6 Local observers First state component-local observer and distributed controller
and distributed controllers. 1.5
a First state components,
showing synchronization,
1
b First tracking error compo-
nents, c First observer error
components
0.5
0
-0.5
-1
a 0 5 10 15
First tracking error component-local observer and distributed controller
0.8
0.6
0.4
0.2
0
-0.2
-0.4
-0.6
0 5 10 15
b
First observer error component-local observer and distributed controller
0.6
0.4
0.2
0
-0.2
-0.4
-0.6
-0.8
c 0 1 2 3 4 5 6 7 8 9 10

4.10 Conclusion 139
Fig. 4.7 Local controllers First state component-distributed observer and local controller
1.5
and neighborhood observers.
a First state components,
showing synchronization,
1
b First tracking error compo-
nents, c First observer error
components 0.5
0
-0.5
-1
a 0 5 10 15
First tracking error component-distributed observer and local controller
0.8
0.6
0.4
0.2
0
-0.2
-0.4
-0.6
b 0 2 4 6 8 10 12 14 16 18 20
First observer error component-distributed observer and local controller
1.5
1
0.5
0
-0.5
-1
c 0 5 10 15

140 4 Riccati Design for Synchronization of Discrete-Time Systems
stability if a condition in terms of the graph eigenvalues and stability properties
of the local agent dynamics holds. A duality principle for distributed systems on
graphs was given. Three cooperative dynamic regulator designs were presented,
each using distributed feedback controllers and observers that use only the local
agent information available in the graph. All three guarantee synchronization of
multi-agent systems to the state of a control node using only output feedback. Fur-
thermore, the separation principle is shown to be valid in all three cases for multi-
agent systems on graphs. The results presented in this chapter could be extended to
time-varying graphs using the results available in the literature.
References
1. Duan Z, Chen G, Huang L (2009) Disconnected synchronized regions of complex dynamical
networks. IEEE Trans Automat Contr 54(4):845–849
2. Elia N, Mitter SK (2001) Stabilization of linear systems with limited information. IEEE
Trans Automat Contr 46(9):1384–1400
3. Fu M, Xie L (2005) The sector bound approach to quantized feedback control. IEEE Trans
Automat Contr 50(11):1698–1711
4. Hengster-Movric K, You K, Lewis FL, Xie L (2013) Synchronization of discrete-time multi-
agent systems on graphs using riccati design. Automatica, 49(2):414–423
5. Lewis FL, Vrabie D, Syrmos VL (2012) Optimal Control, 3rd Edn. Wiley, New York
6. Li Z, Duan Z, Chen G, Huang L (2010) Consensus of multiagent systems and synchroniza-
tion of complex networks: a unified viewpoint. IEEE Trans Circuits Syst I, Reg papers,
57(1):213–224
7. Li Z, Duan Z, Chen G (2011) Consensus of discrete-time linear multi-agent systems with ob-
server-type protocols. Discrete and Continuous Dynamical Systems, Series B 16(2):489–505
8. Pecora LM, Carroll TL (1998) Master stability functions for synchronized coupled systems.
Phys Rev Lett 80(10):2109–2112
9. Sinopoli B, Schenato L, Franceschetti M, Poolla K, Sastry S (2004) Kalman filtering with
intermittent observations. IEEE Trans Automat Contr 49(9):1453–1464
10. Wang XF, Chen G (2002) Pinning control of scale free dynamical networks. Physica A
310(3–4):521–531
11. You K, Xie L (2011) Network topology and communication data rate for consensusability of
discrete-time multi-agent systems. IEEE Trans Automat Contr 56(10):2262–2275
12. Zhang H, Lewis FL, Das A (2011) Optimal design for synchronization of coopera-
tive systems: state feedback, observer and output feedback. IEEE Trans Automat Contr
56(8):1948–1952

Chapter 5
Cooperative Globally Optimal Control
for Multi-Agent Systems on Directed
Graph Topologies
In Chaps. 3 and 4, we showed that locally optimal design in terms of Riccati equa-
tions can guarantee synchronization for cooperative multi-agents on graphs. In this
chapter, we examine the design of distributed control protocols that solve global
optimal problems for all the agents in the graph. In cooperative control systems on
graphs, it turns out that local optimality for each agent and global optimality for all
the agents are not the same. This chapter brings together stability and optimality
theory to design distributed cooperative control protocols that guarantee synchro-
nization and are also optimal with respect to a positive semidefinite global perfor-
mance criterion. A common problem in optimal decentralized control is that global
optimization problems generally require global information from all the agents,
which is not available to distributed controllers. In cooperative control of multi-
agent systems on graphs, each agent is only allowed to use distributed information
that respects the graph topology, that is, information about itself and its neighbors.
Global optimal control for multi-agent systems is complicated by the fact that the
communication graph topology interplays with agent system dynamics.
In this chapter, we use an inverse optimality approach together with partial sta-
bility to consider synchronization with globally optimal performance. Agents are
assumed identical with linear time-invariant dynamics. Directed communication
graphs of fixed topology are considered. Specially structured quadratic perfor-
mance indices are derived that capture the topology of the graph, allowing for glob-
ally optimal controllers that can be implemented using local distributed protocols.
A new class of digraphs is defined on which global optimal controllers exist
that are distributed in form, namely, those graphs whose Laplacian matrix has a
diagonal Jordan form. Such graphs are shown to admit distributed controllers that
solve global optimality problems for all agents on the entire graph. This structural
constraint can in fact be relaxed, and optimal cooperative controllers developed for
arbitrary digraphs, by allowing state-control cross-weighting terms in the perfor-
mance criterion.
The results in this chapter come from [7].
F. L. Lewis et al., Cooperative Control of Multi-Agent Systems, 141
Communications and Control Engineering, DOI 10.1007/978-1-4471-5574-4_5,
© Springer-Verlag London 2014

142 5 Cooperative Globally Optimal Control for Multi-Agent Systems …
5.1 Stability, Local Optimality, and Global Optimality for
Synchronization Control on Graphs
The relations between stability and optimality have long been debated in the com-
munity and are now understood for single-agent systems. However, relations of
stability and optimality in multi-agent cooperative control systems are only now
beginning to be clarified. There are more intriguing relations between stability and
optimality in cooperative control than appear in the single-agent case, since local
stability and global team stability are not the same, and local agent optimality and
global team optimality are not the same. New phenomena appear that are not pres-
ent for single-agent systems. Moreover, throughout everything synchronization of
the states of all agents must be guaranteed.
In cooperative multi-agent control on graphs, any admissible control protocols
must be distributed in the sense that they use only information locally available to
an agent on the prescribed graph topology. Specifically, distributed control proto-
cols are allowed to depend only on information about the agent and its direct neigh-
bors. The communication restrictions imposed by graph topologies can severely
limit what can be accomplished by local distributed control protocols at each agent.
Chapters 3 and 4 showed that local optimal design of distributed protocols at each
agent can guarantee global stability, or synchronization, in multi-agent systems on
communication graphs.
In this chapter, we consider the global optimality of local distributed control
protocols in terms of the overall performance of the team of all agents. It is seen that
globally optimal performance cannot in general be guaranteed for standard linear-
quadratic regulator (LQR) performance measures by using distributed control pro-
tocols for arbitrary digraphs. For linear distributed agent control protocols to yield
global optimal team behaviors, the graph topology must satisfy certain conditions.
These conditions are shown to define a new class of digraphs that admit global
optimal control design using distributed control protocols. If these conditions are
satisfied, moreover, any admissible global performance indices must be selected in
a certain manner that depends on the graph topology. This clarifies the interactions
between stability, optimal performance, and the communication graph topology in
multi-agent systems.
Cooperative optimal control has been considered by many authors—[2–5, 12,
13] to name just a few. Optimality of a control protocol gives rise to desirable
characteristics, such as gain and phase margins, that guarantee robustness in the
presence of some types of disturbances [6, 9]. The common difficulty, however, is
that in the general case optimal control is not distributed [3, 4]. Solution of a global
optimization problem generally requires centralized, i.e., global, information. In or-
der to have local distributed control that is optimal in some sense, it is possible, e.g.,
to consider each agent optimizing its own, local, performance index. This is done
for receding horizon control in [5], implicitly in [17], and for distributed games on
graphs in [15], where the notion of optimality is Nash equilibrium. In [13], the LQR
problem is phrased as a maximization problem of linear matrix inequalities (LMIs)

5.2 Graph Definitions 143
under the constraint of the communication graph topology. This is a constrained
optimization taking into account the local character of interactions among agents. It
is also possible to use a local observer to obtain the global information needed for
the solution of the global optimal problem, as is done in [4]. In the case of agents
with identical linear time-invariant dynamics, [2] presents a suboptimal design that
is distributed on the graph topology.
In this chapter are considered fixed topology directed graphs and linear time-
invariant agent dynamics. A new class of digraphs is defined, namely those whose
Laplacian matrix is simple, i.e., it has a diagonal Jordan form. On these graphs, the
globally optimal LQR problem has a distributed linear protocol solution. If this
condition is satisfied, then distributed linear protocols exist that solve the global
optimal LQR problem only if the performance indices are of a certain form that
captures the topology of the graph. That is, the achievable optimal performance
depends on the graph topology.
The structure of the chapter is the following: Sect. 5.2 introduces graph theory
concepts and some definitions that are used throughout the chapter. More infor-
mation on graphs appears in Chap. 2. Section 5.3 deals with stability of possibly
noncompact invariant consensus manifolds and defines the notion of partial stabil-
ity. Section 5.4 introduces conditions of optimality and inverse optimality suitable
for the study of synchronization on graphs where the consensus manifold may not
be compact. These results are applied in Sects. 5.5 and 5.6. Section 5.5 discusses
globally optimal leaderless consensus and then pinning control to a leader node for
single-integrator agent dynamics. We call these respectively the cooperative regula-
tor and the cooperative tracker problems. Section 5.6 gives global optimality results
for general linear time-invariant agent dynamics.
In Sects. 5.5 and 5.6, it is found that optimality for the standard LQR perfor-
mance index is only possible for graphs whose Laplacian matrix satisfies a certain
condition. In Sect. 5.7, this condition is further discussed and shown to be satisfied
by certain classes of digraphs, specifically for those graphs whose Laplacian matrix
has a diagonal Jordan form. This condition holds in particular for undirected graphs.
In Sect. 5.8, a more general performance index is considered which has state-
control cross-weighting. It is shown that, with proper choice of the performance
index, optimal cooperative control of distributed form can be achieved for any di-
rected graph. This shows that performance indices with state-control cross-weight-
ing terms are in some sense more natural for cooperative control on communication
graphs.
5.2 Graph Definitions
Consider a graph  =(,) with N vertices  ={v ,(cid:31),v } and a set of edges
1 N
or arcs  ⊆×. It is assumed that the graph is simple, i.e., there are no repeat-
ed edges or self-loops (v,v )∉,∀i. Directed graphs are considered. Denote the
i i
connectivity matrix as E=[e ] with e >0 if (v ,v )∈ and e =0 otherwise.
ij ij j i ij

144 5 Cooperative Globally Optimal Control for Multi-Agent Systems …
The set of neighbors of node v is  ={v :(v ,v )∈}, i.e., the set of nodes
i i j j i
with arcs incoming into v. Define the in-degree matrix as D=diag(d …d ) with
i 1 N
d =∑e the (weighted) in-degree of node i (i.e., the ith row sum of E). Define
i ij
j
the graph Laplacian matrix as L= D−E. A path from node v to node v is a
i1 ik
sequence of edges (v v ),(v v ),…(v ,v ), with (v ,v )∈ or (v ,v )∈
i1, i2 i2, i3 ik−1 ik i j-1 i j i j i j-1
for j∈{2,…,k}. A directed path is a sequence of edges (v v ),(v v ),…(v ,v ),
i1, i2 i2, i3 ik−1 ik
with (v ,v )∈ for j∈{2,…,k}. The graph is said to be connected if every
i i
j-1 j
two vertices can be joined by a path. A graph is said to be strongly connected if
every two vertices can be joined by a directed path. The graph is said to contain a
(directed) spanning tree if there exists a vertex such that every other vertex in V
can be connected by a (directed) path starting from it. Such a special vertex is then
called a root node. The Laplacian matrix L has a simple zero eigenvalue if and only
if the undirected graph is connected, or the directed graph contains a spanning tree.
A bidirectional graph is a graph satisfying e >0⇔e >0. A detail balanced
ij ji
graph is a graph satisfying λe =λe for some positive constants λ...λ . By
i ij j ji 1 N
summing over the index i it is seen that then λ
1
…λ
N
 is a left eigenvector for
the zero eigenvalue of L. The Laplacian matrix of a detail balanced graph satisfies
L=ΛP, for some diagonal matrix Λ>0 and P= PT a Laplacian matrix of some
undirected graph. That is, the Laplacian L is symmetrizable. In fact Λ=diag(1/λ)
i
works. The concept of a detail balanced graph is related to the reversibility of an
associated Markov process.
For any matrix A, σ (A), σ (A) are minimal and maximal singular values
min max
of A, respectively. For a positive semidefinite matrix A, σ (A) denotes the
>0min
minimal nonzero singular value. Note that for symmetric L, σ (L)=λ(L), the
>0min 2
graph Fiedler eigenvalue.
5.3 Partial Asymptotic Stability
This section presents concepts of partial stability applied to noncompact manifolds.
The definitions are based on neighborhoods of a manifold and avoid the need for
global coordinates, in contrast to usual formulation of partial stability, e.g., [6]. The
fact that a manifold to which convergence is to be guaranteed is noncompact means
that usual approaches for compact manifolds based on proper Lyapunov functions
are not applicable as such. Furthermore when dealing with noncompact manifolds
one makes the distinction between nonuniform and uniform stability.
Let the system dynamics be given as
x = f(x,u)= f(x)+g(x)u, (5.1)
where f(x),g(x), and u(t) are assumed to be such that the existence of a unique
solution to the initial value problem is guaranteed.

5.3 Partial Asymptotic Stability 145
Definition 5.1 A neighborhood (S) of a manifold S is an open set in an embed-
ding space X containing the manifold S in its interior.
Definition 5.2 An ε-neighborhood of a manifold S ⊂(S) is defined as
 (S)={x∈X d(x,S)<ε}, where d(x,S):=infd(x,y) is the distance of a point
ε
y∈S
from the manifold S as given by the distance function d of the embedding space.
Note that in the case of compact manifolds any neighborhood (S) contains some
ε-neighborhood, but in the case of noncompact manifolds this need not be true. For
the needs of defining stability of noncompact manifolds, one uses neighborhoods
that contain some ε-neighborhood. We call such neighborhoods regular.
Definition 5.3 A manifold S is said to be (Lyapunov) stable if there exists a
regular neighborhood (S), S ⊂(S), such that for every ε-neighborhood
 (S) contained in it there exists a subneighborhood (S) satisfying the property
ε
x(0)∈(S)⇒x(t)∈ (S) ∀t≥0. If (S) can be taken as the entire state space
ε
embedding the manifold S, then the stability is global.
If a manifold is Lyapunov stable and furthermore there exists a neighborhood (S)
satisfying the property x(0)∈(S)⇒d(x(t),S)→0 as t→∞, then the manifold
S is asymptotically stable.
If a manifold is Lyapunov stable and for every ε-neighborhood  (S), a per-
ε
taining subneighborhood (S)⊆ (S) contains a δ-neighborhood  (S) then it
ε δ
is uniformly stable. And the stability conclusion can be phrased as ∀ε>0 ∃δ>0
such that d(x(0),S)<δ⇒d(x(t),S)<ε∀t≥0.
If a manifold is uniformly stable and asymptotically stable so that a neigh-
borhood (S) contains a δ-neighborhood  (S) satisfying the property
δ
x(0)∈ (S)⇒d(x(t),S)→0 as t→∞, uniformly ∀�x(0)∈ (S), then it is
δ δ
uniformly asymptotically stable.
If a manifold is uniformly asymptotically stable and there exist constants
K,σ >0 such that d(x(t), S)≤Kd(x(0), S)e−σt, for x(0) in some δ-neighbor-
hood  (S) then the stability is exponential.
δ
A sufficient condition for the various types of stability of a manifold, possibly
noncompact, is given as the following theorem, motivated by [6], Chap. 4. See that
reference for the basic definitions used here.
Theorem 5.1 Partial Stability Given a manifold S, possibly noncompact, con-
tained in a neighborhood ⊃S, if there exists a C1 function V :→(cid:25) and a 
class function α such that
V(x)=0⇔ x∈S
V(x)≥α(d(x,S)) for x∈\S
V(cid:28)(x)≤0 for x∈
then S is Lyapunov stable. If furthermore there is a  class function β such that
α(d(x,S))≤V(x)≤β(d(x,S))

146 5 Cooperative Globally Optimal Control for Multi-Agent Systems …
then the stability is uniform. If in addition there is a  class function γ such that
V(x)<−γ(d(x,S))
then the stability is uniformly asymptotic. If there exist a,b,c,p>0 such that
ad(x,S)p ≤V(x)≤bd(x,S)p
V(x)<−cd(x,S)p
then the stability is exponential.
Proof Take any  (S), then on the boundary ∂ (S) one has d(x,S)=ε yield-
ε ε
ing a bound V(x)≥ α(ε). Taking η= α(ε) and defining  ={x∈(S)V(x)<η}
η
one has for x∈ that α(d(x,S))<η meaning that d(x,S)< ε which implies
η
that  ⊆ (S). Taking x(0)∈ , owing to the nonincreasing property of V(x),
η ε η
one obtains
α(d(x(t),S))≤V(x(t))≤V(x(0))< α(ε),∀t≥0
This guarantees x(t)∈ (S)∀t≥0, proving the Lyapunov stability of S.
ε
However, there is no guarantee that, due to noncompactness, one does not have
inf d(x,S)= 0 which means that the η level set of V(x) is not bounded away
x∈∂
fromη the manifold S. This is remedied by the uniformity requirement since then
one can choose δ>0 such that β(δ)=α(ε), and by the previous argument for
x(0)∈ (S)
δ
α(d(x(t),S))≤V(x(t))≤V(x(0))<β(δ)=α(ε),
Asymptotic and exponential stability follow from the proof analogous to partial
stability results in [6]. □
The purpose of  class functions is to bind the level sets of the Lyapunov function
away from the manifold and away from infinity, allowing the interpretation of a
value of the Lyapunov function as a measure of the distance from the manifold. For
global conclusions one would require  , as an analog of properness, i.e., radial
∞
unboundedness.
Remark 5.1 Note that the uniformity property is always found in the case where
the manifold S is compact. However, since we are dealing with a noncompact man-
ifold here, the difference needs to be emphasized. Theorem 5.1 will be used together
with the inverse optimality approach of the next section, to guarantee asymptotic
stabilization to a consensus manifold that is also optimal. ▋
Remark 5.2 In case the partial stability conditions are satisfied, one does not nec-
essarily have bounded trajectories. Trajectories are constrained to a noncompact set,
and finite escape to infinity, while remaining in the noncompact neighborhood of S,
is thereby not precluded. Therefore, in order to avoid such an occurrence, one needs
to independently impose that solutions can be extended for all time. Since linear
systems are globally Lipschitz solutions cannot escape to infinity in finite time.
However, in more general cases, with nonlinear dynamics, an additional, proper,

| 5.4  | Inverse Optimal Control  |     |     |     | 147 |
| ---- | ------------------------ | --- | --- | --- | --- |
Lyapunov function could be used to guarantee boundedness of trajectories to a com-
pact set. Note that this does not contradict the stability of a noncompact set, since
La Salle invariance principle can be used to guarantee convergence to (a subset of)
| such a set.  |     |     |     |     | ▋   |
| ------------ | --- | --- | --- | --- | --- |
Remark 5.3 The stability properties presented in this coordinate free topological
setting are based on properties of neighborhoods of a manifold S. These properties
are not preserved by general homeomorphisms or even diffeomorphisms, since it is
easy to construct a diffeomorphism that maps a regular neighborhood onto one that
is not regular. In fact, the convergence of trajectories can be changed by a proper
choice of a mapping. The sufficient condition for a homeomorphism h to preserve
the stability properties of a manifold S, i.e., to preserve the regularity of neighbor-
hoods (S) and convergence of trajectories, is that there exist  class functions
α,β such that
|     |     | α(d(x,S))≤d(h(x),h(S))≤ | β(d(x,S)) |     |     |
| --- | --- | ----------------------- | --------- | --- | --- |
on the domain of h. This is fulfilled in particular by homeomorphisms that are uni-
formly continuous and have uniformly continuous inverse, although this condition
is not necessary.
Note that the requirements on the Lyapunov function specialize in case of com-
pact manifolds to familiar conditions [6]. In this case, all bounded open neighbor-
hoods are precompact. Specifically when one considers an equilibrium point, the
conditions specialize to
) for  x∈\{0}, V(cid:28)
|     | V(x)=0⇔ | x=0, V(x)≥α( | x   | ≤0 for x∈�. |     |
| --- | ------- | ------------ | --- | ------------ | --- |
In case of linear systems and pertaining quadratic partial stability Lyapunov func-
xTPx≥0, the target manifold is the null space of the positive semi-
tions V(x)=
definite matrix  P. Also the uniformity condition is automatically satisfied since
| σ                     | 2 yTPy≤ | σ 2, where  | y∈kerP⊥, and  |                            |     |
| --------------------- | ------- | ----------- | ------------- | -------------------------- | --- |
|                       | y ≤     | y           |               | y  serves as the distance  |     |
| min>0                 |         | max         |               |                            |     |
| from the null space.  |         |             |               |                            | ▋   |
5.4   Inverse Optimal Control
This section presents inverse optimality notions for specific application to the con-
sensus problem, where the consensus manifold may be noncompact. Inverse opti-
mality is a property of a stabilizing control u= φ(x), e.g., guaranteed by a control
Lyapunov function V(x), that is optimal with respect to some positive (semi) defi-
nite performance index. Let the system be given by the affine-in-control form

|     |     | x = f(x,u)= | f(x)+g(x)u. |     | (5.2) |
| --- | --- | ------------ | ----------- | --- | ----- |
Certain results of optimal control can be explicitly derived for systems in this form,
e.g., Hamilton–Jacobi–Bellman (HJB) equation.

148 5 Cooperative Globally Optimal Control for Multi-Agent Systems …
5.4.1 Optimality
The following lemma details the conditions for optimality of a stabilizing control
under an infinite horizon criterion [6].
Lemma 5.1 Optimality Consider the control affine system (5.2). Let S be a target
manifold, possibly noncompact. Given the infinite horizon optimality criterion
∞
J(x
0
,u)=∫(x,u)dt (5.3)
0
If there exist functions V(x), φ(x), and  class functions α,γ satisfying the fol-
lowing conditions:
V(x)=0⇔ x∈S
V(x)≥α(d(x,S))
φ(x)=0⇐x∈S
∇V(x)T f(x,φ(x))≤-γ(d(x,S))
H(x,φ(x))=0
H(x,u)≥0
with H(x,u)=(x,u)+∇V(x)T f(x,u). Then the feedback control u= φ(x) is op-
timal with respect to the performance index (5.3) and asymptotically stabilizing
with respect to the target set S. Furthermore the optimal value of the performance
index is
J(x ,φ(x))=V(x(0)).
0
Conditions 1, 2, and 4 show that V(x) is a control Lyapunov function for the
closed-loop system guaranteeing asymptotic stability of the set S, by Theorem 5.1.
If S is taken as a point, i.e., a compact manifold of dimension zero, then those
conditions become the familiar conditions on the Lyapunov function stabilizing an
equilibrium point
V(0)=0
V(x)≥α( x )x≠0
φ(0)=0
∇V(x)T f(x,φ(x))<0.

5.4 Inverse Optimal Control 149
5.4.2 Inverse Optimality
If the feedback control u= φ(x) is uniformly asymptotically partially stabilizing,
then there exists a partial stability Lyapunov function V(x) satisfying the condi-
tions 1, 2, and 4 of Lemma 5.1 by the converse Lyapunov theorems [6, 14].
In inverse optimality settings an asymptotically stabilizing control law u= φ(x)
is given. Then the performance integrand (x,u) and Lyapunov function V(x) are
to be determined. In this chapter, we are concerned with nonnegative performance
index integrands, so this is to be contrasted with the more general inverse optimality
where the performance integrand need not be nonnegative, as long as it guarantees a
stabilizing control. That the performance integrand must be positive (semi) definite
imposes constraints on V(x).
The next result formulates inverse optimality in a special form required for the
proofs of our main results.
Lemma 5.2a Inverse optimality Consider the control affine system (1). Let
u= φ(x) be a stabilizing control, with respect to a manifold S. If there exist scalar
functions V(x) and L(x) satisfying the following conditions:
1
V(x)=0⇔ x∈S
V(x)≥ α(d(x,S))
L(x)≥γ(d(x,S))
1
1
L(x)+∇V(x)T f(x)− ∇V(x)Tg(x)R−1g(x)T∇V(x)=0 (5.4)
1 4
1
(cid:31)φ(x)=- R-1g(x)T∇V(x)
2
then u= φ(x) is optimal with respect to the performance index with the integrand
(x,u)= L(x)+uTRu. Moreover, the optimal value of the performance criterion
1
equals J(x ,φ(x))=V(x ).
0 0
Proof Assume one has an optimal control problem (5.2), (5.3) with the optimality
performance integrand in (5.3) (x,u)= L (x)+uTRu. Then Lemma 5.1 states that
1
the solution of optimal problem can be obtained by forming the Hamiltonian
H(x,u)= L(x)+uTRu+∇V(x)T(f(x)+g(x)u).
1
This gives the optimal control in form of
∂
H(x,u)=2uTR+∇V(x)Tg(x)=0
∂u

150 5 Cooperative Globally Optimal Control for Multi-Agent Systems …
1
u= φ(x)=− R−1g(x)T∇V(x)
2
This feedback control vanishes on the set S since the gradient ∇V(x) equals zero
there. The Hamiltonian evaluated at this optimal control equals zero since
1
H(x,φ(x))= L(x)+∇V(x)T f(x)− ∇V(x)Tg(x)R−1g(x)T∇V(x)=0.
1 4
The Hamiltonian can then be concisely written in quadratic form
H(x,u)= L +uTRu+ ∇VT f +∇VTgu
1 
1 T -1 T
=-L1+ ∇V gR g ∇V
4
1
=uTRu+ ∇VTgR-1gT∇V +∇VTgu
4 
T
T =-2φ(cid:31) Ru
=(cid:31)φ Rφ(cid:31)
=(u-φ)TR(u-φ)≥0.
The value of the performance criterion then follows as
∞ ∞ ∞ ∞ ∞
dV
J = ∫(x,u)dt =−∫∇V(x)T f(x,u)dt+∫H(x,u)dt =−∫ dt+∫H(xx,u)dt
dt
0 0 0 0 (cid:31)0(cid:29)(cid:29)(cid:29)(cid:29)(cid:30)(cid:29)(cid:29)(cid:29)(cid:29)(cid:28)
≥0
∞
=V(x )−V(x(t→∞))+∫H(x,,u)dt
0 (cid:31)(cid:29)(cid:29)(cid:29)(cid:29)(cid:29)(cid:30)(cid:29)(cid:29)(cid:29)(cid:29)(cid:29)(cid:28)
→0 (cid:31)0(cid:29)(cid:29)(cid:29)(cid:29)(cid:30)(cid:29)(cid:29)(cid:29)(cid:29)(cid:28)
≥0
The optimum is reached precisely at u= φ(x), for which the integral on the right
side vanishes, and by asymptotic stability assumption V(x(t))→0; thus the optimal
value of the performance criterion equals J*(x )= J(x ,φ(x))=V(x ). □
0 0 0
That this optimal feedback control u= φ(x) is stabilizing follows also from the
Lyapunov equation
1
V(x)=∇VT f +∇VTgu=∇VT f − ∇VTgR−1gT∇V
2
1 1
=−L + ∇VTgR−1gT∇V − ∇VTTgR−1gT∇V
1
4 2
1
=−L (x)− ∇VTgR−1gT∇V ≤−L (x)≤−γ(d(x,S))
1 1
4
By the assumptions of Lemma 5.2a, the Lyapunov function V(x) satisfies all the
conditions of the Theorem 5.1 for partial stability.

| 5.4  Inverse Optimal Control           |     |           |                            | 151 |
| -------------------------------------- | --- | --------- | -------------------------- | --- |
|                                        |     |           | xTQx, V(x)= xTPx, the HJB  |     |
| In the linear quadratic case, i.e., x |     | = Ax+Bu,L | =                          |     |
1
Eq. (5.4) becomes the Algebraic Riccati equation (ARE)

|     | Q+ATP+PA−PBR−1BTP=0. |     |     | (5.5) |
| --- | -------------------- | --- | --- | ----- |
The next more general result allows state-control cross-weighting terms in the per-
formance integrand . This result is used in Sect. 5.8.
Lemma 5.2b Inverse optimality with cross-weighting terms Consider the con-
trol affine system (5.2). Let u= φ(x) be a stabilizing control, with respect to a
manifold  S. If there exist scalar functions V(x) and  L(x),L (x) satisfying the
1 2
following conditions:
V(x)=0⇔ x∈S
V(x)≥ α(d(x,S))
L (x)=0⇐x∈S
2
1
(x)+∇V(x)Tg(x)R−1LT(x)+g(x)T∇V(x)=0
| L (x)+∇V(x)f(x)− | L    |     |       |     |
| ---------------- | ----- | --- | ----- | --- |
| 1                | 4  2 |     |   2 |    |
1
|     | φ(x)=− | R−1(LT(x)+g(x)T∇V(x)) |     |     |
| --- | ------ | --------------------- | --- | --- |
2
2
|     |         | (x)φ φTRφ | ≥γ(d(x,S)) |     |
| --- | ------- | --------- | ---------- | --- |
|     | L (x)+L | +         |            |     |
|     | 1       | 2         |            |     |
then u= φ(x) is optimal with respect to the performance index with the integrand
(x,u)= L(x)+L (x)u+uTRu. Moreover, the optimal value of the performance
1 2
| criterion equals J(x | ,φ(x))=V(x | ).  |     |     |
| -------------------- | ---------- | --- | --- | --- |
|                      | 0          | 0   |     |     |
Proof Assume one has an optimal control problem (5.2), (5.3) with the optimal-
ity performance integrand in (5.3) (x,u)= L(x)+L (x)u+uTRu. Then Lemma
1 2
5.1 states that the solution of optimal problem can be obtained by forming the
Hamiltonian
| H(x,u)= | L(x)+L | (x)u+uTRu+∇V(x)T(f(x)+g(x)u). |     |     |
| ------- | ------ | ----------------------------- | --- | --- |
1 2
This gives the optimal control in form of
∂
|     | H(x,u)=2uTR+L | (x)+∇V(x)Tg(x)=0 |     |     |
| --- | ------------- | ---------------- | --- | --- |
2
∂u
1 R−1(LT(x)+g(x)T∇V(x))
u= φ(x)=−
2 2

152 5 Cooperative Globally Optimal Control for Multi-Agent Systems …
This feedback control vanishes on the set S since the gradient ∇V(x) and L (x)
2
equal zero there. The Hamiltonian evaluated at this optimal control equals zero
since
H(x,φ(x))= L (x)+L (x)  − 1 R−1 (LT(x)+g(x)T∇V(x)) 
1 2  2 
 2 
+  − 1 R−11(LT(x)+g(x)T∇V(x))  T R  − 1 R−1(LT(x)+g(x)T∇V(x)) 
 2   2 
 2   2 
+∇V(x)T f(x)+∇V(x)Tg(x)  − 1 R−1(LT(x)+g(x)T∇V(x)) 
 2 
 2 
1 1 1 1
= L +∇VT f − L R−1LT − L R−1gT∇V + L R−1LT + ∇VTgR−1gT∇V
11 2 2 2 2 2
2 2 4 4
1 1 1
+ LL R−1gT∇V − ∇VTgR−1LT − ∇VTgR−1gT∇V
2 2
2 2 2
1 1 1
= L +∇VT f − L R−1LT − L R−1gT∇V − ∇VTgR−1gT∇V
1 2 2 2
4 22 4
1
= L
1
+∇VT f − 

L
2
+∇VTg

R−1

LT
2
+gT∇V

=0
4
The Hamiltonian can then be concisely written in quadratic form
H(x,u)= L +L u+uTRu+ ∇VT f +∇VTgu
1 2 
1 T -1 T 1 -1T 1 -1 T
=-L1+
4
∇V gR g ∇V+
4
L2R L
2
+
2
L2R g ∇V
1 1 1
=uTRu+ ∇VTgR-1gT∇V + L R-1LT + L R-1gT∇V +L u+∇VTgu
44
2

2
2
2

2
T
T =-2φ(cid:31) Ru
=(cid:31)φ Rφ(cid:31)
=(u-φ)TR(u-φ)≥0.
The value and the optimal value of the performance criterion then follow as in
Lemma 5.2a. □
That this optimal feedback control u= φ(x) is stabilizing follows also from the
Lyapunov equation
1
V(x)=∇VT f +∇VTgu=∇VT f − ∇VTgR−1(LT +gT∇V)
2
2
1 1 1
=−L + L R−1LT + L R−1gT∇V + ∇VTgR−1gT∇V
1 2 2 2
4 22 4
1 1
− ∇VTgR−1gT∇V − ∇VTgR−1LT
2
2 2
1 1
=−L (x))− ∇VTgR−1gT∇V + L R−1LT
1 2 2
4 4
=−L (x)−L (x)φ−φTRφ ≤−γ(d(x,S))
1 2

5.5 Optimal Cooperative Control for Quadratic Performance … 153
By the assumptions of Lemma 5.2b the Lyapunov function V(x) satisfies all the
conditions of the Theorem 5.1 for partial stability.
5.5 Optimal Cooperative Control for Quadratic
Performance Index and Single-Integrator
Agent Dynamics
This section considers the global optimal control problem for cooperative single-
integrator systems on a given graph topology. Any admissible control protocols for
cooperative control must be distributed in the sense that they respect the prescribed
graph topology by using information only about the agent and its direct neighbors.
Unfortunately, in global optimal control problems, the optimal controls generally
require information about all the states [10]. In fact, the communication restric-
tions imposed by a prescribed graph topology can severely limit the possible global
optimal performance of cooperative agents on that graph. It is seen here that the
cooperative global optimal control problem only has a solution using distributed
control protocols under certain conditions on the graph topology. Moreover, if these
conditions hold, then for the existence of global optimality, the global performance
index must be selected in a certain fashion that depends on the graph topology. This
helps clarify the interactions between stability, optimality, and the graph topology
in multi-agent systems on graphs. The approach used here is to consider inverse
optimality of consensus protocols for the leaderless consensus [8, 12] and the pin-
ning control cases [16]. We call these respectively the cooperative regulator and
cooperative tracker problems.
This section considers the single-integrator agent dynamics
x =u ∈(cid:25), (5.6)
i i
or in global form
x =u, (5.7)
where x=[x (cid:31)x ] T and u =[u (cid:31)u ]T. More general dynamics are considered
1 N 1 N
in the next section.
5.5.1 Optimal Cooperative Regulator
In the leaderless consensus case [8, 12], which we call the cooperative regulator
problem, where there are N agents with states x ∈(cid:25), i=1..N, it is desired for all
i
agents to achieve the same state, that is, ||x(t)−x (t)||→0 as t→∞, ∀(i, j). Then
i j

154 5  Cooperative Globally Optimal Control for Multi-Agent Systems …
T N
the consensus manifold, S:=span(1), where 1=[1 1 ⋅⋅⋅1] ∈ (cid:25) is noncompact.
Therefore, to apply inverse optimality to the cooperative regulator problem, one
needs the partial stability results of Theorem 5.1.
Define the local neighborhood tracking error as

|     |     | η = ∑ e | (x -x ). | (5.8) |
| --- | --- | ------- | -------- | ----- |
|     |     | i       | ij i j   |       |
j∈N i
T
The overall local neighborhood tracking error e=[η (cid:31)η ]  is e= Lx. Then a
1 N
distributed control that guarantees consensus is given as u =−η  or in global form
i i

|     |     | u=−Lx, |     | (5.9) |
| --- | --- | ------ | --- | ----- |
which gives the global closed-loop system

|     |     | x =−Lx. |     | (5.10) |
| --- | --- | -------- | --- | ------ |
Lemma 5.3 If the graph has a spanning tree, then 0 is a simple eigenvalue of the
graph Laplacian matrix [8, 11]. Furthermore, the distributed control law u=−Lx
solves the cooperative regulator problem for the system (5.7).
If the condition of Lemma 5.3 is satisfied then the measure of the distance from the
consensus manifold in Theorem 5.1 is given by any norm of the local neighborhood
| disagreement vector e= | Lx. |     |     |     |
| ---------------------- | --- | --- | --- | --- |
The following theorem states sufficient conditions for the global optimality of
the linear distributed control law (5.9).
Theorem 5.2 Let the systems given as (5.7) be connected on a graph topology L.
RT
Then for some R= >0 the distributed control u=−Lx is globally optimal with
respect to the performance index
|     | ∞                     |     | ∞                |        |
| --- | --------------------- | --- | ---------------- | ------ |
|     | ,u)=∫(xTLTRLx+uTRu)dt |     | =∫(eTRe+uTRu)dt, |        |
|     | J(x                   |     |                  | (5.11) |
0
|     | 0   |     | 0   |     |
| --- | --- | --- | --- | --- |
and is stabilizing to a manifold which is the null space of L if there exists a positive
| semidefinite matrix P= | PT  | ≥0 satisfying |     |     |
| ---------------------- | --- | ------------- | --- | --- |

|     |     | P=  | RL. | (5.12) |
| --- | --- | --- | --- | ------ |
Moreover, if the graph contains a spanning tree then consensus is reached.
Proof First note that since  R is nonsingular the null space of  P equals that
xTPx equals zero on the null space of P
of L. The Lyapunov function V(x)=
and is greater than zero elsewhere since  P≥0. If one introduces the orthogonal
2, where
complement of the null space of P, one has V(x)= xTPx≥ σ (P) y
>0min

5.5 Optimal Cooperative Control for Quadratic Performance … 155
x= x + y, y∈kerP⊥. Since y is a measure of the distance d(x,kerP), the
0
Lyapunov function is found to satisfy the conditions 1 and 2 of Lemma 5.2a.
The part of the performance integrand L(x)= xTQx= xTLTRLx≥ σ (LTRL) y 2
1 >0min
L(x)= xTQx= xTLTRLx≥ σ (LTRL) y 2 satisfies the condition of Theorem 5.1. The ARE (5.5) given as
1 >0min
LTRL−PR−1P=0
is satisfied by P= RL, and u=−Lx=−R−1Px. Therefore, all the conditions of
Lemma 5.2 are satisfied by this linear quadratic problem.
If the graph has a spanning tree, by Lemma 5.3, zero is a simple eigenvalue of L
and thus the null space of P is the consensus manifold span(1). Then, consensus
is reached. This concludes the proof. □
This result was first given in [3] for undirected graphs, where condition (5.12) al-
ways holds. See the discussion below.
Note that the time derivative of Lyapunov function V(x)= xTPx equals
V(x)=−xT(PL+LTP)x=−2xTLTRLx≤−σ (LTRL) y 2,
>0min
which guarantees asymptotic stability of the null space of L or equivalently of P.
Also, since V(x)= xTPx≤σ (P) y 2, according to Theorem 5.1, the stability
>0max
is uniform.
It is seen that if condition (5.12) is satisfied for the given graph topology L,
then any admissible performance index for global optimality must depend on the
graph topology as prescribed by the form (5.11), where the state weighting term is
xTQx= xTLTRLx, and R moreover must be selected to satisfy (5.12).
Remark 5.4 Undirected Graphs The constraint RL= P is a joint constraint on
the graph topology and performance criterion. This can easily be met in the case of
undirected graphs L= LT by selecting R= I, in which case P= L and Q= LTL.
Then, the value of the optimality criterion is given as J*(x )=V(x )= xTLx which
0 0 0 0
is the graph Laplacian potential [18]. Moreover, σ (L) in the proof equals
>0min
λ(L), the Fiedler eigenvalue of the graph. More generally, for undirected graphs
2
the constraint (5.12) can be interpreted as the commutativity condition RL= LR,
which restricts the choice of the symmetric matrix R, but allows choices other than
R= I. Note that then R generally depends on the graph topology. ▋
The constraint (5.12) can also be met by special bidirectional graphs L= R−1P
with P being a symmetric Laplacian matrix and R a positive diagonal matrix. For
general digraphs, since P is symmetric, the constraint (5.12) implies the condition
RL= LTR. (5.13)
The constraint (5.12) defines a new class of digraphs and is further discussed in
Sect. 5.7.

156 5 Cooperative Globally Optimal Control for Multi-Agent Systems …
5.5.2 Optimal Cooperative Tracker
In the pinning control case [8, 16], it is desired for all the agents to reach the state
x of a leader or control node 0, that is, ||x(t)−x (t)||→0 as t→∞, ∀i. This is
0 i 0
called a synchronization problem since the leader’s state may be time varying. We
call this the cooperative tracker problem. It is assumed here that x =0.
0
Consider the optimal cooperative tracker for systems (5.6) and define the local
neighborhood tracking error as
η
i
=∑ e
ij
(x
i
-x
j
)+g
i
(x
i
-x
0
), (5.14)
j∈i
where the pinning gains g ≥0 are nonzero only for a few nodes i directly con-
i
nected to a leader node. The overall local neighborhood tracking error is equal to
e=(L+G)δ, where the global disagreement error is δ= x-1x . Then a distributed
0
control that guarantees synchronization is given as u =−η, or in global form
i i
u=-(L+G)δ, (5.15)
with G=diag(g ...g ), the diagonal matrix of pinning gains. This gives the global
1 N
dynamics
x =u=-(L+G)δ. (5.16)
To achieve synchronization, the ġlobal disagreement system,
δ
(cid:28)
=u=-(L+G)δ, (5.17)
must be asymptotically stabilized to the origin. This means that partial stability no-
tions need not be used, and the sought solution P of the global ARE (5.5) must be
positive definite.
Lemma 5.4 If the graph has a spanning tree, given that there exists at least one
nonzero pinning gain connecting into a root node, then L+G is nonsingular, and
the distributed control u=-(L+G)δ solves the cooperative tracking problem for
the system [8] (5.7).
If the conditions of Lemma 5.4 are satisfied, then the measure of distance from the
target state x is given by any norm of the local neighborhood disagreement vector
0
e=(L+G)δ.
The next result gives sufficient conditions for the global optimality of the distrib-
uted linear protocol (5.15).
Theorem 5.3 Given a graph topology (L+G), let the error dynamics be given as
(5.17), and the conditions of Lemma 5.4 be satisfied. Then for some R= RT >0 the
distributed control u=-(L+G)δ is globally optimal with respect to the perfor-
mance index

5.5 Optimal Cooperative Control for Quadratic Performance … 157
∞ ∞
J(δ,u)=∫(δT(L+G)TR(L+G)δ+uTRu)dt =∫(eTRe+uTRu)dt, (5.18)
0
0 0
and guarantees synchronization to the reference state x if there exists a positive
0
definite matrix P= PT >0 satisfying
P= R(L+G). (5.19)
Proof The Lyapunov function V(δ)=δTPδ>0 and performance integrand
L(δ)=δTQδ=δT(L+G)TR(L+G)δ>0 satisfy the conditions of Lemma 5.2.
1
The ARE
(L+G)TR(L+G)−PR−1P=0
is satisfied by P, and u=-(L+G)δ=-R-1Pδ, thus proving the theorem. □
Remarks similar to Remark 5.4 about the constraint (5.19) between R and L+G
apply here. Under conditions of Lemma 5.4 and (5.19) P is nonsingular since both
R and L+G are nonsingular. For the undirected graph case, one choice that satis-
fies (5.19) is R= I. Then, P= L+G. A more general choice for undirected graphs
is any R>0 that commutes with L+G.
For general digraphs, since P is symmetric, the constraint (5.19) implies the
condition
R(L+G)=(L+G)TR. (5.20)
If R is diagonal, this is equivalent to (5.13) and conditions (5.12) and (5.19) are
equivalent. The constraint (5.19) is further discussed in Sect. 5.7.
It is seen that if condition (5.19) is satisfied for the given graph topology L+G,
then any admissible performance index for global optimality must depend on the
graph topology as prescribed by the form (5.18), where the state error weighting
term is δTQδ=δT(L+G)TR(L+G)δ, and R moreover must be selected to satisfy
(5.19).
Remark 5.5 Both in the optimal cooperative regulator and tracker performance
criteria, the expressions Lx and (L+G)δ, respectively, play a prominent role. In
either case one can concisely write the performance index as
∞
J(e ,u)=∫(eTRe+uTRu)dt.
0
0
In this performance index, matrix R generally depends on the graph topology
through the constraints (5.12) or (5.19). Moreover, the local neighborhood track-
ing error e(t) depends on the graph topology L. Thus, when written in terms of the
global disagreement error, Q depends on the graph topology in the quadratic term
L(δ)=δTQδ=δT(L+G)TR(L+G)δ. ▋
1

158 5 Cooperative Globally Optimal Control for Multi-Agent Systems …
5.6 Optimal Cooperative Control for Quadratic
Performance Index and Linear Time-Invariant
Agent Dynamics
This section considers the global optimal control problem for cooperative systems
on a given graph topology where the agents have identical linear time-invariant
dynamics. Any admissible control protocols for cooperative control must be distrib-
uted in the sense that they respect the prescribed graph topology by using informa-
tion only about the agent and its direct neighbors. It is seen here that the cooperative
global optimal control problem only has a solution using distributed control pro-
tocols under certain conditions on the graph topology. Moreover, if these condi-
tions hold, then for the existence of global optimality, the performance index must
be selected in a certain fashion that depends on the graph topology. The approach
used here is to consider inverse optimality of consensus protocols for the leaderless
consensus [8, 12] and the pinning control cases [16]. We call these respectively the
cooperative regulator and cooperative tracker problem.
This section considers inverse optimality of consensus protocols for the leader-
less and pinning control cases for agents having states x ∈(cid:25)n with linear time-
i
invariant dynamics
x = Ax +Bu, (5.21)
i i i
or in global form
x =(I ⊗A)x+(I ⊗B)u. (5.22)
N N
Here, we consider the case of identical agent dynamics. If the agent dynamics are
heterogeneous, or not the same, then the Kronecker product cannot be used. The
analysis in this chapter relies heavily on the Kronecker product.
5.6.1 Optimal Cooperative Regulator
In the cooperative regulator problem it is desired for all agents to achieve the same
state, that is, ||x(t)−x (t)||→0 as t→∞, ∀(i, j). Define the local neighborhood
i j
tracking error as
η = ∑ e (x −x ), (5.23)
i ij i j
j∈i
where η ∈ n. The overall local neighborhood tracking error η=[ηT (cid:31)ηT ]T
i 1 N
is equal to e=(L⊗I )x. Then a distributed control that guarantees consensus is
n

5.6  Optimal Cooperative Control for Quadratic Performance … 159
η
given as u =−cK  for an appropriate coupling gain c>0 and local feedback
i 2 i
| matrix K | , as shown in [17]. In global form this is |     |     |     |     |     |     |     |
| -------- | ------------------------------------------ | --- | --- | --- | --- | --- | --- | --- |
2
|     |     |     |     | u=−c(L⊗K |     | )x, |     | (5.24) |
| --- | --- | --- | --- | -------- | --- | --- | --- | ------ |
2
which gives the global closed-loop system

|     |     |     |     | x =(I | ⊗A−cL⊗BK |     | )x. | (5.25) |
| --- | --- | --- | --- | ------ | -------- | --- | --- | ------ |
|     |     |     |     | N      |          |     | 2   |        |
The next result gives sufficient conditions for the global optimality of the distrib-
uted linear protocol (5.24).
Theorem 5.4 Let the systems given as (5.22) be connected on a graph topology L.
PT
Suppose there exist a positive semidefinite matrix P = ≥0 and a positive defi-
1 1
| nite matrix P |     | = PT | >0 satisfying |     |     |     |     |     |
| ------------- | --- | ---- | ------------- | --- | --- | --- | --- | --- |
2 2
|     |     |     |     |       | P =cRL,   |     |     | (5.26) |
| --- | --- | --- | --- | ----- | --------- | --- | --- | ------ |
|     |     |     |     |       | 1         | 1   |     |        |
|     |     |     | ATP |       | −PBR−1BTP |     |     |        |
|     |     |     |     | +PA+Q |           |     | =0, | (5.27) |
|     |     |     |     | 2 2   | 2         | 2 2 | 2   |        |
for some Q =QT >0,R = RT >0,R = RT >0 and coupling gain c>0. Define
|                            | 2   | 2   | 1   | 1   | 2   | 2   |     |     |
| -------------------------- | --- | --- | --- | --- | --- | --- | --- | --- |
| the feedback gain matrix K |     |     |     |  as |     |     |     |     |
2

|     |     |     |     | K   | = R−1BTP. |     |     | (5.28) |
| --- | --- | --- | --- | --- | --------- | --- | --- | ------ |
|     |     |     |     |     | 2 2       | 2   |     |        |
Then the distributed control u=−cL⊗K x is globally optimal with respect to the
2
performance index
J(x ,u)
0

∞
| = ∫xT[c2(L⊗K |     | )T(R | ⊗R  | )(L⊗K | )−cRL⊗(ATP |     | +P A)]x+uT(RR | ⊗R )udt, |
| ------------ | --- | ---- | --- | ----- | ---------- | --- | ------------- | -------- |
|              |     | 2    | 1   | 2     | 2          | 1   | 2 2           | 1 2      |
| 0            |     |      |     |       |            |     |               | (5.29)   |
and is stabilizing to the null space of L⊗I  for sufficiently high coupling gain c
n
satisfying (5.31). Moreover, if the conditions of Lemma 5.3 hold then consensus is
reached.
Proof Form the matrix  P= P⊗P. Since  P  is nonsingular the null space of
|     |     |     |     | 1   | 2   | 2   |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
P equals the null space of  P⊗I  which by nonsingularity of  R  is the same
|     |     |     |     | 1   | n   |     |     | 1   |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
as that of  L⊗I . Therefore, by positive semidefiniteness the Lyapunov function
n
V(x)= xTPx= xT(P⊗P)x is zero on the null space of L⊗I  and positive else-
|     |     |     | 1 2 |     |     |     | n   |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
where. By the arguments similar to those presented in the proof of Theorem 5.2, this
Lyapunov function satisfies the conditions of Theorem 5.1.

160 5 Cooperative Globally Optimal Control for Multi-Agent Systems …
Also,
L(x)= xTQx
1
= xT(c2(L⊗K )T(R ⊗R )(L⊗K )−cRL⊗(ATP +PA))x (5.30)
2 1 2 2 1 2 2
equals zero on the null space of L⊗I and satisfies the condition of Lemma 5.2 if
n
the value of the coupling gain is taken as
σ (RL⊗(Q −KTR K ))
c> max 1 2 2 2 2 . (5.31)
σ (LTRL⊗KTR K )
>0min 1 2 2 2
Q=c2(L⊗K )T(R ⊗R )(L⊗K )−cRL⊗(ATP +P A)
2 1 2 2 1 2 2
=c2LTRL⊗KTR K +cRRL⊗(Q −KTR K )
1 2 2 2 1 2 2 2 2
So one has
c2σ (LTRL⊗KTR K )−cσ (RL⊗(Q −KTR K ))>0⇒Q≥0
>0min 1 2 2 2 max 1 2 2 2 2
which gives the lower bound on the coupling gain c. The ARE for system (5.22)
(I ⊗A)TP+P(I ⊗A)+Q−P(I ⊗B)R−1(I ⊗B)TP=0,
N N N N
written as
P⊗ATP +P⊗PA+Q−(P⊗PB)R−1⊗R−1(P⊗BTP)=0
1 2 1 2 1 2 1 2 1 2
P⊗(ATP +PA)++Q−PR−1P⊗(PBR−1BTP)=0
1 2 2 1 1 1 2 2 2
is satisfied by the choice of P= P⊗P since
1 2
Q=c2(L⊗K )T(R ⊗R )(L⊗K )−cRL⊗(ATP +PA)
2 1 2 2 1 2 2
=c2LTRL⊗KTR K +cRRL⊗(Q −PBR−1BTP)
1 2 2 2 1 2 2 2 2
= PR−1P⊗PBR−1BTP +P⊗(Q −PBR−1BTTP)
1 1 1 2 2 2 1 2 2 2 2
=Q ⊗PBR−1BTP +P⊗(Q −PBR−1BTP),
1 2 2 2 1 2 2 2 2
where Q =c2LTRL= PR−1P is introduced for notational simplicity. It follows by
1 1 1 1 1
the conditions (5.26), (5.27) of the theorem that
P⊗(ATP +PAT +Q −PBR−1BTP)+(Q −PR−1P)⊗(PBR−1BTP)=00
1 2 2 2 2 2 2 1 1 1 1 2 2 2
By conditions (5.26), (5.27), and (5.28) the control satisfies
u=−cL⊗K x=−R−1(I ⊗B)TPx=−(R−1⊗R−1)(I ⊗BT)(P⊗P)x
2 N 1 2 N 1 2
=−R−1P⊗R−1BTPx.
1 11 2 2

5.6  Optimal Cooperative Control for Quadratic Performance … 161
Therefore, all the conditions of the Theorem 5.1 are satisfied.
If the graph has a spanning tree, then by Lemma 5.3, zero is a simple eigenvalue
of L and thus the null space of P is the consensus manifold span(1). Then, con-
| sensus is reached. This concludes the proof.  |     |     |     |     | □   |
| --------------------------------------------- | --- | --- | --- | --- | --- |
xTPx equals
Note that the time derivative of the Lyapunov function V(x)=
| V(x)=2xTPx | =2xTP(I              | ⊗Ax−cL⊗BK | x)               |         |     |
| ------------ | -------------------- | --------- | ---------------- | ------- | --- |
|              |                      | N         | 2                |         |     |
|              | = xT(P⊗(PA+ATP)−2P(I |           | ⊗B)((R−1⊗R−1)(I  | ⊗BT)P)x |     |
|              | 1 2                  | 2         | N 1 2            | N       |     |
|              | =−xT(Q+c2(L⊗K        | )T(R ⊗R   | )(L⊗K ))x≤−xTQxx |         |     |
|              |                      | 2 1       | 2 2              |         |     |
implying asymptotic stability to the null space of Q, which equals the null space of
L⊗I  (see (5.30)).
n
It is emphasized that this theorem provides a global optimal solution given in
terms of a local Riccati design equation (5.27) solved at each node. The dimen-
sion of this equation is the dimension of the local agent dynamics n and it does not
depend on the number of nodes N in the graph. As such, this method is scalable to
large graphs.
Note that local optimal design in terms of Riccati equation (5.27) does not guar-
antee global optimal performance of all the agents unless condition (5.26) holds
and the global performance index is selected to depend on the graph topology as in
(5.29). According to the results of Sect. 3.2, however, the locally optimal protocol
(5.27), (5.28) does guarantee stable consensus if the conditions of Lemma 5.3 hold.
Remark 5.6 The graph topology constraint (5.26) is similar to the constraint
(5.12), and comments similar to those stated in Remark 5.4 apply here as well. This
constraint is further discussed in Sect. 5.7. On the other hand, there always exists
PT
a P = >0 satisfying the local Riccati equation (5.27) if (A,B) is stabilizable
2 2
and (A, Q ) is observable. This local Riccati equation was used for design of
2
protocols that guarantee synchronization in Sect. 3.2.The value of the coupling
gain c must be sufficiently great to overpower the, generally, indefinite terms stem-
| ming from the drift dynamics Ax |     |  as in condition (5.31).  |     |     | ▋   |
| ------------------------------- | --- | ------------------------- | --- | --- | --- |
i
5.6.2   Optimal Cooperative Tracker
We now consider the cooperative tracker problem for linear time-invariant agent
dynamics (5.21). In the pinning control or cooperative tracker problem [8, 16], it
∈(cid:25)n of a leader or control node
is desired for all the agents to reach the state x
0
0, that is,  x(t)−x (t) →0 as t→∞, ∀i. It is assumed here that the leader has
i 0
command generator dynamics
|     |     | x = | Ax . |        |     |
| --- | --- | ---- | ---- | ------ | --- |
|     |     |      |      | (5.32) |     |
|     |     | 0    | 0    |        |     |
Consider the optimal cooperative tracker problem for the systems (5.21) and define
the local neighborhood tracking errors as

162 5  Cooperative Globally Optimal Control for Multi-Agent Systems …
η ∑
|     |     |     | =    | e (x −x )+g | (x  | −x ), | (5.33) |
| --- | --- | --- | ---- | ----------- | --- | ----- | ------ |
|     |     |     | i    | ij i j      | i   | i 0   |        |
|     |     |     | j∈i |             |     |       |        |
where η ∈(cid:25)n. The pinning gains g ≥0 are nonzero only for a few nodes directly
|     | i   |     |     | i   |     |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- |
connected to a leader node. The overall local neighborhood tracking error is equal
to e=(L+G)⊗Iδ, where the global disagreement error is δ= x-1⊗x . Then
|     | n   |     |     |     |     |     | 0   |
| --- | --- | --- | --- | --- | --- | --- | --- |
a distributed control that guarantees synchronization is given as u =−cK η, for
i 2 i
an appropriate coupling gain c>0 and local feedback matrix K . In global form
2
this is
|     |     |     | u=-c(L+G)⊗Kδ, |     |     |     | (5.34) |
| --- | --- | --- | ------------- | --- | --- | --- | ------ |
|     |     |     |               |     | 2   |     |        |
with G=diag(g ...g ), the diagonal matrix of pinning gains. This gives the global
1 N
dynamics

|     |     |     | x = I ⊗Ax-c(L+G)⊗BKδ. |     |     |     | (5.35) |
| --- | --- | --- | ---------------------- | --- | --- | --- | ------ |
|     |     |     | N                      |     |     | 2   |        |
To achieve synchronization the global disagreement system
|     |     |     | δ =(I | ⊗A)δ+(I | ⊗B)u, |     | (5.36) |
| --- | --- | --- | ------ | ------- | ----- | --- | ------ |

|     |     |     |     | N   | N   |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- |
or, with control u=-c(L+G)⊗Kδ,
2
|     |     | δ  | =(I | ⊗A-c(L+G)⊗BK |     | )δ, | (5.37) |
| --- | --- | --- | --- | ------------ | --- | --- | ------ |
|     |     |     | N   |              |     | 2   |        |
must be asymptotically stabilized to the origin. This means that partial stability no-
tions need not be used, and the sought solution P of the global ARE (5.5) must be
positive definite. Stability of (5.37) to the origin is equivalent to asymptotic refer-
ence tracking of x  and synchronization under the conditions of Lemma 5.4.
0
The next theorem gives sufficient conditions for the global optimality of the
distributed linear protocol (5.34).
Theorem 5.5 Given a graph topology (L+G), let the error dynamics be given as
(5.37) and the conditions of Lemma 5.4 be satisfied. Suppose there exist a positive
definite matrix P = PT >0, and a positive definite matrix P = PT >0 satisfying
|     | 1   | 1   |     |             |     | 2 2 |        |
| --- | --- | --- | --- | ----------- | --- | --- | ------ |
|     |     |     |     | P =cR(L+G), |     |     | (5.38) |
1 1
|     |     | ATP | +PA+Q | −PBR−1BTP |     | =0, | (5.39) |
| --- | --- | --- | ----- | --------- | --- | --- | ------ |
|     |     |     | 2 2   | 2         | 2 2 | 2   |        |

for some Q =QT >0,R = RT >0,R = RT >0 and coupling gain c>0. Define
|                            | 2 2 | 1   | 1   | 2 2 |     |     |     |
| -------------------------- | --- | --- | --- | --- | --- | --- | --- |
| the feedback gain matrix K |     |     |  as |     |     |     |     |
2
R−1BTP.
|     |     |     |     | K = |     |     | (5.40) |
| --- | --- | --- | --- | --- | --- | --- | ------ |
|     |     |     |     | 2 2 | 2   |     |        |
Then the control u=-c(L+G)⊗Kδ is globally optimal with respect to the per-
2
formance index

5.6 Optimal Cooperative Control for Quadratic Performance … 163
J(δ,u)
0
∞
=∫δT  c2((L+G)⊗K
2
)T(R
1
⊗R
2
)((L+G)⊗K
2
)-cR
1
(L+G)⊗(ATP
2
+P
2
A) δ+uT(R
1
⊗R
2
)udt
0 (5.41)
and guarantees synchronization for sufficiently high coupling gain c satisfying
(5.42).
Proof Form the matrix P= P⊗P. Since P and P are nonsingular so is P. The
1 2 1 2
Lyapunov function V(δ)=δTPδ>0, by the arguments similar to those presented
in the proof of Theorem 5.3. This Lyapunov function satisfies the conditions of
Theorem 5.1, specialized to a single equilibrium point. Also,
L(δ)=δTQδ
1
=δT[c2((L+G)⊗K )T(R ⊗R )((L+G)⊗K )+cR(L+G)⊗(ATP +PA)]δ
2 1 2 2 1 2 2
is positive definite and satisfies the condition of Theorem 5.1 if the value of the
coupling gain is taken as
σ (R (L+G)⊗(Q -KTR K ))
c> max 1 2 2 2 2 (5.42)
σ ((L+G)TR (L+G)⊗KTR K )
>0min 1 2 2 2
Q=c2((L+G)⊗K )T(R ⊗R )((L+G)⊗K )−cR(L+G)⊗(ATP +PA)
2 1 2 2 1 2 2
=c2(L+GG)TR(L+G)⊗KTR K +cR(L+G)⊗(Q −KTR K )
1 2 2 2 1 2 2 2 2
So one has
c2σ ((L+G)TR (L+G)⊗KTR K )-cσ (R (L+G)⊗(Q -KTR K ))>0
>0min 1 2 2 2 max 1 2 2 2 2
⇒Q>0
which gives the lower bound on the coupling gain c. The ARE (5.5) for system
(5.36)
(I ⊗A)TP+P(I ⊗A)+Q−P(I ⊗B)R−1(I ⊗B)TP=0,
N N N N
written as
P⊗ATP +P⊗PA+Q−(P⊗PB)R−1⊗R−1(P⊗BTP)=0
1 2 1 2 1 2 1 2 1 2
P⊗(ATP +PA)++Q−PR−1P⊗(PBR−1BTP)=0
1 2 2 1 1 1 2 2 2
is satisfied by the choice of P= P⊗P since
1 2
Q=c2((L+G)⊗K )T(R ⊗R )((L+G)⊗K )−cR(L+G)⊗(ATP +PA)
2 1 2 2 1 2 2
=c2(L+GG)TR(L+G)⊗KTR K +cR(L+G)⊗(Q −PBR−1BTP)
1 2 2 2 1 2 2 2 2
= PR−1P⊗PBRR−1BTP +P⊗(Q −PBR−1BTP)
1 1 1 2 2 2 1 2 2 2 2
=Q ⊗PBR−1BTP +P⊗(Q −PBR−11BTP)
1 2 2 2 1 2 2 2 2

164 5 Cooperative Globally Optimal Control for Multi-Agent Systems …
where Q =c2(L+G)TR(L+G)= PR−1P is introduced for notational simplicity.
1 1 1 1 1
It follows by the conditions (5.38), (5.39) of the theorem that
P⊗(ATP +PAT +Q −PBR−1BTP)+(Q −PR−1P)⊗(PBR−1BTP)=000
1 2 2 2 2 2 2 1 1 1 1 2 2 2
By conditions (5.38), (5.39), and (5.40) the control u satisfies
u=-c(L+G)⊗K δ=-R-1(I ⊗B)TPδ
2 N
=-(R-1⊗R-1)(I ⊗BT)(P ⊗P )δ=-R-1P ⊗R-1BTPδ.
1 2 N 1 2 1 1 2 2
Therefore, all the conditions of the Theorem 5.1 are satisfied, and the control is
stabilizing to the origin for (5.36). This guarantees synchronization and completes
the proof. □
Note that the time derivative of the Lyapunov function V(δ)= δTPδ equals
V(cid:28)(δ)=2δTPδ (cid:28) =2δTP(I ⊗A-c(L+G)⊗BK )δ
N 2
=δT(P ⊗(P A+ATP )-2P(I ⊗B)(R-1⊗R-1)(I ⊗BT)P)δ
1 2 2 N 1 2 N
=-δT(Q+c2(L⊗K )T(R ⊗R )(L⊗K ))δ≤-δTQδ<0,
2 1 2 2
implying asymptotic stability of (5.37) to the origin.
This theorem provides a global optimal solution given in terms of a local Riccati
design equation (5.39) solved at each node. The dimension of this equation is the
dimension of the local agent dynamics n and it does not depend on the number of
nodes N in the graph. As such, this method is scalable to large graphs.
Note that local optimal design in terms of Riccati equation (5.39) does not guar-
antee global optimal performance of all the agents unless condition (5.38) holds
and the global performance index is selected to depend on the graph topology as in
(5.41). According to the results of Sect. 3.2, however, the locally optimal protocol
(5.39), (5.40) does guarantee synchronization if the conditions of Lemma 5.4 hold.
Remark 5.7 The graph topology constraint (5.38) is similar to the constraint (5.19),
and comments similar to those stated there apply here as well. This constraint is
further discussed in Sect. 5.7. On the other hand, there always exists a P = PT >0
2 2
satisfying (5.39) if (A,B) is stabilizable and (A, Q ) is observable. This local
2
Riccati equation was used for design of protocols that guarantee synchronization in
Sect. 3.2. The value of the coupling gain c must be sufficiently great to overpower
the, generally, indefinite terms stemming from the drift dynamics Ax, as in condi-
i
tion (5.42). ▋
5.7 Constraints on Graph Topology
In order to admit a distributed control solution to an appropriately defined global
optimal control problem, the graph topology must satisfy the appropriate constraints
(5.12), (5.19) or (5.26), (5.38) in terms of the Laplacian matrix L or the pinned

5.7 Constraints on Graph Topology 165
Laplacian matrix L+G. This section investigates classes of graphs that satisfy
these conditions. A new class of digraphs is presented for which the condition al-
ways holds, namely, the digraphs whose Laplacian matrix is simple, that is, having
diagonal Jordan form.
Generally, one can express these conditions as
RL= P,
(5.43)
where R= RT >0, L is a singular (i.e., the graph Laplacian) or nonsingular (i.e.,
the pinned graph Laplacian) M-matrix, and P= PT ≥0, a singular or nonsingular
positive definite matrix, respectively. Equivalently
RL= LTR (5.44)
For the following classes of graph topologies one can satisfy this condition.
5.7.1 Undirected Graphs
Given that the graph is undirected, then L is symmetric, i.e., L= LT so the condi-
tion (5.43) becomes a commutativity requirement
RL= LTR= LR. (5.45)
See Remark 5.4 where it is shown that the choice R= I always satisfies this condi-
tion for undirected graphs. Then, P= L.
More generally, condition (5.45) is satisfied by symmetric matrices R and L
if and only if R and L have all eigenvectors in common. Since L is symmetric it
has a basis of orthogonal eigenvectors, and one can construct R satisfying (5.45)
as follows. Let T be an orthogonal matrix whose columns are eigenvectors of L,
then L=TΛTT with Λ a diagonal matrix of real eigenvalues. Then for any posi-
tive definite diagonal matrix Θ one has that R=TΘTT >0 commutes with L and
satisfies the commutativity requirement (5.45).
Note that the R so constructed for global optimal performance depends on
all the eigenvectors of the Laplacian L in (5.43) (i.e., the graph Laplacian or the
pinned Laplacian as appropriate). By contrast, it is known that consensus properties
depend only on the left eigenvector for the zero eigenvalue of L [8, 12]. That is, for
global optimal performance more information about the eigenstructure of the Lapla-
cian is required than in simply achieving consensus.
5.7.2 Detail Balanced Graphs
Given a detail balanced graph (defined in Sect. 5.2), its Laplacian matrix is sym-
metrizable, that is, there exists a positive diagonal matrix Λ>0 such that L=ΛP,
where P is a symmetric graph Laplacian matrix. Then, condition (5.43) holds with
R=Λ−1. Recall that for detail balanced graphs, the diagonal elements of R in the

166 5 Cooperative Globally Optimal Control for Multi-Agent Systems …
unpinned case are then the elements of the left eigenvector of the Laplacian for the
eigenvalue of zero.
5.7.3 Directed Graphs with Simple Laplacian
In this subsection, we introduce a new class of digraphs which, to our knowledge,
has not yet appeared in the cooperative control literature. This class of digraphs ad-
mits a distributed control solution to an appropriately defined global optimal control
problem.
Given a directed graph, let it be such that Laplacian matrix L (either the graph
Laplacian or the pinned graph Laplacian) in (5.43) is simple, that is, its Jordan form
is diagonal (i.e., there exists a basis of rank 1 eigenvectors of L). Then there exists
a matrix R>0 depending on all the eigenvectors of the Laplacian L that satisfies
the condition (5.43). This result is given in the following theorem. Let the Jordan
form decomposition of L be given by
L=T−1ΛT (5.46)
with T being the matrix of left eigenvectors and Λ being diagonal and real.
Theorem 5.6 Let L be a Laplacian matrix (generally not symmetric). Then there
exists a positive definite symmetric matrix R= RT >0 such that RL= P is a sym-
metric positive semidefinite matrix if and only if L is simple. Then a suitable choice
for R is R=TTT.
Proof
(i) Let L be simple. Then it is diagonalizable, i.e., there exists a transformation
matrix T such that TLT−1 =Λ, where Λ is a diagonal matrix of eigenvalues of
L. Then
TLT−1 =Λ=ΛT =T−TLTTT,
implying TTTLT−1T−T = LT, which implies that (TTT)L= LT(TTT). Let
R=TTT. Obviously, R= RT >0 and P= RL=TTTL=TTΛT ≥0 since Λ≥0
(∀x0≤ xTPx= xTTTΛTx= yTΛy∀y) [1].
(ii) Let L be positive semidefinite matrix. Suppose there exists R= RT >0 sat-
isfying the condition RL= P is a symmetric positive semidefinite matrix. Then
one needs to show that L is simple. To show this, we will prove the contrapositive
of this by contradiction. Therefore, we suppose the negation of the contrapositive.
That is, suppose L is not simple but that there exists R= RT >0 satisfying the
condition RL= P is a symmetric positive semidefinite matrix.
Since L is not simple, there exists a coordinate transformation bringing L to
a Jordan canonical form T−1LT = J, with nonzero superdiagonal (otherwise L
would be simple). Then one has RL= RTJT−1 = P= PT =T−TJTTTR. But then
(TTRT)J = JT(TTRT). Therefore, there exists R =TTRT = RT >0 such that
2 2

5.8 Optimal Cooperative Control for General Digraphs: Performance … 167
R J = JTR . Without loss of generality let us assume that the first Jordan block is
2 2
not simple, and with a slight abuse of notation R will refer to the corresponding
2,11
block in R . Then one has that R (λI+E)=(λI+ET)R ⇒R E= ETR ,
2 2,11 2,11 2,11 2,11
where E is a nilpotent matrix having ones on the superdiagonal. This identity
means that the first row and first column of R are zero, except for the last entry.
2,11
However, then R cannot be positive definite, since there are vanishing principal
2
minors (Sylvester’s test). □
Since the simplicity of the Laplacian matrix is a necessary and sufficient condition
for the graph topology constraint (5.43) to be satisfied, one can state the following
theorem relating the graph Laplacian matrix (unpinned or pinned) to the global op-
timality of distributed cooperative control as given in Sects. 5.5 and 5.6. The next
result is for Sect. 5.6.
Theorem 5.7 The distributed control in cooperative regulator problem (5.25)
(respectively cooperative tracker problem (5.37)) is optimal under optimality crite-
rion (5.29) (resp. (5.41)) for some R= R ⊗R >0, if and only if the graph Lapla-
1 2
cian matrix in (5.26) (resp. (5.38)) is simple.
Proof If the control law in the respective instances is optimal then the constraint
(5.43) on P,R,L is satisfied, hence, by Theorem 5.6, L is simple. If, conversely L
is simple, then there exists a quadratic performance criterion with respect to which
the cooperative distributed control given by L is inversely optimal. □
Remark 5.8 These results place constraints on the graph topologies on which the
linear distributed protocols can guarantee global optimality with respect to a stan-
dard linear quadratic performance criterion. Moreover, if the constraints hold, then
the global performance index must be selected to depend on the graph topology.
This in turn guarantees asymptotic consensus or synchronization. The following
section will allow for a more general form of performance criterion which yields
optimal control for general directed graphs. ▋
5.8 Optimal Cooperative Control for General Digraphs:
Performance Index with Cross-Weighting Terms
Heretofore, we have seen that, when using the standard quadratic performance index
that weights norms of the state and the control input, global optimal performance
can be obtained by linear distributed control protocols only if the graph satisfies a
condition. This condition was seen to hold for the class of digraphs with Laplacian
matrices having simple Jordan form. In this section, we show that if state-control
cross-weighting terms are allowed in the performance index, then global optimal
performance can be obtained by distributed protocols on any digraph. This indicates
that global performance indices with cross-weighting terms are in some sense more
natural for cooperative multi-agent systems on communication graph topologies.
When dealing with general directed graphs, the constraint (5.12) on the graph
Laplacian L, or (5.19) on the pinned graph Laplacian L+G, is too restrictive.

168 5 Cooperative Globally Optimal Control for Multi-Agent Systems …
These constraints only hold for a special class of digraphs whose Laplacian matrix
(or pinned Laplacian L+G) has diagonal Jordan form. This constraint can be re-
laxed, and optimal cooperative controllers developed for arbitrary digraphs, by al-
lowing state-control cross-weighting terms in the performance criterion [10]. Then,
requiring that the performance criterion be positive (semi) definite leads to condi-
tions on kernel matrix P in V(x)= xTPx, or equivalently on the control Lyapunov
function, which should be satisfied for the existence of distributed globally optimal
controls. This condition is milder than the conditions (5.12), (5.19), where no cross-
weighting term is allowed in the performance index.
In Sects. 5.8.1 and 5.8.2, we treat the optimal cooperative regulator and tracker
for single-integrator dynamics, including a state-control cross-weighting term in the
performance index. In Sect. 5.8.3, we discuss the resulting constraint conditions on
the graph topology that must be satisfied by the graph Laplacian for existence of an
optimal controller of distributed form. It is shown that, unlike conditions (5.12) and
(5.19), the new conditions can be satisfied for arbitrary directed graphs by proper
selection of the performance index weighting matrices.
In Sects. 5.8.4 and 5.8.5, we treat the optimal cooperative regulator and tracker
for linear time-invariant agent dynamics. Again, it is shown that if cross-weighting
terms are allowed in the performance index, then the conditions required for exis-
tence of a distributed optimal controller can be satisfied on arbitrary digraphs.
5.8.1 Optimal Cooperative Regulator—Single-Integrator
Agent Dynamics
This section considers the cooperative regulator problem for single-integrator agent
dynamics x =u or in global form (5.7). Since the consensus manifold is noncom-
i i
pact, it is necessary to use the partial stability results in Theorem 5.1. Using the
distributed control protocol u=−Lx gives the closed-loop system x =−Lx.
The next result extends Theorem 5.2 to the case of state-control weighting terms
in the global performance index.
Theorem 5.8 Let the graph topology be given by L and multi-agent systems be
given as (5.7). Then for some R= RT >0 the control u= φ(x)=−Lx is optimal
∞
with respect to the performance index J(x ,u)=∫(x,u)dt with the performance
0
integrand 0
(x,u)= xTLTRLx+uTRu+2xT(LTR−P)u≥0 (5.47)
and is stabilizing to a manifold which is the null space of L if there exists a posi-
tive semidefinite matrix P= PT ≥0, having the same kernel as L, satisfying the
inequality condition
LTP+PL−PR−1P≥0 (5.48)

5.8  Optimal Cooperative Control for General Digraphs: Performance … 169
Moreover, if the graph contains a spanning tree then consensus is reached.
Proof Let V(x)= xTPx be a partial stability Lyapunov function. Then
V(x)=−2xTPLx=−xT(PL+LTP)x≤−xTPR−1Px≤ (PR−1P) 2
σ y
>0min
where x= x + y, y∈kerP⊥. Thus the control is stabilizing to the null space of P.
0
Also, the performance integrand equals
|           |  L T RL L T R−P |  x  |
| --------- | ----------------- | ----- |
|          | T T              | .     |
| (x,u)= x | u                |    |
 
|     | RL−P R | u |
| --- | ------- | ---- |
One has (x,u)≥0 if  R>0 and the Schur complement inequality (5.48) holds.
The control is optimal since
1
| u=φ(x)=− R−1(LT | +gT∇V) |     |
| --------------- | ------ | --- |
2
2
| 1 R−1(2(RL−P)x+2Px)=− |     | 1 R−1(2RL)x |
| --------------------- | --- | ----------- |
=−
| 2   |     | 2   |
| --- | --- | --- |
=−−Lx
The performance integrand evaluated at the optimal control satisfies
| (x,φ(x))= xTLTRLx+xTLRLx−2xT(LTR−P)Lx |     |     |
| -------------------------------------- | --- | --- |
=2xTLTRLx−2xTLTRLx+2xTTPLx
| = xT(PL+LTP)x≥ | xTPR−1Px |     |
| -------------- | -------- | --- |
(PR−1P) 2
| ≥ σ | y   |     |
| --- | --- | --- |
min
Hence, all the conditions of Lemma 5.2b are satisfied. If the graph has a spanning
tree, by Lemma 5.3, zero is a simple eigenvalue of L and thus the null space of P
is the consensus manifold span(1). Then, consensus is reached. This concludes the
proof.  □
Note that if the constraint P= RL in (5.12) is met as in previous sections, the cross-
weighting term in (x,u) in the proof vanishes, so the performance criterion is
quadratic, and therefore (x,u)≥0. That is, substituting P= RL into (5.48) shows
that (5.48) is satisfied.
Remark 5.9 The kernels of P and L in (5.48) need not be the same, but under
condition (5.48) their relation is given by the following result.  ▋
Proposition Let there exist a symmetric positive semidefinite P satisfying (5.48)
for some L, and R>0 then kerL⊆kerP.

170 5 Cooperative Globally Optimal Control for Multi-Agent Systems …
The proof of this proposition uses a result on symmetric positive semidefinite
matrices summarized in the following lemma, which is not difficult to prove.
Lemma 5.5 Given a positive semidefinite symmetric matrix Q≥0 the kernel of Q
equals the set where the pertaining quadratic form satisfies xTQx=0.
Note that this result, albeit straightforward, is not trivial since a nonsymmetric ma-
trix Q generally does not share this property.
Now, to prove the proposition notice that under (5.48) LTP+PL−PR−1P is a
symmetric positive semidefinite matrix. Consider the quadratic form
xT(LTP+PL−PR−1P)x≥0.
Assume x∈kerL but x∉kerP, then for such an x
(cid:31)x(cid:29) T (cid:29)L(cid:29) T (cid:29)P(cid:29)(cid:29)x(cid:30)+(cid:29)x(cid:29) T (cid:29)(cid:29)P(cid:29)L(cid:29)x(cid:28)−xTPR−1Px≥0⇒−xTPR−1Px=−(Px)TR−−1(Px)≥0.
=0
However, since R>0 this forces Px=0, whence it follows x∈kerP, which is
a contradiction. Therefore, one has x∈kerL⇒x∈kerP meaning kerL⊆kerP,
which proves the proposition. More discussion about the condition (5.48) is pro-
vided in Sect. 5.8.3.
5.8.2 Optimal Cooperative Tracker—Single-Integrator
Agent Dynamics
In case of the optimal cooperative tracker with pinning from a leader node for the
single-integrator agent dynamics system (5.7), one has the global disagreement er-
ror dynamics (5.17), which must be stabilized to the origin. This means that partial
stability notions need not be used, and the sought matrix P must be positive defi-
nite. Therefore, for the optimal cooperative tracker problem the applied logic is the
same, the only difference being that positive semidefiniteness is replaced by posi-
tive definiteness in the performance index and Lyapunov function.
Theorem 5.9 Let the graph topology be (L+G), the error dynamics be given as
(5.17), and the conditions of Lemma 5.4 be satisfied. Then for some R= RT >0
the control u=φ(δ)=-(L+G)δ is optimal with respect to the performance index
∞
J(δ,u)=∫(δ,u)dt with the performance integrand
0
0
(δ,u)=δT(L+G)TR(L+G)δ+uTRu+2δT((L+G)TR-P)u>0 (5.49)
and synchronization is reached if there exists a positive definite matrix P= PT ≥0,
satisfying the inequality
(L+G)TP+P(L+G)−PR−1P>0 (5.50)

5.8 Optimal Cooperative Control for General Digraphs: Performance … 171
Proof Let V(δ)=δTPδ be a Lyapunov function. Then
V(δ)=-2δTP(L+G)δ=-δT(P(L+G)+(L+G)TP)δ<-δTPR-1Pδ<0.
Thus, the control is stabilizing to the origin for (5.17) and synchronization is
reached. Also the performance integrand equals
(δ,u)=

δT uT


 
(L
R
+
(
G
L
)
+
T
G
R(
)
L
-
+
P
G) (L+G
R
)TR-P
 

 
δ
u

 
>0
and (x,u)>0 if R>0 and inequality (5.50) holds (by Schur complement). The
control is optimal since
1
u=φ(δ)=- R-1(LT +gT∇V)
2 2
1 1
=- R-1(2(R(L+G)-P)δ+2Pδ)=- R-1(2R(L+G))δ
2 2
=-(L+G)δ
The performance integrand evaluated at the optimal control satisfies
(δ,φ(δ))=δT(L+G)TR(L+G)δ+δT(L+G)TR(L+G)δ
-2δT((L+G)TR-P)(L+G)δ
=2xδT(L+G)TR(L+G)δ-2δT(L+G)TR(L+G)δ+2δTP(L+G)δ
=δT(P(L+G)+(L+G)TP)δ>δTPR-1Pδ>0
Hence, all the conditions of Lemma 5.2b are satisfied, which concludes the proof. □
Note that if the constraint P= R(L+G) in (5.19) is met as in previous sections,
the cross-weighting term in (δ,u) in the proof vanishes, so that the performance
criterion is quadratic and therefore (x,u)>0. That is, P= R(L+G) guarantees
that (5.50) is satisfied. More discussion about the condition (5.50) is provided in
Sect. 5.8.3.
5.8.3 Condition for Existence of Global Optimal Control with
Cross-weighting Terms in the Performance Index
In this section, we show that conditions (5.48) and (5.50) can be met for arbitrary
digraphs, in contrast to (5.12) or (5.19) which only hold for digraphs with simple
Laplacian matrices. This indicates that global performance indices with cross-
weighting terms are in some sense more natural for cooperative multi-agent systems
on communication graph topologies.
Conditions (5.48) and (5.50) must be met for the existence of a distributed
linear control protocol that solves a global optimality problem on the prescribed

172 5 Cooperative Globally Optimal Control for Multi-Agent Systems …
graph. These conditions allow state-control cross-weighting terms in the perfor-
mance index, and express joint constraints on the graph matrices L, or L+G, and
the choice of control weighting matrix R. These conditions are less strict than the
conditions (5.12) and (5.19), respectively, that guarantee the existence of a global
optimal controller of distributed form when no cross-weighting term is allowed.
In particular, note that if condition (5.12) or (5.19) hold then, respectively, (5.48)
and (5.50) hold as well, and the cross-weighting terms equal zero. The additional
freedom stemming from allowing the presence of cross-weighting terms in the per-
formance integrand allows for more general graph topologies excluded under the
Riccati conditions (5.12) or (5.19) to support inverse optimality of linear distributed
control protocols.
Conditions (5.12) and (5.19) are only satisfied by digraphs that have a simple
Jordan form for L or L + G, respectively. This includes undirected graphs and the
detail balanced digraphs. It is now shown that conditions (5.48) and (5.50) can be
satisfied for arbitrary digraphs.
For arbitrary digraphs, a matrix P having the same kernel as L and satisfying
the optimal cooperative regulator condition (5.48) can be constructed as follows. To
find P= PT ≥0 such that LTP+PL−PR−1P≥0 and kerP=kerL one can solve
the equivalent inequality
−LTP−PL≤−PR−1P,
by solving an intermediate Lyapunov equation
−LTP−PL=−Q≤−PR−1P, (5.51)
with Q=QT ≥0, kerQ=kerL. The solution P to this Lyapunov equation exists
since -L is stabilizing to its null space, and equals
∞
P=∫e−LTτQe−Lτdτ≥0.
0
That P= PT follows from the construction, and if L has a simple zero eigenvalue,
which is necessary for consensus, kerP=kerQ=kerL. Since P is bounded for
any fixed Q, and the solution P does not depend on R, choosing R large enough,
in the sense of any matrix norm, will make PR−1P≤Q. Therefore, such a con-
structed P satisfies condition (5.48).
A similar method can be used to construct, for any digraph, the required matrix
P for the optimal tracker condition (5.50).
5.8.4 General Linear Time-Invariant Systems—Cooperative
Regulator
This section deals with agents having states x ∈ n with drift dynamics
i
x(cid:31) = Ax +Bu ∈(cid:30)n, or in global form (5.22). Since the synchronization manifold,
i i i

5.8  Optimal Cooperative Control for General Digraphs: Performance … 173
null space of L⊗I , is noncompact, the partial stability Theorem 5.1 must be used.
n
The next result extends Theorem 5.4 to the case of state-control cross-weighting
terms.
Theorem 5.10 Let the graph topology be given by L and multi-agent systems be
given as (5.22). Define the local feedback matrix to be K  such that the cooperative
2
feedback control u=−cL⊗K x, with a scalar coupling gain c>0, makes (5.22)
2
asymptotically converge to the consensus manifold, i.e., achieve consensus. Then
PT
there exists a positive semidefinite matrix P= ≥0, satisfying

| c2(L⊗K  | )TR(L⊗K )−P(I | ⊗A)−(I ⊗AT)P≥0 | (5.52) |
| ------- | ------------- | -------------- | ------ |
|         | 2 2           | N N            |        |
| P(cL⊗BK | −(I ⊗A))+⊗(cL | B−K ⊗A))TP     |        |
|         |               | (I             |        |
|         | 2 N           | 2 N            |        |
−P(I ⊗B)R−1(I ⊗BT)P≥0
(5.53)
N N
for some R= RT >0. Moreover, the control u=−cL⊗K x is optimal with respect
2
∞
to the performance index J(x ,u)=∫(x,u)dt  with the performance integrand
0
0
| (x,u)= xT[c2(L⊗K | )TR(L⊗K )−P(I   | ⊗A)−(I ⊗AT)P]x+uTRu |     |
| ----------------- | --------------- | ------------------- | --- |
|                   | 2 2             | N N                 |     |
| +2xT[c(L⊗⊗K       | )TR−P(I ⊗B)]u≥0 |                     |     |
|                   | 2 N             |                     |     |
and is stabilizing to the null space of P for sufficiently high coupling gain c. Finally,
if the graph has a spanning tree, then consensus is reached.
Proof Since the cooperative feedback is assumed to make (5.22) synchronize the
closed-loop system matrix  A = I ⊗A−cL⊗BK  defines a partially stable sys-
|     | cl N | 2   |     |
| --- | ---- | --- | --- |
tem with respect to the consensus manifold. This manifold equals the kernel of
L⊗I  if  L contains a spanning tree. Then for any positive semidefinite matrix
n
Q=QT ≥0, having the kernel equal to the consensus manifold, there exists a solu-
tion P= PT ≥0 to the Lyapunov equation
+ATP=−Q
PA
|     | cl cl |     |     |
| --- | ----- | --- | --- |
∞
|     | P=∫eAcl TτQeAcl | τdτ≥0 |     |
| --- | --------------- | ----- | --- |
0
with kernel equal to the consensus manifold.
The inequality (5.52) is satisfied for sufficiently high values of the coupling gain
c>0, since for sufficiently large c the first term dominates the second one every-
where, except on the null space of L⊗K . On this null space, the control signal
2
vanishes. According to the assumption on partial asymptotic stability of the consen-
sus manifold under the chosen feedback control, and the Lyapunov equation, the
second term in (5.52) is positive semidefinite when evaluated on the null space of
L⊗K . Hence, the inequality (5.52) is satisfied everywhere. The inequality (5.53)
2

174 5 Cooperative Globally Optimal Control for Multi-Agent Systems …
is satisfied via Lyapunov equation by choosing R= RT >0 sufficiently large, in the
sense of matrix norms, such that 0≤P(I ⊗B)R−1(I ⊗BT)P≤Q.
N N
Let V(x)= xTPx be a partial stability Lyapunov function. Then
V(x)=2xTPx =2xTP((I ⊗A)x−c(L⊗BK )x)
N 2
= xT(P(I ⊗A)+(I ⊗AT)P)x−−cxTP(L⊗BK )x−cxT(L⊗BK )TPx
N N 2 2
= xT P(I ⊗A−cL⊗BK )+(I ⊗A−cL⊗BK ))TP x
 N 2 N 2 
= xT PA +ATP x=−xTQx≤−xTP(I ⊗B)R−1(I ⊗BT)Px≤0
 cl cl  N N
The quadratic form xTQx≥0 serves as a measure of distance from the consensus
manifold. Thus, the control is stabilizing to the consensus manifold, as assumed.
Also, the performance integrand equals
(x,u)=xT uT
 
c2(L⊗K )TR(L⊗K )-P(I ⊗A)-(I ⊗AT)P c(L⊗K )TR-P(I ⊗B)
2 2 N N 2 N
 
 cR(L⊗K )-(I ⊗B)P R 
2 N
x
≥0
u
and (x,u)≥0 by Schur complement if inequalities (5.52) and (5.53) hold. The
feedback control is optimal since
1
u= φ(x)=− R−1(LT +gT∇V)
2 2
1
=− R−1(2(cR(L⊗K )−(I ⊗BT)P)x+2(I ⊗BBT)Px)
2 2 N N
1
=− R−1(2cR(L⊗K ))x=−c(L⊗K )x
2 2 2
The performance integrand evaluated at the optimal control satisfies
(x,(x))= xT c2(L⊗K )TR(L⊗K )−P(I ⊗A)−(I ⊗AT)Px
 2 2 N N 
+xTc2(L⊗KK )TR(L⊗K )x−2cxT c(L⊗K )TR−P(I ⊗B)(L⊗K )x
2 2  2 N  2
=−xT[P(I ⊗A)+((I ⊗AT)P]x+2cxTP(I ⊗B)(L⊗K )x
N N N 2
=−xT P(I ⊗A)+(I ⊗AT)Px+2ccxTP(L⊗BK )x
 N N  2
= xT (cL⊗BK −I ⊗A)TP+P(cL⊗BK −I ⊗A)x
 2 N 2 N 
= xT −ATTP−PA x= xTQx≥ xTP(I ⊗B)R−1(I ⊗BT)Px≥0
 cl cl N N

5.8  Optimal Cooperative Control for General Digraphs: Performance … 175
Hence all the conditions of Lemma 5.2b are satisfied.
If the communication graph has a spanning tree, then by Lemma 5.3 the null
|           |     |                                       |     |     |     |     | S:=span(1⊗α), | α∈(cid:25)n,  |
| --------- | --- | ------------------------------------- | --- | --- | --- | --- | ------------- | ------------- |
| space of  | L⊗I |  equals the synchronization manifold  |     |     |     |     |               |               |
n
therefore, synchronization is asymptotically achieved in the optimal way.
| This concludes the proof.  |     |     |     |     |     |     |     | □   |
| -------------------------- | --- | --- | --- | --- | --- | --- | --- | --- |
Specifying  the  form  of  P  and  R  as  P= P⊗P,  R= R ⊗R   and  assum-
|     |     |     |     |     |     | 1   | 2 1 2 |     |
| --- | --- | --- | --- | --- | --- | --- | ----- | --- |
ing further that  K = R−1BTP, where  P  is a solution of local Riccati equation
|        |     | 2         | 2 2 |                                                     | 2   |     |     |     |
| ------ | --- | --------- | --- | --------------------------------------------------- | --- | --- | --- | --- |
| PA+ATP |     | −PBR−1BTP |     |                                                     |     |     |     |     |
|        | +Q  |           |     | =0 as used in Theorems 5.4 and 5.5, the inequality  |     |     |     |     |
| 2      | 2   | 2 2       | 2 2 |                                                     |     |     |     |     |
(5.53) becomes
|     |     | cPL⊗PBK         | −P⊗(PA+ATP)+cLTP⊗KTBTP |     |     |     |       |     |
| --- | --- | --------------- | ---------------------- | --- | --- | --- | ----- | --- |
|     |     | 1               | 2 2                    | 1   | 2   | 2   | 1 2 2 |     |
|     |     | −PR−1P⊗PBR−1BTP |                        |     | ≥0. |     |       |     |
|     |     | 1 1             | 1 2                    | 2   | 22  |     |       |     |
Equivalently, since
|     |     | PBK | = KTBTP | =   | PBR−1BTP | = KTR | K ≥0, |     |
| --- | --- | --- | ------- | --- | -------- | ----- | ----- | --- |
|     |     | 2   | 2 2     | 2   | 2 2      | 2     | 2 2 2 |     |
one has
|     | (cPL+cLTP |     | −PR−1P)⊗KTR |     | K−P⊗(KTR |     |          |     |
| --- | --------- | --- | ----------- | --- | -------- | --- | -------- | --- |
|     |           |     |             |     |          |     | K−Q )≥0. |     |
|     |           | 1   | 1 1 1       | 1   | 2        | 1   | 2 2      |     |
Note the similarity to condition (5.48) introduced in single-integrator consensus
problem in Sect. 5.8.1. If condition (5.48) is satisfied, then for sufficiently high
value of the coupling gain c this constraint can be met.
Clearly, if Riccati conditions (5.26), (5.27) are satisfied, then the cross-weighting
term vanishes
|     | cR(L⊗K |     | )=(I ⊗BT)P⇔c(L⊗K |     |     | )=  | R−1(I ⊗BT)P. |     |
| --- | ------ | --- | ---------------- | --- | --- | --- | ------------ | --- |
|     |        | 2   | N                |     |     | 2   | N            |     |
R−1BTP
One should also note that choosing  K =  affords an infinite interval of
|     |     |     |     |     | 2 2 | 2   |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
positive values for coupling gain c that achieve synchronization [18], which allows
one to find a sufficiently high value of c to satisfy inequality (5.52) without worry-
ing about losing synchronization. The same applies whenever one needs to choose
c to be, for any purpose, sufficiently large.
5.8.5   General Linear Time-Invariant Systems—Cooperative
Tracker
If the goal is to synchronize dynamics (5.22) to the leader’s trajectory x = Ax ,
0 0
i.e., solve the cooperative tracking problem, then one should use the global error
| system δ= | x-1⊗x | , with the same global error dynamics |     |     |     |     |     |     |
| --------- | ----- | ------------------------------------- | --- | --- | --- | --- | --- | --- |
0
|     |     |     | δ =(I | ⊗A)δ+(I |     | ⊗B)u. |     | (5.54) |
| --- | --- | --- | ------ | ------- | --- | ----- | --- | ------ |
|     |     |     |        | N       |     | N     |     |        |

176 5 Cooperative Globally Optimal Control for Multi-Agent Systems …
Theorem 5.11 Let the graph topology be given by (L+G), the conditions of
Lemma 5.4 be satisfied, and multi-agent systems be given as (5.54). Define the
local feedback matrix to be K such that the cooperative feedback control
2
u=−c(L+G)⊗K δ, with a scalar coupling gain c>0, makes (5.54) asymptoti-
2
cally converge to the origin. Then there exists a positive definite matrix P= PT >0,
satisfying
c2((L+G)⊗K )TR((L+G)⊗K )−P(I ⊗A)−(I ⊗AT)P>0 (5.55)
2 2 N N
P(c(L+G)⊗BK −(I ⊗A))+(c(L+G)⊗BK −(I ⊗A))TP
2 N 2 N
−P(I ⊗B)R−1(I ⊗BTT)P>0 (5.56)
N N
for some R= RT >0. Moreover, the control u=-c(L+G)⊗Kδ is optimal with
2
∞
respect to the performance index J(δ,u)=∫(δ,u)dt with the performance inte-
0
grand 0
(δ,u)=δT 

c2((L+G)⊗K
2
)TR((L+G)⊗K
2
)-P(I
N
⊗A)-(I
N
⊗AT)P δ+uTRu
+2δT 

c((L+G)⊗K
2
)TR-P(I
N
⊗B)

u>0.
Proof Since the cooperative feedback is assumed to stabilize (5.54) to the ori-
gin, the closed-loop system matrix A = I ⊗A−c(L+G)⊗BK defines a stable
cl N 2
system. Then for any positive definite matrix Q=QT >0, there exists a solution
P= PT >0 to the Lyapunov equation
PA +ATP=−Q
cl cl
that is given by
∞
P=∫eAcl TτQeAcl τdτ>0
0
The inequality (5.55) is satisfied for sufficiently high values of the coupling gain
c>0, since for sufficiently large c the first term in (5.55) dominates the sec-
ond one everywhere. The inequality (5.56) is satisfied via Lyapunov equation by
choosing R= RT >0 sufficiently large, in the sense of matrix norms, such that
0≤P(I ⊗B)R−1(I ⊗BT)P<Q.
N N
Let V(δ)=δTPδ>0 be a Lyapunov function. Then
V(δ)=2δTPδ  =2δTP((I ⊗A)δ-c((L+G)⊗BK )δ)
N 2
=δT(P(I ⊗A)+(I ⊗AT)P)δ-cδTP((L+G)⊗BK )δ
N N 2
- cδT((L+G)⊗BK )TPδ
2
=δT(P(I ⊗A-c(L+G)⊗BK )+(I ⊗A-c(L+G)⊗BK )TP)δ
N 2 N 2
=δT(PA +ATP)δ=-δTQδ<-δTP(I ⊗B)R-1(I ⊗BT)Pδ≤0.
cl cl N N

5.8 Optimal Cooperative Control for General Digraphs: Performance … 177
Thus, the control is stabilizing to the origin, as assumed. Also, the performance
integrand equals
(δ,u)=δT u T
 
   c2((L+G)⊗K 2 c ) R T ( R (L (( + L G + ) G ⊗ )⊗ K K ) 2 - ) ( - I P ⊗ (I N BT ⊗ )P A)-(I N ⊗AT)P c((L+G)⊗K 2 ) R TR-P(I N ⊗B)     δ u   >0
2 N
and (δ,u)>0 by Schur complement if inequalities (5.55), (5.56) hold. The con-
trol is optimal since
1
u=φ(δ)=- R-1(LT +gT∇V)
2 2
1
=- R-1(2(cR((L+G)⊗K )-(I ⊗BT)P)δ+2(I ⊗BT)Pδ)
2 2 N N
1
=- R-1(2cR((L+G)⊗K ))δ
2 2
=-c(L+G)⊗Kδ
2
The performance integrand evaluated at the optimal control satisfies
(δ,φ(δ))=δT c2((L+G)⊗K )TR((L+G)⊗K )-P(I ⊗A)-(I ⊗AT)Pδ
 2 2 N N 
+δTc2((L+G)⊗K )TR((L+G)⊗K )δ
2 2
-2cδT c((L+G)⊗K )TR-P(I ⊗B)((L+G)⊗K )δ
 2 N  2
=-δT P(I ⊗A)+(I ⊗AT)Pδ+2cδTP(I ⊗B)((L+G)⊗K )δ
 N N  N 2
=-δT P(I ⊗A)+(I ⊗AT)Pδ+2cδTP((L+G)⊗BK )δ
 N N  2
=δT (c(L+G)⊗BK -I ⊗A)TP+P(c(L+G)⊗BK -I ⊗A)δ
 2 N 2 N 
=δT -ATP-PA )δ=δTQδ>δTP(I ⊗B)R-1(I ⊗BT)Pδ≥0
 cl cl  N N
Hence, all the conditions of Lemma 5.2b are satisfied, which concludes the proof.
□
Specifying the form of P and R as P= P⊗P, R= R ⊗R and assum-
1 2 1 2
ing further that K = R−1BTP, where P is a solution of local Riccati equation
2 2 2 2
PA+ATP +Q −PBR−1BTP =0, as used in Theorems 5.4 and 5.5, the inequality
2 2 2 2 2 2
(5.56) becomes
cP(L+G)⊗PBK −P⊗(PA+ATP)+c(L+G)TP⊗KTBTP
1 2 2 1 2 2 1 2 2
−PR−1P⊗PBBR−1BTP >0.
1 1 1 2 2 2
Equivalently, since
PBK = KTBTP = PBR−1BTP = KTR K ≥0,
2 2 2 2 2 2 2 2 2 2

178 5 Cooperative Globally Optimal Control for Multi-Agent Systems …
one has
(cP(L+G)+c(L+G)TP −PR−1P)⊗KTR K
1 1 1 1 1 2 2 2
−P⊗(KTR K −Q )>0.
1 2 2 2 2
Note the similarity to condition (5.50) introduced in single-integrator consensus
problem in Sect. 5.8.2. If condition (5.50) is satisfied then for sufficiently high value
of the coupling gain c this constraint can be met.
Remark 5.10 Due to the connection of the inequality here and the one in the pre-
ceding section with inequalities for single-integrator systems (5.48) and (5.50),
respectively, the comments in Sect. 5.8.3 on constructing the suitable P matrix
1
apply here as well. ▋
Clearly, if Riccati conditions (5.38), (5.39) are satisfied, then the cross-weighting
term vanishes, for
cR((L+G)⊗K )=(I ⊗BT)P⇔c((L+G)⊗K )= R−1(I ⊗BT)P.
2 N 2 N
One should also note that choosing K = R−1BTP affords an infinite interval of
2 2 2
positive values for coupling gain c that achieve stabilization [18], which allows one
to find a sufficiently high value of c to satisfy inequality (5.55) without worrying
about losing stability of the closed-loop system.
5.9 Conclusion
In this chapter, we consider the global optimality of local distributed control pro-
tocols in terms of the overall performance of the team of all agents. It is seen that
globally optimal performance using standard LQR performance measures cannot
in general be guaranteed by using distributed control protocols for arbitrary di-
graphs. For linear distributed agent control protocols to yield global optimal team
behaviors, the graph topology must satisfy certain conditions. These conditions are
shown to define a new class of digraphs that admit global optimal control design
using distributed control protocols, namely, the digraphs whose Laplacian matrix
has a diagonal Jordan form. If this condition is satisfied, moreover, any admissible
global performance indices must be selected in a certain manner that depends on
the graph topology. This clarifies the interactions between stability, optimal per-
formance, and the communication graph topology in multi-agent systems. In Sect.
5.8, a more general LQR performance index is considered which has state-control
cross-weighting. It is shown that with proper choice of this performance index, opti-
mal cooperative control in distributed form can be achieved for any directed graph.
This shows that performance indices with state-control cross-weighting terms are in
some sense more natural for cooperative control on communication graphs.

References 179
References
1. Bernstein DS (2009) Matrix Mathematics, Theory Facts, and Formulas. Princeton University
Press, Princeton and Oxford
2. Borelli F, Keviczky T (2008) Distributed LQR design for identical dynamically decoupled
systems. IEEE Trans Automat Contr 53(8):1901–1912
3. Cao Y, Ren W (2010) Optimal linear-consensus algorithms: an LQR perspective. IEEE Trans
Syst Man Cybern 40(3):819–830
4. Dong W (2010) Distributed optimal control of multiple systems. Int J Contr 83(10):2067–
2079
5. Dunbar WB, Murray RM (2006) Distributed receding horizon control for multi-vehicle for-
mation stabilization. Automatica 42(4):549–558
6. Haddad W.M, Chellaboina V (2008) Nonlinear Dynamical Systems and Control, A Lyapu-
nov-Based Approach. Princeton University Press, Princeton and Oxford
7. Hengster-Movric K, Lewis FL (2013) Cooperative optimal control for multi-agent sys-
tems on directed graph topologies. IEEE Trans Automat Contr, in press. (DOI: 10.1109/
TAC.2013.2275670)
8. Jadbabaie A, Lin J, Morse A (2003) Coordination of groups of mobile autonomous agents
using nearest neighbour rules. IEEE Trans Automat Contr 48(6):988–1001
9. Jovanovic MR (2005) On the optimality of localized distributed controllers. In: Proc. Amer.
Control Conf., Portland, OR, pp. 4583–4588
10. Lewis FL, Vrabie D, Syrmos VL (2012) Optimal Control, 3rd edn. John Wiley & Sons
11. Olfati-Saber R, Murray RM (2003) Consensus protocols for networks of dynamic agents. In:
Proc. Amer. Control Conf., Denver, CO, pp. 951–956
12. Olfati-Saber R, Murray RM (2004) Consensus problems in networks of agents with switch-
ing topology and time-delays. IEEE Trans Automat Contr 49(9):1520–1533
13. Semsar-Kazerooni E, Khorasani K (2009) Multi-agent team cooperation: a game theory ap-
proach. Automatica 45(10):2205–2213
14. Slotine JJ, Li W (1991) Applied Nonlinear Control. New Jersey, Prentice Hall
15. Vamvoudakis KG, Lewis FL (2011) Policy iteration algorithm for distributed networks and
graphical games. In: Proc. IEEE Conf. Decision Control and European Control Conf., Or-
lando, FL, pp. 128–135
16. Wang XF, Chen G (2002) Pinning control of scale free dynamical networks. Physica A
310:521–531
17. Zhang H, Lewis FL (2011) Optimal design for synchronization of cooperative systems: state
feedback, observer and output feedback. IEEE Trans Automat Contr 56(8):1948–1952
18. Zhang H, Lewis FL (2012) Lyapunov, adaptive, and optimal design techniques for coopera-
tive systems on directed communication graphs. IEEE Trans Industr Elec 59(7):3026–3041

Chapter 6
Graphical Games: Distributed Multiplayer
Games on Graphs
In Chaps. 3 and 4, we showed that locally optimal Riccati design of cooperative
control protocols can guarantee synchronization of multi-agent systems on com-
munication graphs. The control protocols turned out to be distributed in the sense
that the control of each agent only depends on the allowable information available
in the graph, namely, information about the agent and its neighbors. By contrast, in
Chap. 5 we saw that for a linear distributed protocol to be globally optimal for mul-
ti-agent teams on graphs, the global performance index must be selected to depend
on the graph topology. Specifically, global performance measures should depend
on the graph Laplacian matrix. Moreover, the standard linear quadratic regulator
(LQR) problem does not have a linear distributed protocol solution unless the graph
is of a certain class, namely, the graph Laplacian matrix must be simple—it must
have a diagonal Jordan form.
In this chapter, it is seen that distributed control protocols that both guarantee
synchronization and are globally optimal for the multi-agent team always exist on
any sufficiently connected communication graph if a different definition of optimal-
ity is used. To this end, we study the notion of Nash equilibrium for multiplayer
games on graphs. This leads us to the idea of a new sort of differential game—
graphical games. In graphical games, each agent has its own dynamics as well as its
own local performance index. The dynamics and local performance indices of each
agent are distributed; they depend on the state of the agent, the control of the agent,
and the controls of the agent’s neighbors. We show how to compute distributed con-
trol protocols that guarantee global Nash equilibrium for multi-agent teams on any
graph that has a spanning tree.
Teams of multi-agent systems arise in several domains of engineering and can be
used to solve problems which are difficult for an individual agent to solve. Strategies
for team decision problems, including optimal control, N-player games (H-infinity
control and nonzero sum), and so on, are normally solved for off-line by solving
associated matrix equations such as the coupled Riccati equations or coupled Ham-
ilton–Jacobi (HJ) equations. However, using that approach players cannot change
their objectives online in real time without calling for a completely new off-line
solution for the new strategies. Therefore, in this chapter we bring together coopera-
F. L. Lewis et al., Cooperative Control of Multi-Agent Systems, 181
Communications and Control Engineering, DOI 10.1007/978-1-4471-5574-4_6,
© Springer-Verlag London 2014

182 6 Graphical Games: Distributed Multiplayer Games on Graphs
tive control, game theory, and reinforcement learning (RL) to present a multi-agent
formulation for online solution of team games.
The notion of graphical games is developed for dynamical multi-agent systems,
where both the dynamics and the performance indices for each node depend only
on local neighbor information. It is shown that standard definitions for Nash equi-
librium are not sufficient for graphical games and a new definition of “Interactive
Nash Equilibrium” is given. Based on RL principles, we give a cooperative policy
iteration (PI) algorithm for graphical games that converges to the best response
when the neighbors of each agent do not update their policies and to the cooperative
Nash equilibrium when all agents update their policies simultaneously. This is used
to develop RL methods for online adaptive learning solutions of graphical games in
real time along with proofs of stability and convergence.
6.1 Introduction: Games, RL, and PI
Game theory provides an ideal environment in which to study multiplayer decision
and control problems and offers a wide range of challenging and engaging prob-
lems. Game theory [5, 29, 31] has been successful in modeling strategic behavior,
where the outcome for each player depends on the actions of himself and all the
other players. Every player chooses a control to minimize independently from the
others his own performance objective. Multiplayer cooperative games rely on solv-
ing coupled HJ equations, which in the linear quadratic case reduce to the coupled
algebraic Riccati equations [1, 5, 10, 11]. These coupled equations are difficult to
solve. Solution methods are generally off-line and generate fixed control policies
that are then implemented in online controllers in real time.
RL is a subarea of machine learning concerned with how to methodically modify
the actions of an agent (player) based on observed responses from its environment
[30]. RL methods have allowed control systems researchers to develop algorithms
to learn online in real time the solutions to optimal control problems for dynamic
systems that are described by difference or ordinary differential equations. These
involve computational intelligence techniques known as policy iteration (PI) and
value iteration [6, 30], which refer to a class of algorithms with two steps, policy
evaluation and policy improvement. These methods have primarily been developed
for discrete-time systems, and implementation for control systems design has been
developed through approximation of the value function [6, 40, 41]. Neurodynamic
programming [6] finds optimal control solutions by off-line computation using val-
ue function approximation (VFA) and PI. The approximate dynamic programming
(ADP) methods of Werbos [40, 41] show how to use VFA and value iteration to com-
pute optimal control solutions online in real time using data measurements available
along the system trajectories. Thus, RL provides effective means of learning solutions
to HJ equations online. Applications of ADP are further developed in [3, 4, 9] and
surveyed in [38]. In control theoretic terms, the PI algorithm amounts to learning the
solution to a Lyapunov equation, and then updating the policy through minimizing

6.2 Synchronization and Node Error Dynamics 183
a Hamiltonian function. Practical methods for applying PI and value iteration to
continuous-time systems have been developed in [2] and using the integral RL
methods in [35, 36].
RL methods have been used to solve multiplayer games for finite-state systems
in [8, 25]. RL has been applied to learn online in real time the solutions for opti-
mal control problems for dynamic systems and differential games in [9, 14, 20, 23,
32, 33].
This chapter brings together cooperative control, RL, and game theory to study
multiplayer differential games on communication graph topologies. A new class of
differential games is introduced—the graphical games. In graphical games, each
agent has its own dynamics as well as its own local performance index. The dynam-
ics and local performance indices of each agent are distributed; they depend on the
state of the agent, the control of the agent, and the controls of the agent’s neigh-
bors. This graphical game allows for synchronization as well as Nash equilibrium
solutions on communication graphs. It is shown that standard definitions for Nash
equilibrium are not sufficient for graphical games and a new definition of “Interac-
tive Nash Equilibrium” is given. We develop coupled Riccati equations for solution
of graphical games. A PI algorithm for solution of graphical games is given that
relies only on local information from neighbor nodes. It is shown that this algorithm
converges to the best response policy of a node if its neighbors have fixed policies
and to the global Nash solution if all nodes update their policies. Finally, an online
adaptive learning algorithm is presented for computing the Nash equilibrium solu-
tions of graphical games. The approach here is based on VFA using neural network
(NN) adaptive control as given in [21].
The material in this chapter is from [34].
6.2 Synchronization and Node Error Dynamics
In this section, we recall some graph theory basics. We introduce the synchroniza-
tion problem for multi-agent systems connected by a communication graph. The
local neighborhood synchronization error dynamics are derived. These error dy-
namics are the basis for the definition of graphical games in the next section.
6.2.1 Graphs
Consider a graph Gr =(V,) with a nonempty finite set of N nodes V ={v,,v }
1 N
and a set of edges or arcs  ⊆V ×V. We assume the graph is simple, e.g., no re-
peated edges and (v,v )∉,∀i no self-loops. Denote the connectivity matrix as
i i
EE==[ee ] with e >0if (v ,v)∈ and e =0 otherwise. Note e =0. The set of
ijij ij j i ij ii
neighbors of a node v is N ={v :(v ,v )∈}, i.e., the set of nodes with arcs
i i j j i

184 6 Graphical Games: Distributed Multiplayer Games on Graphs
incoming to v. Define the in-degree matrix as a diagonal matrix D=diag(d ) with
i i
d = ∑e the weighted in-degree of node i (i.e., ith row sum of E). Define the
i ij
j∈Ni
graph Laplacian matrix as L= D−E, which has all row sums equal to zero.
A directed path is a sequence of nodes v ,v,,v such that
0 1 r
(v,v )∈,i∈{0,1,(cid:31),r-1}. A directed graph is strongly connected if there is a
i i+1
directed path from v to v for all distinct nodes v,v ∈V. A (directed) tree is a
i j i j
connected digraph where every node except one, called the root node, has in-degree
equal to one. A graph is said to have a spanning tree if a subset of the edges forms
a directed tree. A strongly connected digraph contains a spanning tree. In a strongly
connected graph, all nodes are root nodes.
General directed graphs with fixed topology are considered in this chapter.
6.2.2 Synchronization and Node Error Dynamics
Consider the N systems or agents distributed on communication graph Gr with node
dynamics
x = Ax +Bu (6.1)
i i i i
where x(t)∈n is the state of node i, u (t)∈mi its control input. Cooperative
i i
team objectives may be prescribed in terms of the local neighborhood tracking er-
ror δ ∈(cid:25)n [17] as
i
δ = ∑ e (x -x )+ g (x -x ) (6.2)
i ij i j i i 0
j∈Ni
The pinning gain g ≥0 is nonzero for a small number of nodes i that are coupled
i
directly to the leader or control node x , and g >0 for at least one i [24, 39]. We
0 i
refer to the nodes i for which g ≠0 as the pinned or controlled nodes. Note that
i
δ represents the information available to node i for state feedback purposes as
i
dictated by the graph structure, depending as it does only on immediate neighbors
in the graph.
The state of the control or target node is x (t)∈n which satisfies the dynamics
0
x = Ax (6.3)
0 0
Note that this is in fact a command generator [19] and we seek to design a coopera-
tive control command generator tracker. Note that the trajectory generator A may
not be stable. As such, this command generator captures a wide range of motion
trajectories, including position unit step commands, velocity unit ramp commands,
oscillatory commands (which have applications in hard disk drive tracking control),
and more.

| 6.2   Synchronization and Node Error Dynamics  |     |     |     |     |     |     |     | 185 |
| ---------------------------------------------- | --- | --- | --- | --- | --- | --- | --- | --- |
The synchronization control design problem is to design local control protocols
u (t)∈mi so that all the nodes in Gr synchronize to the state of the control node,
i
i.e., one requires x(t)→x (t),∀i. The control protocols must be distributed in the
i 0
sense that they depend for each agent on information locally available in the graph,
that is, on the states of the agent’s immediate neighbors.
From (6.2), the overall error vector for network Gr is given by

|             | δ=((L+G)⊗I |          | )(x-x | )=((L+G)⊗I |     | )ζ    |     | (6.4)  |
| ----------- | ---------- | -------- | ----- | ---------- | --- | ----- | --- | ------ |
|             |            |          | n     | 0          |     | n     |     |        |
|             |            |          |       |            | T   | T     | T   | T nN,  |
| where  the  | global     | vectors  |       | are  x     | x   | x     | x   | R      |
|             |            |          |       |            | = 1 | 2 ··· | N   | ∈      |
|             |            | T        |       | T          |     |       |     |        |
δ= δ T δ T (cid:31) δxT  ∈x T  nNx, T  and   x =x TIx ∈(cid:25)R nnN (cid:31) N,  with  I 1 I n(cid:30) RnN n
|  1 2 | N=  |  1 | 2 · ·· | 0 N 0 ∈ |     | =   | ⊗   | ∈ × |
| ----- | --- | --- | ------ | ------- | --- | --- | --- | --- |
|       |     |     |        |         |     | −   | −   |     |
and 1 the N-vector of (cid:31)ones. The Kronecke(cid:30)r product is   [7].  G RN N is a
|     |     |     |     |     |     | ⊗   |     | ×   |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
diagonal matrix with diagonal entries equal to the pinning gains g. The (global)  ∈
i
consensus or synchronization error (e.g., the disagreement vector in [27]).
|     |     |     | ζ=(x-x | )∈(cid:25)nN |     |     |     | (6.5) |
| --- | --- | --- | ------ | ------------ | --- | --- | --- | ----- |
0
The communication digraph is assumed to be strongly connected. Then, if g ≠0
i
for at least one i, (L+G) is nonsingular with all eigenvalues having positive real
parts [17]. The next result therefore follows from (6.4), the Cauchy–Schwartz in-
equality, and the properties of the Kronecker product [7].
Lemma 6.1 Let the graph have a spanning tree and g >0 for at least one root
i
node i. Then L + G is nonsingular and the global consensus synchronization error
is bounded by
|     |     |     | ζ ≤ δ | /σ(L+G) |     |     |     | (6.6) |
| --- | --- | --- | ----- | ------- | --- | --- | --- | ----- |
with σ(L+G) being the minimum singular value of (L G), and δ(t)≡0 if and
+
only if the nodes synchronize, that is,
|     |     |     | x(t)= | Ix (t) |     |     |     | (6.7) |
| --- | --- | --- | ----- | ------ | --- | --- | --- | ----- |
0
According to this lemma, if the local neighborhood errors (6.2) are small and the
graph has a spanning tree with pinning into at least one root node, then the global
disagreement errors (6.5) are small and all nodes synchronize close to the leader’s
state. We specify the next assumption.
Assumption 6.1 The graph has a spanning tree with pinning gain  g >0 for at
i
least one root node i.
To find the dynamics of the local neighborhood tracking error, write
|     |     | (cid:28) ∑ |     |     |     |     |     |     |
| --- | --- | ---------- | --- | --- | --- | --- | --- | --- |
  δ = e (x(cid:28) -x(cid:28) )+ g (x(cid:28) -x(cid:28) ) (6.8)
|     |     | i   | ij  | i j | i i 0 |     |     |     |
| --- | --- | --- | --- | --- | ----- | --- | --- | --- |
j∈Ni

186 6  Graphical Games: Distributed Multiplayer Games on Graphs
which by using equations (6.1) and (6.3) becomes
(cid:28)
|     | δ = Aδ +(d | +g )Bu - | ∑ e B u | (6.9) |
| --- | ---------- | -------- | ------- | ----- |
|     | i i        | i i i i  | ij j j  |       |
j∈Ni
| ∈(cid:25)n,u ∈(cid:25)mi,∀i. |     |     |     |     |
| ---------------------------- | --- | --- | --- | --- |
with δ
| i i |     |     |     |     |
| --- | --- | --- | --- | --- |
These error dynamics are dynamical systems where the error of agent i is driven
by the control input of agent i and also by the control inputs of its neighbors in the
graph. Note that if the control inputs are selected to make all the local neighbor-
hood error dynamics asymptotically stable and the graph has a spanning tree with
pinning into at least one root node, then Lemma 1 shows that the states of all agents
synchronize to the leader’s state.
6.3   Cooperative Multiplayer Games on Graphs
In this section, we define the core idea of this chapter—graphical games. This idea
captures notions of differential game theory for multiple dynamical agents con-
nected by a communication graph topology. In graphical games, not only are the
dynamics and control policies of the agents important but also of vital concern is the
topology of the communication graph. We wish to achieve synchronization while
simultaneously optimizing some local performance specifications on the agents. To
capture this, we intend to use the machinery of multiplayer games [5].
A key idea in game theory is the relation between the control policy of a single
agent and the control policies of other agents in the game. In graphical games,
there are two main sets of agents with which the policy of a single agent must be
compared: the set of all its neighbors and the set of all other agents in the graph.
Therefore, define
|     | u    | ={u : j∈N, | j≠i} | (6.10) |
| --- | ---- | ---------- | ---- | ------ |
|     | Gr−i | j          |      |        |
as the set of policies of all the other nodes in the graph other than node i. Define
|                           |                                    | u ={u : j∈N} |     | (6.11) |
| ------------------------- | ---------------------------------- | ------------ | --- | ------ |
|                           |                                    | −i j         | i   |        |
| as the set of policies {u | : j∈N} of the neighbors of node i. |              |     |        |
j i
6.3.1   Cooperative Performance Index
In the error dynamics (6.9), the state of each agent is affected by its own control
policies and also by the control policies of its immediate neighbors in the graph.
This structure comes from the desired objective of synchronizing the states of all the

| 6.3   Cooperative Multiplayer Games on Graphs  |     |     |     |     |     |     |     |     | 187 |
| ---------------------------------------------- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
agents. Therefore, let us define a multiplayer game where likewise the performance
index for each agent depends on its own control policies and also on the control pol-
icies of its immediate neighbors in the graph. Define the local performance indices
∞
1
|     |           |       | ∫(δTQδ | +uTR |      | ∑uTR |      |     |     |
| --- | --------- | ----- | ------ | ---- | ---- | ---- | ---- | --- | --- |
|     | J (δ(0),u | ,u )= |        |      | u    | +    | u    | )dt |     |
|     | i i       | i -i  | 2 i    | ii i | i ii | i    | j ij | j   |     |
|     |           |       | 0      |      |      | j∈N  | i    |     |     |
∞
1
|     |     | ≡   | ∫L(δ(t),u |     | (t),u | (t))dt |     |     | (6.12) |
| --- | --- | --- | --------- | --- | ----- | ------ | --- | --- | ------ |
|     |     |     | i         | i i | -i    |        |     |     |        |
2
0
where  all  weighting  matrices  are  constant  and  symmetric  with
Q >0,R >0,R 0. Note that the ith performance index includes only infor-
| ii  | ii ij ≥ |     |     |     |     |     |     |     |     |
| --- | ------- | --- | --- | --- | --- | --- | --- | --- | --- |
mation about the inputs of node i and its neighbors.
It is desired to select control policies for all the agents such that the performance
indices of each agent are minimized in the sense that
∞
1
|     | J*(δ(0))=min |     | ∫(δTQδ | +uTR | u      | + ∑uTR | u    | )dt | (6.13) |
| --- | ------------ | --- | ------ | ---- | ------ | ------ | ---- | --- | ------ |
|     | i i          |     | i      | ii i | i ii i |        | j ij | j   |        |
u 2
|     |     | i   | 0   |     |     | j∈N |     |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
i
for all agents i. This optimization problem only takes into account directly the con-
| trol policy u of agent i and the value of its own performance index. The policies of  | i   |     |     |     |     |     |     |     |     |
| ------------------------------------------------------------------------------------- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
other agents in the game come into play only indirectly through their influence on
J (δ(0),u ,u ). This has been called a noncooperative game in the literature in the
| i i | i -i |     |     |     |     |     |     |     |     |
| --- | ---- | --- | --- | --- | --- | --- | --- | --- | --- |
sense that each player only takes into account directly its own policy and not those
of other agents in the graph.
We call minimizing (6.13) subject to the dynamics (6.9) a graphical game. It
depends on the topology of the communication graph Gr =(V,).
Though the optimization objective (6.13) is myopic and does not take into ac-
count the neighbors’ policies, it is seen that the neighbors’ policies are weighted in
the performance index (6.12). Therefore, in some sense each agent tries to minimize
its own performance index without causing its neighbors to use undue control energy.
If optimization problem (6.13) is solved, then boundedness of J (δ(0),u ,u )
|     |     |     |     |     |     |     |     | i i | i -i |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | ---- |
for all i implies that the integrand vanishes with t. Then, positive definiteness of
Q ii guarantees that the states δ (t) go to zero, so that local error dynamics (6.9)
i
are stable. Hence, if the graph is strongly connected, the states of equations (6.1)
synchronize to the leader (6.3) in view of Lemma 6.1.
For dynamics (6.9) with performance objectives (6.12), introduce the associated
Hamiltonians
|     |           |       |    |     |        |     |      |      |     |
| --- | --------- | ----- | --- | --- | ------ | --- | ---- | ----- | --- |
|     |           |       | pT  |     |        |     | ∑    |       |     |
|     | H (δ,p ,u | ,u )≡ | Aδ | +(d | +g )Bu | -   | e    | B u  |     |
|     | i i i     | i -i  | i   | i   | i i    | i i | ij   | j j   |     |
|     |           |       |    |     |        |     | j∈Ni |      |     |
|     |           |       |    |     |        |     |      |      |     |
1
|     |     | +   | δTQδ | +uTR | u    | + ∑ | uTR u |    | (6.14) |
| --- | --- | --- | ----- | ---- | ---- | --- | ----- | --- | ------ |
|     |     |     | i     | ii i | i ii | i   | j ij  | j   |        |
|     |     |     | 2    |      |      |     |       |    |        |
j∈Ni

188 6  Graphical Games: Distributed Multiplayer Games on Graphs
where p is the costate variable. Necessary conditions [22] for a minimum of (6.12)
i
are (6.9) and the costate equations

∂H
|     |     |     |     | -p(cid:28) = | i ≡ ATp +Qδ |      |     | (6.15) |
| --- | --- | --- | --- | ------------ | ----------- | ---- | --- | ------ |
|     |     |     |     | i            | i           | ii i |     |        |
∂δ
i
and the stationarity conditions
∂H
|     |     |     |     |      |         | )R−1BTp |     |        |
| --- | --- | --- | --- | ---- | ------- | ------- | --- | ------ |
|     |     |     | 0=  | i ⇒u | =−(d +g |         |     | (6.16) |
|     |     |     |     | ∂u   | i i i   | ii i    | i   |        |
i
6.3.2   Global and Local Performance Objectives: Cooperation
and Competition
The overall objective in graphical games is to ensure synchronization of all the
states  x(t) to  x (t). The multiplayer game formulation just presented allows for
|     | i   | 0   |     |     |     |     |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
considerable freedom of each agent while achieving this objective. The minimiza-
tion objective in (6.13) is myopic or “noncooperative” in that it only takes into ac-
count directly the control policy of agent i. This has been called a noncooperative
game in the literature. Nevertheless, the agents can have conflicting as well as col-
laborative team objectives as seen in the following development.
The performance objective of each node can be written as
|         |                    |       | N   |             | N               |             |                         |        |
| ------- | ------------------ | ----- | --- | ----------- | --------------- | ----------- | ----------------------- | ------ |
|         |                    |       | 1   | 1           |                 |             |                         |        |
|         |                    |       | ∑w  | ∑w          |                 |             | +Jconflict              |        |
|         |                    | J i = | ij  | J j +       | ij (J i -J      | j )≡ J team | i                       | (6.17) |
|         |                    |       | N   | N           |                 |             |                         |        |
|         |                    |       | j=1 |             | j=1             |             |                         |        |
| where w | =1 when j = i or e |       |     |             | =0 otherwise, J |             |                         |        |
|         |                    |       |     |  > 0, and w |                 |             |  is the overall (“cent- |        |
|         | ij                 |       |     | ij          | ij              |             | team                    |        |
er of gravity”) performance objective of the networked team and Jconflict is the con-
i
flict of interest or competitive objective. J  measures how much the players are
team
vested in common goals, and Jconflict expresses to what extent their objectives differ.
i
The objective functions can be chosen by the individual players, or they may be as-
signed to yield some desired team behavior.
In the case of N-player zero-sum games, one has J =0 and there are no com-
team
mon objectives. One case is the 2-player zero-sum game, where J =−J, and one
|     |     |     |     |     |     |     | 2   | 1   |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
=0 and Jconflict
| has J |      |     | = J. |     |     |     |     |     |
| ----- | ---- | --- | ---- | --- | --- | --- | --- | --- |
|       | team |     | i    | i   |     |     |     |     |
6.3.3   Graphical Games
Interpreting the control inputs u,u  as state-dependent policies or strategies, the
i j
value function for node i corresponding to those policies is
∞
1
|     |     | V(δ(t))= |     | ∫(δTQδ | +uTR u   | + ∑uTR | u )dt  | (6.18) |
| --- | --- | -------- | --- | ------ | -------- | ------ | ------ | ------ |
|     |     | i        | i   | i ii   | i i ii i |        | j ij j |        |
2
j∈N
|     |     |     |     | 0   |     | i   |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |

| 6.3  |  Cooperative Multiplayer Games on Graphs  |     |     |     |     |     | 189 |
| ---- | ----------------------------------------- | --- | --- | --- | --- | --- | --- |
Given fixed policies of its neighbor nodes, the control objective of agent i in the
graphical game is to determine
∞
1
|     | V*(δ(t))=min |     | ∫(δTQδ | +uTR | u + ∑uTR | u )dt  | (6.19) |
| --- | ------------ | --- | ------ | ---- | -------- | ------ | ------ |
|     |              | i i | i ii   | i i  | ii i     | j ij j |        |
|     |              | u   | 2      |      |          |        |        |
|     |              |     | i 0    |      | j∈N      |        |        |
i
This is known as the best response policy of agent i to the fixed policies of its
neighbors.
Definition 6.1 Admissible Policies Control policies u, ∀i are defined as admis-
i
sible if u  are continuous, u (0)=0, u  stabilize systems (6.9) locally, and the
|     | i   |     | i   | i   |     |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- |
values (6.18) are finite.
When V  is finite, using Leibniz’s formula, a differential equivalent to (6.18) is
i
given in terms of the Hamiltonian functions (6.14) by the graphical games Bellman
equations
|     |       |         |          |     |        |           |     |
| --- | ----- | ------- | --------- | --- | ------ | ---------- | --- |
|     |       | ∂V      | ∂V T      |     |        |            |     |
|     |       | i       | i         |     |        | ∑e         |     |
|     | H (δ, | , u , u | -i )≡ Aδ | +(d | +g )Bu | - B u     |     |
|     | i     | i ∂δ i  | ∂δ       | i i | i i    | i ij j j  |     |
|     |       | i       | i        |     |        | j∈N       |     |
i
|     |     |     |    |     |     |    |     |
| --- | --- | --- | --- | --- | --- | --- | --- |
1
|     |     |     | TQ   |      | TR     | ∑uT      |        |
| --- | --- | --- | ---- | ---- | ------ | -------- | ------ |
|     |     |     | + δ | δ +u | u +    | R u  =0 | (6.20) |
|     |     |     | 2 i | ii i | i ii i | j ij j  |        |
|     |     |     |     |      |        |         |        |
j∈N i
with boundary condition V(0)=0. (The gradient is disabused here as a column
i
vector.) That is, solution of equation (6.20) serves as an alternative to evaluating
the infinite integral (6.18) for finding the value associated with the current feedback
policies. It is shown in the proof of Theorem 6.2 that (6.20) is a Lyapunov equation.
According to (6.20) and (6.14) one equates the costate  p =∂V /∂δ.
|     |     |     |     |     |     | i i i |     |
| --- | --- | --- | --- | --- | --- | ----- | --- |
Figure 6.1 shows an example communication graph that will be used later for
simulation purposes. The incoming edges show the flow of the local information
that is exchanged between the agents, e.g., node 2 receives information only from
agent 1 (incoming edge). This is the sort of structure captured in the graphical game.
Such topologies appear in practical situations such as coordination of heterogene-
ous teams of unmanned vehicles.
We assume throughout the chapter that the game is well formed in the following
sense.
Definition 6.2 Well-Formed Graphical Game The graphical game with local
dynamics (6.9) and performance indices (6.12) is well formed if B ≠0(cid:18)e ∈,
|     |     |     |     |     |     | j   | ij  |
| --- | --- | --- | --- | --- | --- | --- | --- |
R ij ≠0(cid:18)e ij ∈. This means that whenever we have an edge in the communication
graph, the input matrix B and the user-defined matrix R in the performance indi-
|     |     | j   |     |     |     | ij  |     |
| --- | --- | --- | --- | --- | --- | --- | --- |
ces should be different than zero.
Employing the stationarity condition (6.16), one obtains the control policies

190 6  Graphical Games: Distributed Multiplayer Games on Graphs
F ig. 6.1   Communication
Graph
∂V
|     | u =u | (V )≡-(d | +g )R - 1B | T i ≡-h (p ) |        |
| --- | ---- | -------- | ---------- | ------------ | ------ |
|     | i i  | i i      | i i i i    | i i          | (6.21) |
∂δ
i
In graphical games, we are interested in Nash equilibrium.
Definition 6.3 Nash Equilibrium (Global Nash equilibrium) An N-tuple of poli-
{ u*,u*,...,u*}
cies   is said to constitute a global Nash equilibrium solution for an
| 1 2                          | Ν   |                  |          |             |        |
| ---------------------------- | --- | ---------------- | -------- | ----------- | ------ |
| N-player game if for all i∈N |     | and ∀u,u         |  [5]     |             |        |
|                              |     |                  | i Gr−i   |             |        |
|                              | J*  | (u*,u*           | )≤       | ,u*         | (6.22) |
|                              |     | i (cid:17) J i i | Gr-i J i | (u i Gr-i ) |        |
The N-tuple of game values  { J*,J*,...,J*} is known as a Nash equilibrium out-
|     |     | 1 2 | Ν   |     |     |
| --- | --- | --- | --- | --- | --- |
come of the N-player game.
In Nash equilibrium, each player is in best response to all other players in the game.
Then, it does not benefit any player i to change his policy u  unilaterally when
i
others do not, because any change in policy u  will increase his cost J  or at best
|     |     |     | i   | i   |     |
| --- | --- | --- | --- | --- | --- |
leave it the same.
The distributed multiplayer graphical game with local dynamics (6.9) and local
performance indices (6.12) should be contrasted with standard multiplayer games
[5] which have centralized dynamics
|     |     |            | N      |     |        |
| --- | --- | ---------- | ------ | --- | ------ |
|     |     | z(cid:28)= | Az+∑Bu |     | (6.23) |
i i
i=1
where  z∈n is the state, u (t)∈mi  is the control input for every player, and
i
where the performance index of each player depends on the control inputs of all
other players. In the graphical games, by contrast, each node’s dynamics and per-
formance index only depend on its own state, its control, and the controls of its
immediate neighbors in the graph. See Fig. 6.1, where only local information is

| 6.3   Cooperative Multiplayer Games on Graphs  |     |     |     |     | 191 |
| ---------------------------------------------- | --- | --- | --- | --- | --- |
exchanged. On the contrary, in the standard games [5] the communication graph is
complete (e.g., fully connected). It can be shown that graphical games are a special
case of standard multiplayer games where the graph topology is explicitly revealed.
Static (e.g., nondynamic) graphical games have been studied in the computa-
tional intelligence community [15, 16, 29]. A (nondynamic) graphical game has
been defined there as a tuple (Gr,U,v) with Gr =(V,) being a graph with N
nodes, action set U =U ××U  with U  being the set of actions available to
|              | 1     | N                        | i   |                |       |
| ------------ | ----- | ------------------------ | --- | -------------- | ----- |
|              | v v   | v T                      |     |                |       |
| node i, and  | 1     | N a payoff vector, with  |     | v (U ,{U : j∈N | })∈  |
|              | = ··· |                          |     | i i j          | i     |
being the payoff function of node i. It is important to note that the payoff of node i
|     | (cid:31) | (cid:30) |     |     |     |
| --- | -------- | -------- | --- | --- | --- |
only depends on its own action and those of its immediate neighbors. The work on
static graphical games has focused on developing algorithms to find standard Nash
equilibria for payoffs generally given in terms of matrices at each node. Multiple
Nash equilibria may occur. Such algorithms are simplified in that they only have
complexity on the order of the maximum node degree in the graph, not on the order
of the number of players N. Undirected graphs are studied, and it is assumed that
the graph is connected.
The intention in this chapter is to provide online real-time adaptive methods
for solving differential graphical games that are distributed in nature. That is, the
control protocols and adaptive algorithms of each node are allowed to depend only
on information about itself and its neighbors. Moreover, as the game solution is be-
ing learned, all node dynamics are required to be stable, until finally all the nodes
synchronize to the state of the control node. These online methods are discussed in
Sect. 6.7.
The following notions are needed in the study of differential graphical games.
Definition 6.4 Best Response Agent i’s best response to fixed policies u  of his
-i
neighbors is the policy u* such that [29]
i

|                    |              | J (u*,u | )≤ J (u,u ) |     | (6.24) |
| ------------------ | ------------ | ------- | ----------- | --- | ------ |
|                    |              | i i −i  | i i −i      |     |        |
| for all policies u |  of agent i. |         |             |     |        |
i
For centralized multi-agent games, where there is one single dynamics given by
(6.23) and the performance of each agent depends on the actions of all other agents,
an equivalent definition of Nash equilibrium is that each agent is in best response to
all other agents. In graphical games, if all agents are in best response to their neigh-
bors, then all agents are in Nash equilibrium, as seen in the proof of Theorem 6.1.
However, a counterexample shows the problems with the definition of Nash
equilibrium in graphical games. Consider the completely disconnected graph with
empty edge set where each node has no neighbors. Then Definition 6.4 holds if each
agent simply chooses his single-player optimal control solution J* = J (u*), since
|     |     |     |     | i   | i i |
| --- | --- | --- | --- | --- | --- |
for the disconnected graph case one has
|     | J (u | )= J (u ,u | )= J (u ,u′ | ), ∀i | (6.25) |
| --- | ---- | ---------- | ----------- | ----- | ------ |
|     | i i  | i i Gr-i   | i i Gr-i    |       |        |

192 6 Graphical Games: Distributed Multiplayer Games on Graphs
for any choices of the two sets u ,u′ of the policies of all the other nodes.
Gr-i Gr-i
That is, the value function of each node does not depend on the policies of any other
nodes.
Note, however, that Definition 6.3 also holds, that is, the nodes are in a global
Nash equilibrium. Pathological cases such as this counterexample cannot occur in
the standard games with centralized dynamics (6.23), particularly because stabiliz-
ability conditions are usually assumed.
6.4 Interactive Nash Equilibrium
The counterexample in the previous section shows that in pathological cases when
the graph is disconnected, agents can be in Nash equilibrium, yet have no influence
on each others’ games. In such situations, the definition of coalition-proof Nash
equilibrium [28] may also hold, that is, no set of agents has an incentive to break
away from the Nash equilibrium and seek a new Nash solution among themselves.
To rule out such undesirable situations and guarantee that all agents in a graph
are involved in the same game, we make the following stronger definition of global
Nash equilibrium.
Definition 6.5 Interactive Global Nash Equilibrium An N-tuple of policies
{ u*,u*,...,u*}
is said to constitute an interactive global Nash equilibrium solution
1 2 Ν
for an N-player game if, for all i∈N, the Nash condition (6.22) holds and in addi-
tion there exists a policy u′ such that
k
J (u*,u* )≠ J (u′,u* ) (6.26)
i k Gr-k i k Gr-k
for all i,k∈N. That is, at equilibrium there exists a policy of every player k that
influences the performance of all other players i.
If the systems are in interactive Nash equilibrium, the graphical game is well de-
fined in the sense that all players are in a single Nash equilibrium, with each player
affecting the decisions of all other players. Condition (6.26) means that the reaction
curve [5] of any player i is not constant with respect to all variations in the policy of
any other player k. A similar interactivity condition was used in [26].
The next results give conditions under which the local best responses in Defini-
tion 6.4 imply the interactive global Nash equilibrium of Definition 6.5.
Consider the systems (6.9) in closed loop with admissible feedbacks (6.16),
(6.21) denoted by u k = K k p k − v k for a single node k and u j = K j p j ,∀j≠k. Then
δ (cid:28) = Aδ +(d +g )BK p - ∑e B K p +e B v , k ≠i (6.27)
i i i i i i i ij j j j ik k k
j∈N
i

| 6.4  |  Interactive Nash Equilibrium  |     |     |     |     |     |     |     | 193 |
| ---- | ------------------------------ | --- | --- | --- | --- | --- | --- | --- | --- |
The global closed-loop dynamics are
|        |         | δ (cid:28) |  (I       | ⊗A) | ((L+G)⊗I |        | )diag(B | K )δ                      |        |
| ------ | ------- | ------------ | ---------- | --- | -------- | ------ | ------- | ---------------------------- | ------ |
|        |         |              |            | N   |          |        | n       | i i                          |        |
|        |         |             | =        |     |          |        |         |                           |        |
|        |         | p(cid:28)   | -diag(Q  | )   |          | -(I    | ⊗AT)    | p                        |        |
|        |         |              |           | ii  |          | N      |         |                              |        |
|        |         |              |  ((L+G)⊗I |     | )B      |        | δ     |                              |        |
|        |         |              | +         |     | n k      | v ≡ A | +Bv     |                              | (6.28) |
|        |         |              |            |     |         | k      |        | k                            |        |
|        |         |              |           | 0   |         |        | p     |                              |        |
|        |         |              |            |     |          | T      | T       |                              |        |
| with B | =diag(B |              | ) and  v   | k 0 |          | v      | 0       |  has all block entries zero  |        |
|        | k       |              | i ¯        | =   | ···      | k ···  |         |                              |        |
with v  in block k. Consider n(cid:31)ode i and let M >0 b(cid:30)e the first integer such that
k
[(L+G)M] ≠0, where [.]  denotes the element (i, k) of a matrix. That is, M is
|     |     | ik  |     | ik  |     |     |     |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
the length of the shortest directed path from k to i. Denote the nodes along this path
by k =k ,k ,,k ,k =i. Denote element (i, k) of L+G by (cid:16) . Then the n×m
|     | 0   | 1 M−1 | M   |     |     |     |     | ik  |     |
| --- | --- | ----- | --- | --- | --- | --- | --- | --- | --- |
block element in block row i and block column k of matrix A2(M-1)B is equal to

ik
A2(M-1)B = ∑ (cid:16) (cid:31)(cid:16) B K Q B (cid:31)B K Q B
|     |    |    |     | i,k | k,k | k   | k k     | k k   | k k k |
| --- | --- | --- | --- | --- | --- | --- | ------- | ----- | ----- |
|     |     |     |     | M-1 | 1   | M-1 | M-1 M-1 | M-2 1 | 1 1   |
k ,(cid:31),k
|     |     |     | M-1 | 1    |     |     |     |     |        |
| --- | --- | --- | --- | ---- | --- | --- | --- | --- | ------ |
|     |     | ≡   | ∑ B | B    |     |     |     |     | (6.29) |
|     |     |     | k   | k ,k |     |     |     |     |        |
M-1 M-1
k
M-1
RmkM− mk and [ ]ikdenotes the position of the block element in
| w h    | e r e   B ¯k    | ,k      | 1×  |     |     |     |     |     |     |
| ------ | --------------- | ------- | --- | --- | --- | --- | --- | --- | --- |
|        | M               | 1 ∈     |     |     |     |     |     |     |     |
| t h e  | b l o c k   m−a | t rix . |     |     |     |     |     |     |     |
The next Assumption 6.2a is required. Assumption 6.2b simplifies the upcoming
proof of Theorem 6.1.
Assumption 6.2
| a. B |         | RmkM− | 1× mk has rank m |     | , for all i,k. |     |     |     |     |
| ---- | ------- | ----- | ---------------- | --- | -------------- | --- | --- | --- | --- |
|      | ¯kM 1,k |       |                  |     | kM-1           |     |     |     |     |
|      | −       | ∈     |                  |     |                |     |     |     |     |
b.  All shortest paths to node i from node k pass through a single neighbor k -1 of
M
i, for all i,k.
An example case where Assumption 6.2a holds is when there is a single shortest
| path from k to i, m |     |     | =m,∀i, rank(B)=m,∀i. |     |     |     |     |     |     |
| ------------------- | --- | --- | -------------------- | --- | --- | --- | --- | --- | --- |
|                     |     |     | i                    |     | i   |     |     |     |     |
Lemma 6.2 Let (A,B ) be reachable for all  j∈N and let Assumption 6.2 hold.
j
Then the ith closed-loop system (6.27) is reachable from input v  if and only if there
k
exists a directed path from node k to node i.
Proof
Sufficiency If k =i, the result is obvious. Otherwise, the reachability matrix from
node k to node i has the n×m block element in block row i and block column k
given as

194 6 Graphical Games: Distributed Multiplayer Games on Graphs
ik
A2(M-1)B A2(M-1)+1B A2(M-1)+2B (cid:31)
 
B * * 
k ,k
 M-1 
 
 0 B * 
=∑ B k ∑ AB k ∑ A2B k (cid:31)  k M-1 ,k 
 M-1 M-1 M-1  (cid:29) 0 B
k M-1 k M-1 k M-1  k M-1 ,k 
 
 0 (cid:31) 0 (cid:30)
where * denotes nonzero entries. Under the assumptions, the matrix on the right has
full row rank and the matrix on the left is written as
B AB A2B (cid:31).
 k k k 
M−1 M−1 M−1
However, (A,B ) is reachable.
kM 1
−
Necessity
If there is no path from node k to node i, then the control input of node k cannot
influence the state or value of node i. □
Theorem 6.1 Interactive Nash Equilibrium Let (A,B) be reachable for all i∈N.
i
Let every node i be in best response to all his neighbors j∈N. Let Assumption 6.2
i
hold. Then all nodes in the graph are in interactive global Nash equilibrium if and
only if the graph is strongly connected.
Proof Let every node i be in best response to all his neighbors j∈N . Then
i
J (u*,u )≤ J (u,u ),∀i. Hence u =u*,∀u ∈u and J (u*,u* )≤
i i −i i i −i j j j −i i i -i
J (u ,u* ),∀i. However, according to (6.12) J (u*,u* )= J (u*,u* ,u ),
i i -i i i -i i i -i k
∀k∉{i}∪N so that J (u*,u* )≤ J (u,u* ),∀i and the nodes are in Nash
i i i Gr−i i i Gr−i
equilibrium.
Necessity
If the graph is not strongly connected, then there exist nodes k and i such that there
is no path from node k to node i. Then, the control input of node k cannot influence
the state or the value of node i. Therefore, the Nash equilibrium is not interactive.
Sufficiency
Let (A,B) be reachable for all i∈N. Then if there is a path from node k to node i, the
i
state δ is reachable from u , and from (6.12) input u can change the value J. Strong
i k k i
connectivity means there is a path from every node k to every node i and condition
(6.26) holds for all i,k∈N. □

| 6.5   Stability and Solution of Graphical Games  |     |     |     |     |     |     |     |     | 195 |
| ------------------------------------------------ | --- | --- | --- | --- | --- | --- | --- | --- | --- |
The reachability condition is sufficient but not necessary for interactive Nash
equilibrium.
According to the results just established, the following assumption is specified.
| Assumption 6.3  |     | (A,B) is reachable for all i∈N. |     |     |     |     |     |     |     |
| --------------- | --- | ------------------------------- | --- | --- | --- | --- | --- | --- | --- |
i
6.5   Stability and Solution of Graphical Games
Substituting control policies (6.21) into (6.20) yields the coupled cooperative game
HJ equations
|     |     | T    |        |        |       |       | T        |         |     |
| --- | --- | ---- | ------ | ------ | ----- | ----- | -------- | ------- | --- |
|     | ∂V  | i Ac | 1 δTQδ | 1      |       | )2 ∂V | i BR-1BT | ∂V i    |     |
|     |     | +    |        | +      | (d +g |       |          |         |     |
|     | ∂δ  | i    | 2 i    | ii i 2 | i     | i ∂δ  | i        | ii i ∂δ |     |
|     |     | i    |        |        |       |       | i        | i       |     |
T
|     |     | 1   |     | ∂V  |      |       | ∂V   |        |        |
| --- | --- | --- | --- | --- | ---- | ----- | ---- | ------ | ------ |
|     |     | ∑(d | )2  | j   | R-1R | R-1B  | T    | j      |        |
|     | +   |     | +g  |     | B    |       |      | =0,i∈N | (6.30) |
|     |     | 2   | j j | ∂δ  | j jj | ij jj | j ∂δ |        |        |
|     |     |     |     | j   |      |       |      | j      |        |
j∈N i
where the closed-loop matrices are
∂V
|     |     | Ac  |          |     | )2BR-1BT |      | i   |     |     |
| --- | --- | --- | -------- | --- | -------- | ---- | --- | --- | --- |
|     |     |     | = Aδ -(d | +g  |          |      |     |     |     |
|     |     | i   | i        | i   | i i      | ii i | ∂δ  |     |     |
i
∂V
j
|     |     |     | + ∑ e | (d +g | )B  | R-1B T | ,i∈N |     | (6.31) |
| --- | --- | --- | ----- | ----- | --- | ------ | ---- | --- | ------ |
|     |     |     |       | ij j  | j j | jj j   |      |     |        |
∂δ
|     |     |     | j∈N |     |     |     | j   |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
i
For a given V, define u* =u (V) as (6.21) given in terms of V. Then HJ equations
|     | i   |     | i i | i   |     |     |     | i   |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
(6.30) can be written as
∂V
i ,u*,u*
|     |     |     | H   | (δ,    |     | )=0 |     |     | (6.32) |
| --- | --- | --- | --- | ------ | --- | --- | --- | --- | ------ |
|     |     |     |     | i i ∂δ | i   | -i  |     |     |        |
i
There is one coupled HJ equation corresponding to each node, so solution of this
N-player game problem is blocked by requiring a solution to N coupled partial dif-
ferential equations. In the next sections, we show how to solve this N-player coop-
erative game online in a distributed fashion at each node, requiring only measure-
ments from neighbor nodes, by using techniques from RL.

196 6  Graphical Games: Distributed Multiplayer Games on Graphs
6.5.1   Coupled Riccati Equations
It is now shown that the coupled HJ equations (6.30) can be written as coupled Ric-
cati equations. For the global state δ given in (6.4), we can write the dynamics as
|     |     |     | δ (cid:31) =(I | ⊗A)δ+(L+G)⊗I |     | diag(B | )u  | (6.33) |
| --- | --- | --- | -------------- | ------------ | --- | ------ | --- | ------ |
|     |     |     | N              |              |     | n      | i   |        |
where u is the control given by
|     |     |     | u=−diag(R |     | −1BT)((D+G)⊗I |     | p)  | (6.34) |
| --- | --- | --- | --------- | --- | ------------- | --- | --- | ------ |
|     |     |     |           | ii  | i             |     | n   |        |
where diag(.) denotes diagonal matrix of appropriate dimensions. Furthermore, the
global costate dynamics are
∂H
⊗A)T
|     |     |     | −p(cid:31) = | ≡(I | p+diag(Q |     | )δ  | (6.35) |
| --- | --- | --- | ------------ | --- | -------- | --- | --- | ------ |
|     |     |     | ∂δ           |     | N        |     | ii  |        |
This is the same set of coupled dynamic equations as in the single-agent optimal
control [22]. The solution can be determined using coupled algebraic Riccati equa-
tions. To accomplish this the costate is written as
|     |     |     |     |     | p= Pδ |     |     | (6.36) |
| --- | --- | --- | --- | --- | ----- | --- | --- | ------ |
for some matrix P>0∈nNxnN.
The next result shows that (6.30) can be written in the form of coupled Riccati
equations.
Lemma 6.3 HJ equations (6.30) are equivalent to the coupled Riccati equations
|     |                 |     |     | 1   |       | 1         |     |         |
| --- | --------------- | --- | --- | --- | ----- | --------- | --- | ------- |
|     | δTPTAδ−δTPTBPδ+ |     |     |     | δTQδ+ | δTPTRPδ=0 |     | (6.37)  |
|     |                 | i   | i   |     | i     |           | i   |         |
|     |                 |     |     | 2   |       | 2         |     |         |
or equivalently, in closed-loop form,
|     |     |     | (PTA | +A TP+Q | +PTRP)=0 |     |     | (6.38) |
| --- | --- | --- | ---- | ------- | -------- | --- | --- | ------ |
|     |     |     |      | ic ic   | i        | i   |     |        |
where Pis defined by (6.36), and
|     |     |     |     | 0  |     |    |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
|     |     |     |     |    |     |    |     |     |
0
|     |     |     |     |    |     |    |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
A =
|     |     |     |     | i  | [A]ii |    |     |     |
| --- | --- | --- | --- | --- | ----- | --- | --- | --- |
|     |     |     |     |    |       |    |     |     |
|     |     |     |     |   |       | 0 |     |     |
|     | 0  |     |     |     |      |     |     |     |
|     |    |     |     |     |      |     |     |     |
|     |    |     |     |     |      |     |     |     |
− 1B T),
| B = |     |         | ii      | ij    | diag((d | +g )B | R A = A  | −B P |
| ---- | --- | ------- | ------- | ------ | ------- | ----- | -------- | ---- |
| i    |     |  (d +g | )I    | −e I  |         | i i i | i i i ic | i i  |
|      |    |  i     | i n   | ij n  |        |       |          |      |
|      |    |         |         |        |        |       |          |      |
|      |    |         |         | 0      |        |       |          |      |

6.5 Stability and Solution of Graphical Games 197
0 
 
0
 
Q = ,
i  [Q ]ii 
 ii 
 0
R 
i1
 
(cid:30)
 
 R 
R =diag((d +g )BR−1) ij diag((d +g )R−1BT)
i i i i ii i i ii i
 (cid:30) 
 
R
 ii 
 R
iN

Proof Take (6.20) and write it with respect to the global state and costate as
T
 ∂V 
1
 ∂δ  0 
 1 
 
 (cid:29)  0
 
H ≡  δ
i

(cid:29)

 [A]ii 
 
  ∂V N    0
∂δ N 
T
 ∂V 
1
  0 (cid:28) 0 0 
∂δ B u 
 1    1 1
(cid:29) 0 (cid:29) (cid:29)   
 (cid:29)    (cid:30) (cid:29)
+   ii ij   
 (cid:29)   (cid:29) (cid:29)  (d i +g i )I n   −e ij I n     B i    u i  
  ∂V N    0 (cid:28) 0 0    B Nu N
∂δ N 
0  u  T R u 
1 i1 1
      
0 (cid:29) (cid:30) (cid:29)
+1δT   δ+1    =0 (6.39)
2 

[Q
ii
]ii

 2

u
i 


 R
ii




u
i


 0 u N  R iNu N
By definition of the costate one has
T
∂V ∂V 
p≡ 1 ... ... N  = Pδ (6.40)
∂δ 1 ∂δ N 
From the control policies (6.21), (6.39) becomes (6.37). □

198 6 Graphical Games: Distributed Multiplayer Games on Graphs
6.5.2 Stability and Solution for Cooperative Nash Equilibrium
It is now shown that if solutions can be found for the coupled HJ design equations
(6.30), then they provide the solution to the graphical game problem. It is shown
how to solve these HJ equations online using RL in Sect. 6.7. It requires Assump-
tion 6.1 that the graph has a spanning tree with pinning into at least one root node.
Theorem 6.2 Stability and Solution for Cooperative Nash Equilibrium Let
Assumptions 6.1 and 6.3 hold. Let V >0∈C1,i∈N be smooth solutions to HJ
i
equations (6.30) and control policies u*, i∈N be given by (6.21) in terms of these
i
solutions V . Then:
i
a. Systems (6.9) are asymptotically stable so that all agents synchronize.
b.
{ u*,u*,...,u*}
are in global Nash equilibrium and the corresponding game val-
1 2 Ν
ues are
J*(δ(0))=V, i∈N. (6.41)
i i i
Proof
a. If V >0 satisfies (6.30) then it also satisfies (6.20). Take the time derivative to
i
obtain
∂V T ∂V T  
V(cid:31) = i δ (cid:31) = i Aδ +(d +g )Bu − ∑e B u 
i ∂δ i ∂δ  i i i i i ij j j 
i i  j∈N 
i
 
1
=− δTQδ +uTR u + ∑uTR u  (6.42)
i ii i i ii i j ij j
2 
 j∈N 
i
which is negative definite since Q >0. Therefore, V is a Lyapunov function for
ii i
δ and systems (6.9) are asymptotically stable.
i
b. According to part a,δ(t)→0 for the selected control policies. For any smooth
i
functions V (δ),i∈N, such that V(0)=0, setting V (δ(∞))=0 one can write
i i i i i
(6.12) as
∞ ∞
1
J (δ(0),u ,u )= ∫(δTQδ +uTR u + ∑uTR u )dt+V(δ(0))+∫V(cid:31)dt
i i i −i i ii i i ii i j ij j i i i
2
0 j∈N i 0
or
∞
1
J (δ(0),u ,u )= ∫(δTQδ +uTR u + ∑uTR u )dt+V(δ(0))
i i i −i i ii i i ii i j ij j i i
2
0 j∈N i
∞ T
∂V
+∫ i (Aδ +(d +g )Bu − ∑e B u )dt
i i i i i ij j j
∂δ
0 i j∈N i

| 6.5  |  Stability and Solution of Graphical Games  |     |     |     |     |     |     |     | 199 |
| ---- | ------------------------------------------- | --- | --- | --- | --- | --- | --- | --- | --- |
Now let V  satisfy (6.30) and u*,u * be the optimal controls given by (6.21). By
|     |     | i   |     | i   | −i  |     |     |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
completing the squares one has
|     | J (δ(0),u | ,u )=V(δ(0)) |     |     |     |     |     |     |     |
| --- | --------- | ------------ | --- | --- | --- | --- | --- | --- | --- |
|     | i i       | i −i         | i i |     |     |     |     |     |     |
∞
|     |     |     | 1   | ∑(u   | *)TR | *)+    | 1 −u*)TR |     | −u*) |
| --- | --- | --- | --- | ----- | ---- | ------ | -------- | --- | ---- |
|     |     |     | +∫( |       | −u   | (u −u  | (u       | (u  |      |
|     |     |     | 2   |       | j j  | ij j j | 2 i i    | ii  | i i  |
|     |     |     | 0   | j∈N i |      |        |          |     |      |
T
∂V
|     |     |     | − i | ∑e  | B (u −u | *)+ ∑u*TR | (u −u*))dt |     |     |
| --- | --- | --- | --- | --- | ------- | --------- | ---------- | --- | --- |
|     |     |     |     |     | ij j j  | j         | j ij j j   |     |     |
∂δ
|                            |     |     | i            | j∈N       |     | j∈N     |     |     |     |
| -------------------------- | --- | --- | ------------ | --------- | --- | ------- | --- | --- | --- |
|                            |     |     |              | i         |     | i       |     |     |     |
| At the equilibrium point u |     |     |              | =u* and u |     | =u * so |     |     |     |
|                            |     |     |              | i i       | j   | j       |     |     |     |
|                            |     |     | J*(δ(0),u*,u |           |     | *)=V    |     |     |     |
(δ(0))
|     |     |     |     | i i | i   | −i i i |     |     |     |
| --- | --- | --- | --- | --- | --- | ------ | --- | --- | --- |
Define
∞
1
|     |     | J (u | ,u *)=V | (δ(0))+ |     | ∫(u −u*)TR | (u −u*)dt |     |     |
| --- | --- | ---- | ------- | ------- | --- | ---------- | --------- | --- | --- |
|     |     | i i  | −i      | i       | i   | i i        | ii i i    |     |     |
2
0
And J*
=V (δ(0)). Then clearly J* and J (u,u* ) satisfy (6.24). Since this is
|                                                      | i   | i i |     |     | i   | i i −i |     |     |     |
| ---------------------------------------------------- | --- | --- | --- | --- | --- | ------ | --- | --- | --- |
| true for all i, Nash condition (6.22) is satisfied.  |     |     |     |     |     |        |     |     | □   |
The next result shows when the systems are in interactive Nash equilibrium. This
means that the graphical game is well defined in the sense that all players are in a
single Nash equilibrium with each player affecting the decisions of all other players.
This result requires a stronger type of connectivity than the existence of a spanning
tree required in Theorem 6.2.
Corollary 6.1 Let the hypotheses of Theorem 6.2 hold. Let Assumption 6.2 hold
and the graph be strongly connected. Then  { u*,u*,...,u*}  are in interactive Nash
|     |     |     |     |     |     | 1 2 | Ν   |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
equilibrium and all agents synchronize.
| Proof From Theorems 6.1 and 6.2.  |     |     |     |     |     |     |     |     | □   |
| --------------------------------- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
According to Theorem 6.2 and Corollary 6.1, solutions to the Hamilton–Jacobi–
Bellman (HJB) can be used to construct policies that result in Nash equilibrium
and synchronization if the graph has a spanning tree with pinning into at least one
root node. One of the beauties of Nash equilibrium is its symmetry or anonymity, in
that all nodes play the same role. Unfortunately, from Theorem 6.2 we can deduce
that the symmetry of Nash equilibrium is lost in graphical games. Indeed all that is
needed for Nash equilibrium in graphical games is the existence of a spanning tree,
where one node (the root) may have a privileged role. To restore the symmetry and
anonymity of the nodes we call on interactive Nash equilibrium, which requires that
the graph be strongly connected.

200 6  Graphical Games: Distributed Multiplayer Games on Graphs
6.6   PI Algorithms for Cooperative Multiplayer Games
RL techniques have been used to solve the single-player optimal control problem by
using adaptive learning techniques to determine the optimal value function. Espe-
cially effective are the neurodynamic programming [6] and ADP methods [40, 41].
ADP is a method for online learning of optimal control solutions in real time. RL
techniques have also been applied for multiplayer games with centralized dynamics
(6.23). See, for example, [8, 33, 37]. Most applications of RL for solving optimal
control problems or games online have been to finite-state systems or discrete-time
dynamical systems. In this section is given a PI algorithm for solving continuous-
time differential games on graphs. The structure of this algorithm is used in the next
section to provide online adaptive solutions for graphical games.
6.6.1   Best Response
Theorem 6.2 and Corollary 6.1 reveal that, under Assumptions 6.2 and 6.3, the sys-
tems are in interactive Nash equilibrium if, for all i∈N, node i selects his best re-
sponse policy to his neighbors’ policies and the graph is strongly connected. Define
=u*
the best response HJ equation as the Bellman equation (6.20) with control u
i i
| given by (6.21) and arbitrary policies u |     |       |         |     | ={u : | j∈N}   |        |     |
| ---------------------------------------- | --- | ----- | ------- | --- | ----- | ------ | ------ | --- |
|                                          |     |       |         | −i  | j     | i      |        |     |
|                                          |     |       | ∂V      |     | ∂V T  |        |        |     |
|                                          |     |       | i ,u*,u |     | i Ac  | 1 δTQδ |        |     |
|                                          | 0=  | H (δ, |         | )≡  |       | +      |        |     |
|                                          |     | i i   | ∂δ i    | −i  | ∂δ    | i 2    | i ii i |     |
|                                          |     |       | i       |     | i     |        |        |     |
T
|     |     | 1     | ∂V  |          | ∂V   | 1   |        |        |
| --- | --- | ----- | --- | -------- | ---- | --- | ------ | ------ |
|     | +   | (d +g | )2  | i BR−1BT |      | i + | ∑uTR u | (6.43) |
|     |     | i     | i   | i        | ii i |     | j ij j |        |
|     |     | 2     | ∂δ  |          | ∂δ   | 2   |        |        |
|     |     |       |     | i        |      | i   | j∈N    |        |
i
where the closed-loop matrix is
∂V
|     | c   |      |        | )2B | − 1B T | i   | ∑      |        |
| --- | --- | ---- | ------ | --- | ------ | --- | ------ | ------ |
|     | A   | = Aδ | −(d +g | R   |        | −   | e B u  | (6.44) |
|     | i   | i    | i      | i i | i i i  | ∂δ  | ij j j |        |
i j∈N
i
Theorem 6.3 Solution for Best Response Policy Given fixed neighbor policies
u ={u : j∈N}, assume there is an admissible policy  u. Let V >0∈C1be a
| −i j | i   |     |     |     |     |     | i i |     |
| ---- | --- | --- | --- | --- | --- | --- | --- | --- |
smooth solution to the best response HJ equation (6.43) and let control policy u* be
i
given by (6.21) in terms of this solution V. Then:
i
a. Systems (6.9) are asymptotically stable so that all agents synchronize.
b. u* is the best response to the fixed policies u  of its neighbors.
| i   |     |     |     |     |     | −i  |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
Proof
a. Let V >0 satisfy (6.43). Then the proof follows Theorem 6.2, part a.
i

6.6 PI Algorithms for Cooperative Multiplayer Games 201
b. According to part a, δ(t)→0 for the selected control policies. For any smooth
i
functions V (δ),i∈N, such that V(0)=0, setting V (δ(∞))=0 one can write
i i i i i
(6.12) as
∞
1
J (δ(0),u ,u )= ∫(δTQδ +uTR u + ∑uTR u )dt+V(δ(0))
i i i −i i ii i i ii i j ij j i i
2
0 j∈N i
∞ T
∂V
+∫ i (Aδ +(d +g )Bu − ∑e B u )dt
i i i i i ij j j
∂δ
0 i j∈N i
Now let V satisfy (6.43), u* be the optimal controls given by (6.21), and u be
i i −i
arbitrary policies. By completing the squares one has
∞
1
J (δ(0),u ,u )=V (δ(0))+∫ (u −u*)TR (u −u*)dt
i i i −i i i i i ii i i
2
0
The agents are in best response to fixed policies u when u =u* so
−i i i
J (δ(0),u*,u )=V (δ(0))
i i i −i i i
Then clearly J (δ(0),u ,u ) and J (δ(0),u*,u ) satisfy (6.24). □
i i i −i i i i −i
6.6.2 PI Solution for Graphical Games
The following algorithm for the N-player distributed games is motivated by the
structure of PI algorithms in RL [6, 30], which rely on repeated policy evaluation
(e.g., solution of Bellman equations (6.20)) and policy improvement (solution of
(6.21)). These two steps are repeated until the policy improvement step no long-
er changes the present policy. If the algorithm converges for every i, then (6.20)
and (6.21) hold simultaneously, so that it converges to the solution to HJ equations
(6.30) and hence provides the distributed Nash equilibrium according to Theorem
6.2. One must note that the value functions can be evaluated only in the case of
admissible control policies, for only then do the Bellman equations (6.20) have
positive definite solutions.
Algorithm 1 PI Solution for N-player Distributed Graphical Games
Step 0
Set k = 0. Start with admissible initial policies u0,∀i. Do for k until convergence.
i

202 6  Graphical Games: Distributed Multiplayer Games on Graphs
Step 1 (Policy evaluation)
Solve for Vk using Bellman equations (6.20)
i
k
∂V
|     |     | H (δ, | i   | ,uk,u | k)=0, | ∀i=1,…,N |     | (6.45) |
| --- | --- | ----- | --- | ----- | ----- | -------- | --- | ------ |
|     |     | i     | i   | i     | −i    |          |     |        |
∂δ
i
Step 2 (Policy improvement)
Update the N-tuple of control policies using
k
|     | uk+1 |          |     | ∂V  | i   | k),∀i=1,…,N |     |     |
| --- | ---- | -------- | --- | --- | --- | ----------- | --- | --- |
|     |      | =argminH |     | (δ, | ,u  | ,u          |     |     |
|     | i    |          |     | i i |     | i −i        |     |     |
|     |      |          | u   | ∂δ  | i   |             |     |     |
i
which explicitly is
|     |     |      |     |        | ∂V   | k           |     |        |
| --- | --- | ---- | --- | ------ | ---- | ----------- | --- | ------ |
|     |     | uk+1 |     | )R−1BT |      | i           |     |        |
|     |     | =−(d | +g  |        |      | , ∀i=1,…,N. |     | (6.46) |
|     |     | i    | i   | i ii   | i ∂δ |             |     |        |
i
Go to step 1.
On convergence—end
The following two theorems prove convergence of the PI algorithm for distributed
games for two different cases. The two cases considered are the following: i) only
agent i updates its policy and ii) all the agents update their policies simultaneously.
Theorem 6.4 Convergence of PI algorithm when only ith agent updates its pol-
icy and all players u  in its neighborhood do not change Given fixed neighbors
−i
policies u , assume there exists an admissible policy u. Assume that agent i per-
| −i  |     |     |     |     |     | i   |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
forms Algorithm 1 and the its neighbors do not update their control policies. Then
the algorithm converges to the best response u  to policies u  of the neighbors and
|                   |                                           |     |     |     |     | i   | −i  |     |
| ----------------- | ----------------------------------------- | --- | --- | --- | --- | --- | --- | --- |
| to the solution V |  to the best response HJ equation (6.43). |     |     |     |     |     |     |     |
i
Proof It is clear that
|     |       |     | ∂Vk |        |     | ∂Vk     |      |     |
| --- | ----- | --- | --- | ------ | --- | ------- | ---- | --- |
|     | Ho(δ, |     | i   |        |     | i ,uk,u |      |     |
|     |       |     | ,u  | )≡minH |     | (δ,     | )    |     |
|     |       | i i | ∂δ  | −i     | k i | i ∂δ    | i −i |     |
|     |       |     | i   |        | u i | i       |      |     |
∂Vk
|     |     |     |     | =   | H (δ, | i ,uk+1,u | )   | (6.47) |
| --- | --- | --- | --- | --- | ----- | --------- | --- | ------ |
|     |     |     |     |     | i i   | i         | −i  |        |
∂δ
i
k
∂V
Let H (δ, i ,uk,u )=0 from (6.45) then according to (6.47) it is clear that
| i i |     | i −i |     |     |     |     |     |     |
| --- | --- | ---- | --- | --- | --- | --- | --- | --- |
∂δ
i
∂Vk
|     |     |     | Ho(δ, |     | i ,u | )≤0 |     | (6.48) |
| --- | --- | --- | ----- | --- | ---- | --- | --- | ------ |
|     |     |     |       | i i | −i   |     |     |        |
∂δ
i

6.6 PI Algorithms for Cooperative Multiplayer Games 203
Using the next control policy uk+1 and the current policies u one has the orbital
i −i
derivative [18]
∂Vk
V(cid:31)k = H (δ, i ,uk+1,u )−L (δ,uk+1,u )
i i i ∂δ i −i i i i −i
i
From (6.47) and (6.48) one has
∂V k
V(cid:31)
i
k = H
i
0(δ
i
,
∂δ
i ,u
−i
)−L
i
(δ
i
,u
i
k+1,u
−i
)≤−L
i
(δ
i
,u
i
k+1,u
−i
) (6.49)
i
Because only agent i update its control it is true that
∂Vk+1
H (δ, i ,uk+1,u )=0.
i i ∂δ i −i
i
But since V(cid:31)k+1 =−L (δ,uk+1,u ), from (6.49) one has
i i i i −i
∂V k
V(cid:31)k = H0(δ, i ,u )−L (δ,uk+1,u )≤−L (δ,uk+1,u )=V(cid:31)k+1 (6.50)
i i i ∂δ −i i i i −i i i i −i i
i
so that Vk ≤Vk+1 and by integration it follows that
i i
Vk+1 ≤Vk (6.51)
i i
which shows that it is a nonincreasing function bounded below by zero. As such Vk
i
is convergent as k→∞. We can write limVk =V∞. According to the principle of
i i
k→∞
optimality [22], we have
∞
1
Vk ≥min∫ (δTQδ +uTR u + ∑uTR u )dt
i i ii i i ii i j ij j
u 2
i t j∈N i
∞
1
=∫ (δTQδ +u*TR u*+ ∑uTR u )dt
i ii i i ii i j ij j
2
t j∈N i
where u* is the optimal control. Let k→∞ then
i
∞
1
V∞ ≥∫ (δTQδ +u*TR u*+ ∑ uTR u )dt ≡V*
i i ii i i ii i j ij j i
2
t j∈Ni
Since V* ≤V∞, the algorithm converges, to V*, to the best response HJ equation
i i i
(6.43). □

204 6 Graphical Games: Distributed Multiplayer Games on Graphs
The next result concerns the case where all nodes update their policies simultane-
ously at each step of the algorithm. Then, certain weak coupling conditions must be
satisfied. Define the relative control weighting as ρ =σ(R−1R ), the maximum
ij jj ij
singular value of the ratio of control weightings R−1R .
jj ij
Theorem 6.5 Convergence of PI algorithm when all agents update their
policies Assume all nodes i update their policies at each iteration of PI using Algo-
rithm 1. Then for small edge weights e and ρ , u the algorithm converges to the
ij ij i
global Nash equilibrium and for all i, and the values converge to the optimal game
values Vk →V*.
i i
Proof It is clear that
∂V k+1 ∂V k+1
H (δ, i ,uk+1,u k+1)≡ H0(δ, i ,uk )
i i ∂δ i −i i i ∂δ −i
i i
1
+ ∑(u k+1−u k)TR (u k+1−u k)
j j ij j j
2
j∈N
i
T
+∑ j∈N ( u j k)T R ij (u j k+1−u j k)+  ∂ ∂δ V i i k+1    ∑ j∈N e ij B j (u j k −u j k+1)
i i
and so
V
(cid:31)k+1=−L(δ,uk+1,uk+1)
i i i i −i
1
=−L(δ,uk+1,uk )+ ∑(u k+1−u k)TR (u k+1−u k)
i i i −i 2 j j ij j j
j∈N
i
T
+   ∂ ∂δ V i k+1  ∑e ij B j (u j k −u j k+1)+ ∑( u j k)T R ij (u j k+1−u j k)
 i 
j∈N j∈N
i i
Therefore,
1
V(cid:31)k ≤V(cid:31)k+1− ∑ (u k+1−u k)TR (u k+1−u k)
i i j j ij j j
2
j∈Ni
T
+  ∂ ∂δ V i k+1    ∑ e ij B j (u j k+1−u j k)− ∑ ( u j k)T R ij (u j k+1−u j k)
i j∈Ni j∈Ni
A sufficient condition for Vk ≤Vk+1 is
i i
1
σ(R ) ∆u >e pk+1 ⋅ B +(d +g )ρ pk−1 ⋅ B
ij j ij i j j j ij j j
2

| 6.6   PI Algorithms for Cooperative Multiplayer Games  |     |       |      |     |     |     |     |     | 205 |
| ------------------------------------------------------ | --- | ----- | ---- | --- | --- | --- | --- | --- | --- |
|                                                        |     | k+1−u | k),  |     |     |     |     |     |     |
where ∆u =(u p is the costate, and σ(R ) is the minimum singular
|     | j   | j   | j   | i   |     |     | ij  |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
value of R . This holds if e =0,ρ =0. By continuity, it holds for small values
|     |     |     |     | ij ij |     |     |     |     |     |
| --- | --- | --- | --- | ----- | --- | --- | --- | --- | --- |
ij
of e ,ρ.
ij ij
| By integration of Vk |     |     | ≤Vk+1, it follows that |      |     |     |     |     |        |
| --------------------- | --- | --- | ----------------------- | ---- | --- | --- | --- | --- | ------ |
|                       |     |     | i                       | i    |     |     |     |     |        |
|                       |     |     |                         | Vk+1 | ≤Vk |     |     |     | (6.52) |
|                       |     |     |                         |      | i   | i   |     |     |        |
which shows that it is a nonincreasing function bounded below by zero. As such Vk
i
is convergent as k→∞. We can write limVk =V∞. According to the principle of
i i
| optimality [22], we have |     |     |     |     | k→∞ |     |     |     |     |
| ------------------------ | --- | --- | --- | --- | --- | --- | --- | --- | --- |
∞
1
|     |     | Vk  | ≥∫ (δTQδ | +u*TR  | u*+  | ∑u*TR |      | u*)dt |     |
| --- | --- | --- | -------- | ------ | ---- | ----- | ---- | ----- | --- |
|     |     |     | i        | i ii i | i ii | i     | j ij | j     |     |
2
j∈N
|     |     |     | t   |     |     |     | i   |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
where u*,u* are the optimal controls. Let k→∞ then
|     | i j |     |     |     |     |     |     |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
∞
1
|     |     | V∞  | ≥∫ (δTQδ | +u*TR  | u*+  | ∑u*TR | u*)dt  | ≡V* |     |
| --- | --- | --- | -------- | ------ | ---- | ----- | ------ | --- | --- |
|     |     | i   | i        | ii i i | ii i |       | j ij j | i   |     |
2
|     |     |     | t   |     |     | j∈N |     |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
i
Since V* ≤V∞, the algorithm converges, to V*, to the cooperative Nash equilib-
|                           | i   | i   |     |     |     | i   |     |     |     |
| ------------------------- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| rium HJ equation (6.30).  |     |     |     |     |     |     |     |     | □   |
Remark  6.1 Some  applications  in  graph  theory  require  small  edge  weights
(e ≤e  where e  is a relatively small positive number). Shortest path graph
| ij  | max |     | max |     |     |     |     |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
problems based on scaling [12] and fast matrix multiplication [42] have running
times that depend on the edge weights, and therefore yield improved algorithms for
sufficiently small edge weights.
This proof indicates that for the PI algorithm to converge, the neighbors’ controls
should not unduly influence the ith node dynamics (6.9), and the jth node should
weight its own control u  in its performance index J  relatively more than node
|     |     |     | j   |     |     |     | j   |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
i weights u  in J. These requirements are consistent with selecting the weighting
j i
matrices to obtain proper performance in the simulation examples. An alternative
condition to small edge weights for convergence in Theorem 6.5 is that the norm
||B|| should be small. This is similar to the case of weakly coupled dynamics in
j
| multiplayer games in [5].  |     |     |     |     |     |     |     |     | ▋   |
| -------------------------- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
6.6.3   PI Solution for Graphical Games
In this section, an online algorithm for solving cooperative HJ equations (6.30)
based on [34] is presented. This algorithm uses the structure in the PI Algorithm 1

206 6  Graphical Games: Distributed Multiplayer Games on Graphs
to develop an actor/critic adaptive control architecture for approximate online solu-
tion of (6.30). The implementation procedure in terms of adaptive tuning algorithms is
based on the technology in [21] for online NN adaptive control systems. Approximate
solutions of (6.45), (6.46) are obtained using VFA. The algorithm uses two approxi-
mator structures at each node, which are taken here as NNs [2, 6, 21, 32, 40, 41]. One
critic NN is used at each node for VFA, and one actor NN is used at each node to ap-
proximate the control policy (6.46). The critic NN seeks to solve Bellman equation
(6.45). We give tuning laws for the actor NN and the critic NN such that equations
(6.45) and (6.46) are solved simultaneously online for each node. Then, the solu-
tions to the coupled HJ equations (6.30) are determined. Though these coupled HJ
equations are difficult to solve and may not even have analytic solutions, we show
how to tune the NN so that approximate solutions are learned online. The next as-
sumption is made.
Assumption 6.4 For each admissible control policy the nonlinear Bellman equa-
| tions (6.45) have smooth solutions V |     |     |     | ≥0. |     |     |     |     |
| ------------------------------------ | --- | --- | --- | --- | --- | --- | --- | --- |
i
In fact, only local smooth solutions are needed. To solve the Bellman equations
(6.45), approximation is required of both the value functions V  and their gradients
i
∂V /∂δ. This requires approximation in Sobolev space [2].
i i
6.6.4   Critic NN
This approach is based on the ideas in [21] for NN adaptive control. According to
the Weierstrass higher order approximation theorem [2], there are NN weights W
i
such that the smooth value functions V  and their gradients are approximated using
i
a critic NN as
(δ)=WTφ(z
|     |     |     | V   |     | )+ε |     |     | (6.53) |
| --- | --- | --- | --- | --- | --- | --- | --- | ------ |
|     |     |     | i i | i   | i i | i   |     |        |
where z (t) is an information vector constructed at node i using locally available
i
measurements, e.g., δ(t),{δ (t): j∈N }. Vectors φ(z )∈(cid:26)h are the critic NN
|     |     | i   | j   | i   |     | i   | i   |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
activation function vectors, with h being the number of neurons in the critic NN
hidden layer. According to the Weierstrass theorem, the NN approximation error ε
i
converges to zero uniformly as h→∞. Assuming current weight estimates Wˆ, the
i
outputs of the critic NN are given by
|     |     |     | Vˆ  | =WˆTφ(z | )   |     |     | (6.54) |
| --- | --- | --- | --- | ------- | --- | --- | --- | ------ |
|     |     |     | i   | i       | i i |     |     |        |
Then, the Bellman equation (6.45) can be approximated at each step k as
|     | H   | (δ,Wˆ ,u | ,u )=δTQδ |      | +uTR | u + ∑uTR | u      |     |
| --- | --- | -------- | --------- | ---- | ---- | -------- | ------ | --- |
|     | i   | i i      | i −i      | i ii | i i  | ii i     | j ij j |     |
j∈N
i
∂φ
|     | +Wˆ | T i  |         |       |     | ∑e  |         |        |
| --- | --- | ---- | ------- | ----- | --- | --- | ------- | ------ |
|     |     |      | (Aδ +(d | +g )B | u − | B   | u )≡e   | (6.55) |
|     |     | i ∂δ | i       | i i   | i i | ij  | j j H i |        |
|     |     | i    |         |       |     | j∈N |         |        |
i

6.6 PI Algorithms for Cooperative Multiplayer Games 207
It is desired to select Wˆ to minimize the square residual error
i
1
E = eT e (6.56)
1 2 Hi Hi
Then Wˆ →W which solves (6.55) in a least-squares sense and e becomes small.
i i Hi
Theorem 6.6 below gives a tuning law for the critic weights that achieves this.
6.6.5 Action NN and Online Learning
Define the control policy in the form of an action NN which computes the control
input (6.46) in the structured form [34]
1 ∂φ(z )T
uˆ ≡uˆ =− (d +g )R−1BT i i Wˆ (6.57)
i i+N 2 i i ii i ∂δ i+N
i
where Wˆ denotes the current estimated values of the ideal actor NN weights W.
i+N i
The notation uˆ is used to keep indices straight in the proof (the first N weights
i+N
are used for the critics and the rest for the actors). Define the critic and actor NN
estimation errors as W(cid:25) =W −Wˆ and W(cid:25) =W −Wˆ .
i i i i+N i i+N
The next results show how to tune the critic NN and actor NN in real time at each
node so that equations (6.45) and (6.46) are simultaneously solved, while closed-
loop system stability is also guaranteed. Simultaneous solution of (6.45) and (6.46)
guarantees that the coupled HJ equations (6.30) are solved for each node i.
Definition 6.6 Uniformly Ultimately Bounded System (6.9) is said to be uni-
formly ultimately bounded (UUB) if there exists a compact set S ⊂n so that for
all δ(0)∈S there exists a bound B and a time T(B,δ(0)) such that δ(t) ≤B
i i i
for all t≥t +T.
0
According to Lemma 6.1, UUB guarantees approximate synchronization of all the
nodes’ states.
Select the tuning law for the ith critic NN as
W
(cid:31)ˆ
=−a
∂E
1
i i ∂Wˆ
i
σ  1
=−a i+N σ TWˆ +δTQδ+ Wˆ TDWˆ
i (1+σ Tσ )2   i+N i i ii 4 i+N i i+N
i+N i+N
1 ∂φ ∂φT 
+ Σ (d +g )2Wˆ T j B R−TR R−1BT j Wˆ  (6.58)
4 j∈Ni j j j+N ∂δ
j
j jj ij jj j ∂δ
j
j+N 

208 6 Graphical Games: Distributed Multiplayer Games on Graphs
∂φ
where σ = i (Aδ +(d +g )Buˆ − ∑ e B uˆ ). Select the tuning law
i+N i i i i i+N ij j j+N
∂δ
i j∈N
i
for the ith actor NN as
Wˆ(cid:31) =−a {(SWˆ −FσT Wˆ )− 1 DWˆ σ i+N T Wˆ
i+N i+N i i+N i i+N i 4 i i+N m i
si
1 ∂φ ∂φT σ T
− ∑(d +g )2 j B R−TR R−1BT j Wˆ i+N Wˆ } (6.59)
4 j j ∂δ j jj ij jj j ∂δ j m i+N
j∈Ni j j si
∂φ ∂φT
where D(x)≡ i BR −1BT i , m ≡(σ Tσ +1), σ =σ /(σ Tσ +1),
i ∂δ i ii i ∂δ si i+N i+N i+N i+N i+N i+N
i i
and a >0,…a >0 and F >0,S >0, i∈N are tuning parameters. The actor
i i+N i i
tuning law is based on our work on nonzero-sum Nash games with centralized dy-
namics [33] and it is modified accordingly to capture the required distributed nature
of control protocols and tuning laws of graphical games [34]. It is designed in such a
way to ensure both stability of the system and convergence to the Nash equilibrium.
Definition 6.7 Persistence of Excitation (PE) A time signal s(t) is persistently
exciting over the time interval [t, t + T] if there exist constants β >0,β >0,T >0
1 2
such that, for all t,
t+T
βΙ≤S ≡ ∫ s(τ)sΤ(τ)dτ≤βΙ. (6.60)
1 0 2
t
The PE assumption is needed in adaptive control if one desires to perform sys-
tem identification using, for instance, recursive least squares [13]. It is needed here
because one effectively desires to tune the critic parameters to identify V (δ) in
i i
(6.53).
Theorem 6.6 Online Cooperative Graphical Games Let Assumptions 6.3 and
6.4 hold. Let the error dynamics be given by (6.9), and consider the cooperative
game formulation in (6.13). Let the critic NN at each node be given by (6.54) and
the control input be given for each node by actor NN (6.57). Let the tuning law for
the ith critic NN be provided by (6.58) and the tuning law for the ith actor NN be
provided by (6.59). Assume σ =σ /(σ Tσ +1) is persistently exciting.
i+N i+N i+N i+N
Then the closed-loop system states that δ(t), the critic NN errors W , and the actor
i i
NN errors W are UUB.
i+N
Proof [34]. □
Remark 6.2 Note that in graphical games, the information available to each node
is limited by the graph topology so that each node can obtain information only from
itself and its direct neighbors. As such, the control protocols and the NN tuning laws
must be distributed. Note that, if z is appropriately selected (see Remark 6.5), then
i
φ(z ) only depends on local information and the tuning laws (6.58), (6.59) only use
i i

6.6 PI Algorithms for Cooperative Multiplayer Games 209
information from each node and its neighbors. Theorem 6.6 shows that these tuning
algorithms, when run simultaneously in real time, both guarantee stability and make
the system errors δ(t) small and the NN approximation errors bounded. Small errors
i
guarantee approximate synchronization of all the node trajectories. ▋
Remark 6.3 Persistence of excitation (PE) is needed in standard adaptive control
for system identification [13]. PE is needed here because one effectively desires to
identify the value functions in (6.53). Nonstandard tuning algorithms are required
here for the actor NNs to guarantee stability. It is important to notice that the actor
NN tuning law (6.59) of every agent needs information of the critic weights of all
his neighbors, while the critic NN tuning law (6.58) of every agent needs informa-
tion of the actor weights of all his neighbors. ▋
Remark 6.4 NN usage suggests starting with random, nonzero control NN weights
in (6.57) in order to converge to the coupled HJ equation solutions. However,
extensive simulations show that convergence is more sensitive to the persistence
of excitation in the control inputs than to the NN weight initialization. If the proper
persistence of excitation is not selected, the control weights may not converge to the
correct values. ▋
Remark 6.5 The issue of which inputs z (t) to use for the critic and actor NNs
i
needs to be addressed. According to the dynamics (6.9), the value functions (6.18),
and the control inputs (6.21), the NN inputs at node i should consist of its own error
state δ(t), the error states of its neighbors, and the costates of its neighbors. How-
i
ever, in view of (6.36) the costates are functions of the error states. In view of the
approximation capabilities of NN and the desire to obtain distributed adaptive laws
it is suitable to take as the NN inputs at node i its own error state and the error states
of its neighbors. Furthermore since we are considering Linear Quadratic Regulator
(LQR) case the values are selected as quadratic in these NN inputs as shown in the
simulation. ▋
The next result shows that the tuning laws given in Theorem 6.6 guarantee approx-
imate solution to the coupled HJ equations (6.30) and convergence to the Nash
equilibrium.
Theorem 6.7 Convergence to Cooperative Nash Equilibrium and Synchroniza-
tion Suppose the hypotheses of Theorem 6.6 hold. Then:
∂φT
a. H (δ,Wˆ,uˆ ,uˆ ), ∀i∈N are UUB, where uˆ =−1(d +g )R−1BT i Wˆ .
i i i i −i i 2 i i ii i ∂δ i
That is, Wˆ converge to the approximate cooperative coupled HJ solution i .
i
b. uˆ converge to the approximate cooperative Nash equilibrium (Definition 6.2)
i+N
for every i.
If Assumption 6.1 holds, then synchronization is reached.
Proof The proof is similar to [33] but is done only with respect to the neighbors
(local information) of each agent and not with respect to all the agents.

210 6 Graphical Games: Distributed Multiplayer Games on Graphs
Consider the weights Wˆ ,Wˆ to be UUB as proved in Theorem 6.6.
i i+N
a. The approximate coupled HJ equations are H (δ,Wˆ ,uˆ,uˆ ), ∀i∈N .
i i i i −i
∂φ
H (δ,Wˆ ,uˆ ,uˆ )≡ H (δ,Wˆ Wˆ )=δTQδ +WˆT i Aδ
i i i i −i i i i −i i ii i i i
∂δ
i
1 ∂φ ∂φT
− (d +g )2WˆT i BR−1BT i Wˆ
4 i i i ∂δ i ii i ∂δ i
i i
+ 1 ∑(d +g )2Wˆ T ∂φ j B R−1R R−1B T ∂φ j T Wˆ
4 j j j ∂δ j jj ij jj j ∂δ j
j∈N j j
i
+ 1 WˆT ∂φ i ∑e B R−1B T ∂φ j T Wˆ −ε
2 i ∂δ ij j jj j ∂δ j HJ i
i j∈N j
i
where ε ,∀i are the residual errors due to approximation.
HJ
i
After adding zero we have
∂φ 1 ∂φ ∂φT
H (δ,Wˆ Wˆ )=−W(cid:25)T i Aδ − (d +g )2W(cid:25)T i BR−1BT i W(cid:25)
i i i −i i ∂δ i 4 i i i ∂δ i ii i ∂δ i
i i i
1 ∂φ ∂φT
+ (d +g )2WT i BR−1BT i W
2 i i i ∂δ i ii i ∂δ i
i i
1 ∂φ ∂φT
+ (d +g )2WT i BR−1BT i Wˆ
2 i i i ∂δ i ii i ∂δ i
i i
− 1 ∑(d +g )2W(cid:25) T ∂φ j B R−1R R−1B T ∂φ j T W(cid:25)
4 j j j ∂δ j jj ij jj j ∂δ j
j∈Ni j j
+ 1 ∑(d +g )2W T ∂φ j B R−1R R−1B T ∂φ j T W
2 j j j ∂δ j jj ij jj j ∂δ j
j∈Ni j j
+ 1 ∑ (d +g )2W T ∂φ j B R−1R R−1B T ∂φ j T Wˆ
2 j j j ∂δ j jj ij jj j ∂δ j
j∈Ni j j
∂φ ∂φ T
+WˆT i ∑ e B R−1B T j Wˆ −ε
i ∂δ ij j jj j ∂δ j HJi
i j∈Ni j
− 1 W(cid:25)T ∂φ i ∑ e B R−1B T ∂φ j T W(cid:25)
2 i ∂δ ij j jj j ∂δ j
i j∈Ni j
− 1 WT ∂φ i ∑ e B R−1B T ∂φ j T Wˆ
2 i ∂δ ij j jj j ∂δ j
i j∈Ni j
− 1 WˆT ∂φ i ∑ e B R−1B T ∂φ j T W (6.61)
2 i ∂δ ij j jj j ∂δ j
i j∈Ni j

| 6.7   Simulation Results  |     |     |     |     |     |     |     |     | 211 |
| ------------------------- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
But
|     |     |     |     | Wˆ =−W(cid:25) |     |     |     |     |        |
| --- | --- | --- | --- | -------------- | --- | --- | --- | --- | ------ |
|     |     |     |     |                | +W, | ∀i. |     |     | (6.62) |
|     |     |     |     | i              | i i |     |     |     |        |
After  taking  norms  in  (6.62)  and  letting  W <W   one  has
|                      |     |             |      |                |      |     | i   | imax |     |
| -------------------- | --- | ----------- | ---- | -------------- | ---- | --- | --- | ---- | --- |
| Wˆ = −W(cid:25)      | +W  | ≤ W(cid:25) | + W  | ≤ W(cid:25) +W | .    |     |     |      |     |
| i                    | i i | i           | i    | i              | imax |     |     |      |     |
| Now (6.61) with supε |     | HJ          | <ε i |  becomes       |      |     |     |      |     |
i
∂φ
|     | H   | (δ,Wˆ | Wˆ ) | ≤ W(cid:25) | i Aδ |     |     |     |     |
| --- | --- | ----- | ---- | ----------- | ---- | --- | --- | --- | --- |
|     |     | i i   | i −i | i           |      | i   |     |     |     |
∂δ
i
2
|     |     | 1     |              | 2 ∂φ |       |     |     |     |     |
| --- | --- | ----- | ------------ | ---- | ----- | --- | --- | --- | --- |
|     | +   | (d +g | )2 W(cid:25) |      | i B 2 | R−1 |     |     |     |
|     |     | i     | i            | i    | i     | ii  |     |     |     |
|     |     | 4     |              | ∂δ   |       |     |     |     |     |
i
2
|     |     | 1     |      |      | ∂φ  |       |     |     |     |
| --- | --- | ----- | ---- | ---- | --- | ----- | --- | --- | --- |
|     | +   | (d +g | )2 W | 2    | i B | 2 R−1 |     |     |     |
|     |     | i     | i    | imax |     | i ii  |     |     |     |
|     |     | 2     |      |      | ∂δ  |       |     |     |     |
i
2
|     |     | 1     |      | ∂φ   |     | 2   | (            | )    |     |
| --- | --- | ----- | ---- | ---- | --- | --- | ------------ | ---- | --- |
|     | +   | (d +g | )2 W |      | i B | R−1 | W(cid:25) +W |      |     |
|     |     | i     | i    | imax | i   | ii  | i            | imax |     |
|     |     | 2     |      | ∂δ   |     |     |              |      |     |
i
|     |     | 1         | ∂φ  |     | 2      | ∂φ  |           |     |     |
| --- | --- | --------- | --- | --- | ------ | --- | --------- | --- | --- |
|     | +   | W(cid:25) | i   | ∑e  | R−1    | j   | W(cid:25) |     |     |
|     |     | i         |     | ij  | B j jj |     | j         |     |     |
|     |     | 2         | ∂δ  |     |        | ∂δ  |           |     |     |
|     |     |           | i   | j∈N |        | j   |           |     |     |
i
∂φ
|     |     | 1         | ∂φ   | ∑e      | 2    | R−1 | j ( W(cid:25) |        | )      |
| --- | --- | --------- | ---- | ------- | ---- | --- | ------------- | ------ | ------ |
|     | +   | W         |      | i       | B    |     |               | +W     |        |
|     |     | imax      |      |         | ij j | jj  | ∂δ            | j jmax |        |
|     |     | 2         | ∂δ   |         |      |     | j             |        |        |
|     |     |           |      | i j∈N i |      |     |               |        |        |
|     |     | 1(        |      | ) ∂φ    |      | 2   | ∂φ            |        |        |
|     | +   | W(cid:25) | +W   | i       | ∑e   | B   | R−1           | j W +ε | (6.63) |
|     |     | i         | imax |         | ij   | j   | jj            | jmax   | 2      |
|     |     | 2         |      | ∂δ      |      |     | ∂δ            |        |        |
|     |     |           |      | i       | j∈N  |     |               | j      |        |
i
All the signals on the right-hand side of (6.63) are UUB and convergence to the ap-
proximate coupled HJ solution is obtained for every agent.
b. According to Theorem 6.6,  Wˆ −W ,∀i are UUB. Then it is obvious that
|     |     |     |     | i+N | i   |     |     |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
uˆ ,∀i give the approximate cooperative Nash equilibrium (Definition 6.2).
i+N
If Assumption 6.1 holds, then synchronization is reached according to Theorem 6.2.
 □
6.7   Simulation Results
This section shows the effectiveness of the online approach described in Theorem 6.6
for two different cases. Consider the five-node strongly connected digraph structure
shown in Fig. 6.1, with a leader node connected to node 3. The edge weights and
the pinning gains are taken equal to 1 so that d =2,d =1,d =2,d =2,d =2.
|     |     |     |     |     |     | 1   | 2   | 3 4 | 5   |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |

212 6 Graphical Games: Distributed Multiplayer Games on Graphs
Select the weight matrices in (6.12) as
1 0
Q 11 =Q 22 =Q 33 =Q 44 =Q 55 = 0 1   ,
R =4,R =1,R =1,R =1,R =1,R =9,R =2,R =9,
11 13 14 31 32 33 41 44
R =1,R =2,R =1,R =9.
45 52 54 55
We selected large values for R ,i=1,…,5 so that every agent’s cost is influenced
ii
most by his own control. In addition, we followed the result from Theorem 6.5 that
ρ =σ(R-1R ) must be small.
ij jj ij
In the examples below, every node is a second-order system. Then, for every
T
agent, δ =δ δ  . According to the graph structure, the information vector at
i  i1 i2
each node is
T T T
z =δT δT δT , z =δT δT , z =δT δT δT ,
1  1 3 4 2  1 2 3  1 2 3 
T T
z =δT δT δT , z =δT δT δT
4  1 4 5  5  2 4 5 
Since the value is quadratic, the critic NNs basis sets were selected as the quadratic
vector in the agent’s components and its neighbors’ components. Thus, the NN ac-
tivation functions are
φ(δ,0,δ,δ,0)=δ2 δδ δ2 0 0 0 δ2 δ δ δ2
1 1 3 4  11 11 12 12 31 31 32 32
T
δ2 δ δ δ2 0 0 0
41 41 42 42 
φ(δ,δ,0,0,0)=δ2 δδ δ2 δ2 δ δ
2 1 2  11 11 12 12 21 21 22
T
δ2 0 0 0 0 0 0 0 0 0
22 
φ(δ,δ ,δ,0,0)=δ2 δ δ δ2 δ2 δ δ δ2 δ2 δ δ
3 1 2 3  11 11 12 12 21 21 22 22 31 31 32
T
δ2 0 0 0 0 0 0
32 
φ(δ,0,0,δ,δ)=δ2 δ δ δ2 0 0 0 0 0
4 1 4 5  11 11 12 12
T
0 δ2 δ δ δ2 δ2 δ δ δ2 
41 41 42 42 51 51 52 52

6.7 Simulation Results 213
φ(0,δ ,0,δ,δ)=0 0 0 δ2 δ δ δ2 0 0
5 2 4 5  21 21 22 22
T
0 δ2 δ δ δ2 δ2 δ δ δ2 
41 41 42 42 51 51 52 52
6.7.1 Position and Velocity Regulated to Zero
For the graph structure shown, consider the node dynamics
-2 1 2 -2 1 2
x(cid:28) 1 = -4 -1   x 1 + 1   u 1 , x(cid:28) 2 = -4 -1   x 2 + 3   u 2
-2 1 2 -2 1 1
x(cid:28) 3 = -4 -1   x 3 + 2   u 3 , x(cid:28) 4 = -4 -1   x 4 + 1   u 4
-2 1 3
x(cid:28) 5 = -4 -1   x 5 + 2   u 5
-2 1
and the command generator x(cid:28) = x .
0 -4 -1 0
The graphical game is implemented as in Theorem 6.6. PE was ensured by add-
ing a small exponentially decreasing probing noise to the control inputs. Figures 6.2
and 6.3 show the evolution of the states of every agent.
6.7.2 All the Nodes Synchronize to the Curve Behavior
of the Leader Node
For the graph structure shown above, consider the following node dynamics
0 1 2 0 1 2
x(cid:28) 1 = -1 0   x 1 + 1   u 1 , x(cid:28) 2 = -1 0   x 2 + 3   u 2
0 1 2 0 1 1
x(cid:28) 3 = -1 0   x 3 + 2   u 3 , x(cid:28) 4 = -1 0   x 4 + 1   u 4
0 1 3
x(cid:28) 5 = -1 0   x 5 + 2   u 5
0 1
with target generatorx(cid:28) = x .
0 -1 0 0
The command generator is marginally stable with poles at s=±j, so it generates
a sinusoidal reference trajectory.
The graphical game is implemented as in Theorem 6.6. PE was ensured by add-
ing a small exponential decreasing probing noise to the control inputs. Fig. 6.4
shows the synchronization of all the agents to the leader’s behavior as given by the
circular Lissajous plot in the phase plane.

214 6 Graphical Games: Distributed Multiplayer Games on Graphs
Fig. 6.2 Evolution of the states for agents 1, 2
Fig. 6.3 Evolution of the system for agents 3, 4, 5

References 215
F ig. 6.4 Synchronization of
all five agents to the leader.
6.8 Conclusion
This chapter brings together cooperative control, RL, and game theory to define
and solve multiplayer differential games on communication graph topologies. It
formulates graphical games for dynamic systems and provides PI and online learn-
ing algorithms for computing the Nash equilibrium or best response online in real
time using data measured along the system trajectories. Simulation results show the
effectiveness of the proposed algorithms.
References
1. Abou-Kandil H, Freiling G, Ionescu V, Jank G (2003) Matrix Riccati Equations in Control and
Systems Theory. Birkhäuser
2. Abu-Khalaf M, Lewis FL (2005) Nearly optimal control laws for nonlinear systems with satu-
rating actuators using a neural network HJB approach. Automatica 41(5):779–791
3. Al-Tamimi A, Abu-Khalaf M, Lewis FL (2007) Adaptive critic designs for discrete-time
zero-sum games with application to H-Infinity control. IEEE Trans Syst, Man, Cybern B
37(1):240–247
4. Al-Tamimi A, Lewis FL, Abu-Khalaf M (2008) Discrete-time nonlinear HJB solution using
approximate dynamic programming: convergence proof. IEEE Trans Syst, Man, Cybern B
38(4):943–949
5. Başar T, Olsder GJ (1999) Dynamic Noncooperative Game Theory, 2nd edn. SIAM, Philadel-
phia
6. Bertsekas DP, Tsitsiklis JN (1996) Neuro-Dynamic Programming. Athena Scientific, Belmont
7. Brewer JW (1978) Kronecker products and matrix calculus in system theory. IEEE Trans Cir-
cuits Syst 25:772–781
8. Busoniu L, Babuska R, De Schutter B (2008) A comprehensive survey of multi-agent rein-
forcement learning. IEEE Trans Syst, Man, Cybern C 38(2):156–172

216 6 Graphical Games: Distributed Multiplayer Games on Graphs
9. Dierks T, Jagannathan S (2010) Optimal control of affine nonlinear continuous-time systems
using an online Hamilton–Jacobi–Isaacs formulation. In: Proc. IEEE Conf. Decision Control,
Atlanta, GA, pp. 3048–3053
10. Freiling G, Jank G, Abou-Kandil H (2002) On global existence of solutions to coupled matrix
Riccati equations in closed loop Nash games. IEEE Trans Automat Contr 41(2):264–269
11. Gajic Z, Li T-Y (1988) Simulation results for two new algorithms for solving coupled al-
gebraic Riccati equations. Paper presented at 3rd international symposium on differential
games, Sophia Antipolis, Nice, France
12. Goldberg AV (1995) Scaling algorithms for the shortest paths problem. SIAM J Comput
24:494–504
13. Ioannou P, Fidan B (2006) Adaptive Control Tutorial. SIAM, Philadelphia
14. Johnson M, Hiramatsu T, Fitz-Coy N, Dixon WE (2010) Asymptotic stackelberg optimal
control design for an uncertain euler lagrange system. In: Proc. IEEE Conf. Decision Control,
Atlanta, GA, pp. 6686–6691
15. Kakade S, Kearns M, Langford J, Ortiz L (2003) Correlated equilibria in graphical games.
In: the 4th ACM conf. Electron. Commerce, San Diego, CA, pp. 42–47
16. Kearns M, Littman M, Singh S (2001) Graphical models for game theory. In: Proc. Annual
conf. Uncertainty in Artificial Intelligence, Seattle, WA, pp. 253–260
17. Khoo S, Xie L, Man Z (2009) Robust finite-time consensus tracking algorithm for multirobot
systems. IEEE Trans Mechatron 14:219–228
18. Leake RJ, Liu R-W (1967) Construction of suboptimal control sequences. SIAM J Contr
5(1):54–63
19. Lewis FL (1992) Applied Optimal Control and Estimation: Digital Design and Implementa-
tion. Prentice-Hall, Upper Saddle River
20. Lewis FL, Vrabie D (2009) Reinforcement learning and adaptive dynamic programming for
feedback control. IEEE Circuits & Systems Magazine (invited feature article), pp. 32–50,
Third Quarter 2009
21. Lewis FL, Jagannathan S, Yesildirek A (1999) Neural Network Control of Robot Manipula-
tors and Nonlinear Systems. Taylor and Francis, London
22. Lewis FL, Vrabie D, Syrmos VL (2012) Optimal Control, 3rd edn. Wiley, Hoboken
23. Lewis FL, Vrabie D, Vamvoudakis KG (2012) Reinforcement learning and feedback control.
IEEE Control Systems Magazine, pp. 76–105
24. Li X, Wang X, Chen G (2004) Pinning a complex dynamical network to its equilibrium. IEEE
Trans Circuits Syst I, Reg Papers 51(10):2074–2087
25. Littman ML (2001) Value-function reinforcement learning in Markov games. J Cogn Syst
Res 2(1):55–66
26. Marden JR, Young HP, Pao LY (2012) Achieving pareto optimality through distributed learn-
ing. In: Proc. IEEE Conf. Decision Control, Maui, HI, pp. 7419–7424
27. Olfati-Saber R, Murray R (2004) Consensus problems in networks of agents with switching
topology and time-delays. IEEE Trans Automat Contr 49(9):1520–1533
28. Shinohara R (2010) Coalition proof equilibria in a voluntary participation game. Int J Game
Theory 39(4):603–615
29. Shoham Y, Leyton-Brown K (2009). Multiagent Systems: Algorithmic, Game-Theoretic, and
Logical Foundations. Cambridge University Press, Cambridge
30. Sutton RS, Barto AG (1998) Reinforcement Learning—An Introduction. MIT Press, Cam-
bridge
31. Tijs S (2003) Introduction to Game Theory. Hindustan Book Agency, New Delhi.
32. Vamvoudakis KG, Lewis FL (2010). Online actor-critic algorithm to solve the continuous-
time infinite horizon optimal control problem. Automatica 46(5):878–888
33. Vamvoudakis KG, Lewis FL (2011). Multi-player non-zero sum games: online adaptive
learning solution of coupled Hamilton–Jacobi equations. Automatica 47(8):1556–1569
34. Vamvoudakis KG, Lewis FL, Hudas GR (2012) Multi-agent differential graphical games: on-
line adaptive learning solution for synchronization with optimality. Automatica 48(8):1598–
1611

References 217
35. Vrabie D, Lewis FL (2009) Neural network approach to continuous-time direct adaptive op-
timal control for partially-unknown nonlinear systems. Neural Networks 2(3):237–246
36. Vrabie D, Pastravanu O, Lewis FL, Abu-Khalaf M (2009). Adaptive optimal control for con-
tinuous-time linear systems based on policy iteration. Automatica 45(2):477–484
37. Vrancx P, Verbeeck K, Nowe A (2008). Decentralized learning in Markov games. IEEE Tran
Syst Man Cyber 38(4):976–981
38. Wang F, Zhang H, Liu D (2009) Adaptive dynamic programming: an introduction. IEEE
Comput Intell Mag 4(2):39–47
39. Wang X, Chen G (2002). Pinning control of scale-free dynamical networks. Physica A
310(3–4):521–531
40. Werbos PJ (1974) Beyond Regression: New Tools for Prediction and Analysis in the Behav-
ior Sciences. Ph.D. Thesis, Harvard University
41. Werbos PJ (1992) Approximate dynamic programming for real-time control and neural mod-
eling. In: White DA, Sofge DA (eds) Handbook of Intelligent Control. Van Nostrand Rein-
hold, New York
42. Zwick U (2002) All pairs shortest paths using bridging sets and rectangular matrix multipli-
cation. J ACM 49(3):289–317

Part II
Distributed Adaptive Control for
Multi-Agent Cooperative Systems
The optimal cooperative controllers studied in Part I of the book require complete
information of the system dynamics and rely on off-line solutions of matrix design
equations. Adaptive control [1], [7], [10] is a powerful method for the design of
dynamic controllers that are tuned online in real time to learn stabilizing feedback
controllers for systems with unknown dynamics. In cooperative adaptive control,
moreover, the dynamics of the agents can be heterogeneous, that is, different for
each agent. The agent dynamics can also have unknown disturbances.
In Part II of the book, we show how to design cooperative adaptive controllers
for multi-agent systems on graphs. The challenge is to design adaptive parameter
tuning laws that are distributed in the sense that they only require information from
the neighbors in the graph topology.
In Part I of the book, we studied local and global optimal control for cooperative
multi-agent systems on communication using graphs. In these systems, any control
protocol must be distributed in the sense that the control for each agent is allowed to
depend only on information about that agent and its neighbors in the graph. In Chap.
5 we saw that this means that globally optimal controls of distributed form may not
exist on a given graph. To obtain globally optimal performance using distributed
protocols, the global performance index must be selected to depend on the graph
topology in a certain way, specifically, through the graph Laplacian matrix.
Likewise, we shall now see in Part II of the book that adaptive control design
for cooperative multi-agent systems requires the use of special Lyapunov functions
that depend on the graph topology in a certain way. In adaptive controllers that are
admissible for a prescribed communication graph topology, only distributed control
protocols and distributed adaptive tuning laws are permitted. It is not straightfor-
ward to develop adaptive tuning laws for cooprative agents on graphs that only
require information from each agent and its neighbors. The key to this is select-
ing special Lyapunov functions for adaptive control design that depend in specific
ways on the graph topology. Such Lyapunov functions can be constructed using the
concept of graph Laplacian potential, which depends on the communication graph
topology. The Laplacian potential captures the notion of a virtual potential energy
stored in the graph.

Chapter 7
Graph Laplacian Potential and Lyapunov
Functions for Multi-Agent Systems
In Part I of the book we studied local and global optimal control for cooperative
multi-agent systems on communication on graphs. In these systems, any control
protocol must be distributed in the sense that it must respect the communication
topology limitations. That is, the control protocol for each agent is allowed to de-
pend only on information about that agent and its neighbors in the graph. In Chap. 5
we saw this means that globally optimal controls of distributed form may not ex-
ist on a given graph. It was shown that for the standard linear quadratic perfor-
mance index with state and control weighting, globally optimal controls of linear
distributed form only exist on a class of directed graphs whose Laplacian matrix is
simple, that is, has a diagonal Jordan form. If state-control cross-weighting is al-
lowed, then globally optimal controls of linear distributed form exist on any given
digraph. However, in either case, global optimal performance can be attained for all
agents using distributed protocols only if the global performance index is selected
to depend on the graph topology, specifically, through its Laplacian matrix.
Similarly, we shall see in Part II of the book that adaptive control design for co-
operative multi-agent systems requires the use of special Lyapunov functions that
depend on the graph topology in a certain way. In the design of admissible adap-
tive controllers, only distributed control protocols and distributed adaptive tuning
laws are permitted. It is not straightforward to develop adaptive tuning laws for
cooperative agents on graphs that only require information from that agent and
its neighbors. The key to this is selecting special Lyapunov functions for adaptive
control design that depend in specific ways on the graph topology. This is related
to the selection of performance indices that depend on graph topology for globally
optimal performance in Chap. 5.
In this chapter we show that for networked multi-agent systems, there is an en-
ergy-like function, called the graph Laplacian potential, that depends on the com-
munication graph topology. The Laplacian potential captures the notion of a virtual
potential energy stored in the graph. We shall study the Laplacian potential for both
undirected graphs and directed graphs. The Laplacian potential is further used here
to construct Lyapunov functions that are suitable for the analysis of cooperative
control systems on graphs. These Lyapunov functions depend on the graph topol-
ogy, and based on them a Lyapunov analysis technique is introduced for coopera-
F. L. Lewis et al., Cooperative Control of Multi-Agent Systems, 221
Communications and Control Engineering, DOI 10.1007/978-1-4471-5574-4_7,
© Springer-Verlag London 2014

222 7 Graph Laplacian Potential and Lyapunov Functions for Multi-Agent Systems
F ig. 7.1 Networked spring- (cid:70)
mass system
k
k 3
2
k
1
(cid:68) (cid:69)
tive multi-agent systems on graphs. Control protocols coming from such Lyapunov
functions are distributed in form, depending only on information about the agent
and its neighbors. Such Lyapunov functions that depend on the graph topology are
used for the design of distributed adaptive controllers for multi-agent systems on
graphs in Chaps. 8, 9, and 10.
The results in this chapter were first published in [17].
7.1 Graph Laplacian Potential
Before introducing the graph Laplacian potential, let us first recall the concept of
potential energy for some familiar physical systems. Potential energy often means
the energy stored in a spring or in a potential field, such as the gravity field or the
electric field, when work is done to stretch a spring or against the potential field.
Take the spring for example. If a spring, with the spring constant k, is stretched by a
length of x, then the potential energy stored in the spring is 1 kx2. Consider further
2
a networked spring-mass system, say three point masses linked by three springs, as
shown in Fig. 7.1. Suppose the ideal free lengths of these springs are all zero. Then,
the potential energy P stored in these springs is
E
1 (cid:31)(cid:31)(cid:30) 1 (cid:31)(cid:31)(cid:30) 1 (cid:31)(cid:31)(cid:30)
P = k |ab|2 + k |ac|2 + k |bc|2, (7.1)
E 2 1 2 2 2 3
(cid:31)(cid:31)(cid:30) (cid:31)(cid:31)(cid:30) (cid:31)(cid:31)(cid:30)
where k , k , and k are the spring constants, and |ab|, |ac|, and |bc| are the
1 2 3
lengths between each two masses.
At this point, one may naturally raise a question that, since multi-agent sys-
tems are networked systems, with their connections described by a graph, is there
a counterpart of “potential energy” for the multi-agent systems? The answer is yes.
The “potential energy” for a multi-agent system can be treated as the virtual energy
stored in a graph, and thus is called the graph Laplacian potential. In this case, the
nodes are connected not by springs, but communication links with edge weights.
The graph Laplacian potential was used in [11] for unweighted undirected graphs
as a measure of the total disagreement among all agents. Later, it was extended to

| 7.2  Laplacian Potential for Undirected Graphs  |     |     |     | 223 |
| ----------------------------------------------- | --- | --- | --- | --- |
weighted undirected graphs and balanced graphs in [12] and further to generalized
strongly connected digraphs in [17]. As a kind of energy, albeit virtual, zero Lapla-
cian potential implies a steady-state condition of the graph, i.e., which under certain
conditions is equivalent to consensus of all agents. In this section, we shall study
graph Laplacian potentials for different graphs and their properties.
Consider an interconnected multi-agent system with N agents. Let the com-
munication topology be described by a graph , with associated adjacency ma-
trix  A=[a ]∈(cid:25)N×N, diagonal matrix of in-degrees D = diag{d}, and Laplacian
ij
i
matrix L= D−A=[l ]∈(cid:25)N×N, where l =d =∑N a  and l =−a  for  j≠i.
|     | ij  | ii i | ij ij | ij  |
| --- | --- | ---- | ----- | --- |
j=1
If there is an edge from agent j to agent i, then a >0; otherwise a =0. In ad-
|     |     | ij  |     | ij  |
| --- | --- | --- | --- | --- |
dition, we assume a =0. Denote the neighbor set of agent i as N ={j|a >0}.
|     | ii  |     |     | i ij |
| --- | --- | --- | --- | ---- |
Let the nodes have dynamical systems, with x ∈n being the state of agent i. Let
i
X =col(x,…,x )∈nN be the global state of the multi-agent system obtained by
| 1   | N   |     |     |     |
| --- | --- | --- | --- | --- |
concatenating  x,…,x  column-wise. In the sequel, we shall only consider the
1 N
scalar case x ∈ to simplify the expression, unless otherwise specified. Bear in
i
mind that all results apply also in the vector case by using the Kronecker product.
7.2   Laplacian Potential for Undirected Graphs
For unweighted undirected graphs, the graph Laplacian potential is defined as [11]
N
∑ )2.
|     | P = | (x −x |     | (7.2) |
| --- | --- | ----- | --- | ----- |
L i j
i=1,j∈Ni
For weighted undirected graphs, the graph Laplacian potential is defined as [12]
N
|     | P = | ∑a (x −x )2, |     | (7.3) |
| --- | --- | ------------ | --- | ----- |
L ij i j
i,j=1
where a =a . Note the graph Laplacian potential can also be defined as (7.3),
| ij ji |     |     |     |     |
| ----- | --- | --- | --- | --- |
when a  and a  are not necessarily the same. It is clear that (7.2) is a special case
| ij ji |     |     |     |     |
| ----- | --- | --- | --- | --- |
of (7.3) with unit edge weights. Compare (7.3) and (7.1) to get an “energy-like”
concept of the Laplacian potential.
For both unweighted and weighted undirected graphs, the following property
holds. It relates the Laplacian potential with the graph Laplacian matrix.
Lemma 7.1 The Laplacian potential for undirected graph satisfies the following
identity [11, 12]:
N
|     | ∑a  | )2 =2XTLX. |     |       |
| --- | --- | ---------- | --- | ----- |
|     | P = | (x −x      |     | (7.4) |
|     | L   | ij i j     |     |       |
i,j=1

224 7 Graph Laplacian Potential and Lyapunov Functions for Multi-Agent Systems
Proof Expanding XTLX leads to
N N N
XTLX = ∑ l xx =∑l x2+ ∑ l xx
ij i j ii i ij i j
i,j=1 i=1 i=1;j≠i
N  N  N
=∑ x
i
2∑a iij− ∑ a
ij
x
i
x
j
i=1 j=1  i,j=1
N
= ∑ a x (x −x ).
ij i i j
i,j=1
Since a =a , XTLX can also be written as
ij ji
N
XTLX = ∑ a x (x −x )
ji j j i
i,j=1
N
= ∑ a x (x −x ).
ij j j i
i,j=1
It then follows that
N N
2XTLX = ∑ a x (x −x )+ ∑ a x (x −x )
ij i i j ij j j i
i,j=1 i,j=1
N
= ∑ a (x −x )2 = P .
ij ii j L
i,j=1
□
The Laplacian potential is closely related to the consensus of the multi-agent sys-
tem, as will be shown in Lemma 7.4. Some technical lemmas are needed before we
proceed.
Lemma 7.2 If an undirected graph is connected, then rank(L)= N−1 ([4] Lemma
13.1.1).
Lemma 7.3 Let A= AT ∈n×n. Then, the null space of A is null(A)=
null(A)={x∈n |xTAx=0} if and only if A is positive semidefinite or negative semidefinite,
i.e., A≥0 or A≤0 ([2] Fact 8.15.2).
Lemma 7.4 For a connected undirected graph, P =0 if and only if consensus of
L
the multi-agent system is achieved, i.e., x = x , ∀i, j=1, …, N.
i j
N
Proof If P = ∑ a (x −x )2 =0, then x = x for all a >0. For connected
L ij i j i j ij
i,j=1
graphs, this implies the consensus, i.e., x = x for all i, j=1, …, N. It is obvi-
i j
ous that consensus implies P =0. Using the properties of the Laplacian matrix, an
L
alternative way to prove the necessity is shown as follows. For undirected graphs,
the Laplacian matrix L is symmetric and positive semidefinite. This can be trivially
shown by using the Geršgorin Circle Criterion ([5] Lemma 3.1). By Lemma 7.3,

| 7.2  Laplacian Potential for Undirected Graphs  |     |     |     | 225 |
| ----------------------------------------------- | --- | --- | --- | --- |
=[1,…,1]T ∈(cid:25)N.
| the null space of L is null(L)={X |     | ∈N |XTLX | =0}. Let 1 |     |
| --------------------------------- | --- | --------- | ---------- | --- |
N
The Laplacian matrix has the property that L1 =0. If the undirected graph is con-
N
nected, then rank(L)= N−1. Then, the dimension of the null space of L is 1. There-
fore, the null space of L is null(L)={X |X =α1 ,∀α∈(cid:25)}. This completes the
N
| proof.  |     |     |     | □   |
| ------- | --- | --- | --- | --- |
7.2.1   Laplacian Potential for Directed Graphs
For directed graphs, the Laplacian potential can still be defined as (7.3), but the
identity (7.4) does not hold due to the nonsymmetric property of the Laplacian
matrix L. In this subsection, we shall show how the Laplacian potential relates to
the Laplacian matrix and propose a generalized Laplacian potential for strongly
connected graphs.
Let us begin by defining a different Laplacian matrix for graph , called the
graph column Laplacian matrix Lo.
Definition  7.1 (Column  Laplacian  matrix)  Let  the  out-degree  of  node  i  be
=∑N
do a  and the out-degree matrix be Do =diag{do}∈N×N. Then, the col-
| i j=1 ji                                  |     |      | i    |     |
| ----------------------------------------- | --- | ---- | ---- | --- |
| umn Laplacian matrix of a digraph  is Lo |     | = Do | −AT. |     |
Note that the column Laplacian matrix of graph  is just the Laplacian matrix of its
reverse graph ′, that is, the graph with all edges reversed. If graph  is balanced,
| i.e., ∑N =∑N |             |       |     |     |
| ------------ | ----------- | ----- | --- | --- |
| a            | a , then Lo | = LT. |     |     |
ij ji
| j=1 | j=1 |     |     |     |
| --- | --- | --- | --- | --- |
Lemma 7.5 For general digraphs, we have the identity
N
|     | P = ∑ a | (x −x)2 = XT(L+Lo)X. |     | (7.5) |
| --- | ------- | -------------------- | --- | ----- |
|     | L       | ij j i               |     |       |

i,j=1
For balanced digraphs, we have the identity
N
|     | P = ∑ a | (x −x)2 = XT(L+LT)X. |     | (7.6) |
| --- | ------- | -------------------- | --- | ----- |
|     | L       | ij j i               |     |       |

i,j=1
Proof For general digraphs, straightforward computation gives
N
|     | XTLX | = ∑ a x (x −x | )   |     |
| --- | ---- | ------------- | --- | --- |
|     |      | ij i i        | j   |     |
i,j=1
|     |       | N N     | N       |     |
| --- | ----- | ------- | ------- | --- |
|     | XTLoX | =∑∑a x2 | ∑       |     |
|     |       |         | − a xx  |     |
|     |       | ji i    | ij ii j |     |
|     |       | i=1 j=1 | i,j=1   |     |
N N
|     |     | = ∑ x2 − ∑ |             |     |
| --- | --- | ---------- | ----------- | --- |
|     |     | a ij j     | a ij xx i j |     |
i,j=1 i,j=1
N
|     |     | = ∑ a x (x | −x ). |     |
| --- | --- | ---------- | ----- | --- |
|     |     | ij j j     | i     |     |
i,j=1

226 7  Graph Laplacian Potential and Lyapunov Functions for Multi-Agent Systems
Thus,
N
|     |     | XT(L+Lo)X | = ∑ a (x | −x )2. |     |
| --- | --- | --------- | -------- | ------ | --- |
|     |     |           | ij       | i j    |     |
i,j=1
For balanced digraphs, we haveLo = LT; therefore, (7.6) holds.  □
Lemma 7.5 implies that L+Lo ≥0 for general digraphs and L+LT ≥0 for balanced
digraphs. The case L+LT
≥0 was discussed in [12] under the term “mirror graph.”
Lemma 7.6 For weakly connected digraphs, P =0 if and only if consensus of the
L
|                                          |     |     | = ,∀i, | j=1, …, |     |
| ---------------------------------------- | --- | --- | ------ | ------- | --- |
| multi-agent systems is achieved, i.e., x |     |     | x      | N.      |     |
|                                          |     |     | i j    |         |     |
Proof The sufficiency is obvious. Now we show the necessity. We know that
N
P = ∑ a (x −x)2 =0 implies that x = x  for all a >0. Then, setting a =a
| L ij | j i |     | i j | ij  | ji ij |
| ---- | --- | --- | --- | --- | ----- |
i,j=1
for all a >0 will not change the consensus result. This amounts to replacing all
ij
the directed edges with undirected edges. By definition of the weakly connected
digraph, neglecting the direction of all edges yields a connected undirected graph.
| Thus, consensus follows from Lemma 7.4.  |     |     |     |     | □   |
| ---------------------------------------- | --- | --- | --- | --- | --- |
In Sect. 7.2, we will see that the Laplacian potential identities (7.4) and (7.6) can be
used in the Lyapunov analysis for consensus, where the time derivative of the pro-
posed Lyapunov function is just the negative of the Laplacian potential. However,
the identity (7.5) does not have such a property. Motivated by this point, a general-
ized graph Laplacian potential is defined for strongly connected graphs as follows.
Definition 7.2 (Generalized Laplacian potential) Suppose a digraph  is strongly
connected. Let p=[p , p , …, p ]T  be the left eigenvector of its Laplacian matrix
|     | 1   | 2 N |     |     |     |
| --- | --- | --- | --- | --- | --- |
L associated with eigenvalue λ =0. The generalized graph Laplacian potential is
1
defined as
N
|     |     | = ∑ | −x)2.  |     |       |
| --- | --- | --- | ------ | --- | ----- |
|     |     | P   | pa (x  |     | (7.7) |
|     |     | L   | i ij j | i   |       |
i,j=1
The next result is of major importance in Lyapunov analysis and design for coopera-
tive multi-agent systems.
Lemma 7.7 Suppose the digraph is strongly connected. Let P=diag{p}∈N×N
i
and
Q= PL+LTP,
|     |     |     |     |     | (7.8) |
| --- | --- | --- | --- | --- | ----- |
where  p  is defined as in Definition 7.2. Then the following identity holds
i
N
|     |     | P = ∑ pa | (x −x)2 = | XTQX. | (7.9) |
| --- | --- | -------- | --------- | ----- | ----- |
|     |     | L i ij   | j i       |       |       |

i,j=1

7.2  Laplacian Potential for Undirected Graphs  227
Moreover, P>0 and Q≥0.
Proof It is straightforward that
|        |                |     | N       | N       |       | N                   |          |
| ------ | -------------- | --- | ------- | ------- | ----- | ------------------- | -------- |
|        | XTPLX          | =∑  | ∑       |         |       | ∑                   |          |
|        |                |     | p i x i | a ij (x | i −x  | j )= pa i ij x i (x | i −x j ) |
|        |                |     | i=1     | j=1     |       | i,j=1               |          |
|        |                |     | ∑N      | =∑N     |       |                     |          |
|        | pTL=0 implies  |     | p       | a       | p     | a , we have         |          |
| Since  |                |     | i       | ij      | j     | ji                  |          |
|        |                |     | j=1     |         | j=1   |                     |          |
|        |                |     | N       | N       |       |                     |          |
|        |                |     | ∑ px∑a  |         | (x −x | )                   |          |
|        |                |     |         | i i     | ij i  | j                   |          |
|        |                |     | i=1     | j=1     |       |                     |          |
|        |                |     | N       | N       |       | N                   |          |
|        |                |     | =∑      | x2p ∑a  | −∑    | pa xxx              |          |
|        |                |     |         | i i     | ij    | i ij i j            |          |
|        |                |     | i=1     | j=1     | i,j=1 |                     |          |
|        |                |     | N       | N       |       | N                   |          |
|        |                |     | =∑      | x2∑     | −∑    |                     |          |
|        |                |     |         |         | p a   | pa xx               |          |
|        |                |     |         | i       | j ji  | i ij i j            |          |
|        |                |     | i=1     | j=1     |       | i,j=1               |          |
|        |                |     | N       | N       |       | N                   |          |
|        |                |     | =∑      | x2∑     | −−∑   |                     |          |
|        |                |     |         |         | pa    | pa xx               |          |
|        |                |     |         | j       | i ij  | i ij i j            |          |
|        |                |     | j=1     | i=1     |       | i,j=1               |          |
|        |                |     | N       |         | N     |                     |          |
|        |                |     | = ∑     | pa x2   | −∑    | pa xx               |          |
|        |                |     |         | i ij    | j     | i ij i j            |          |
|        |                |     | i,j=1   |         | i,j=1 |                     |          |
N
|     |     |     | = ∑∑ | pa x | (x −x). |     |     |
| --- | --- | --- | ---- | ---- | ------- | --- | --- |
|     |     |     |      | i ij | j j     | i   |     |
i,j=1
Then

|     | XTQX |     | xT(PL+LTP)x |     |     |     |     |
| --- | ---- | --- | ----------- | --- | --- | --- | --- |
=
=2xTPLx
|     |     |     | N        | N   |       |             |     |
| --- | --- | --- | -------- | --- | ----- | ----------- | --- |
|     |     | =2∑ | px∑a     | (x  | −x    | )           |     |
|     |     |     | i i      | ij  | i j   |             |     |
|     |     |     | i=1      | j=1 |       |             |     |
|     |     |     | N        |     |       | N           |     |
|     |     | =   | ∑ pa x(x | −x  | )+ ∑  | pa x (x −x) |     |
|     |     |     | ii ij    | i i | j     | i ij j j i  |     |
|     |     |     | i,j=1    |     | i,j=1 |             |     |
N
|     |     |     | ∑     | −x)2. |     |     | (7.10) |
| --- | --- | --- | ----- | ----- | --- | --- | ------ |
|     |     | =   | pa (x |       |     |     |        |
|     |     |     | i ij  | j i   |     |     |        |
i,j=1
By Theorem 4.31 in [13],  p >0, ∀i=1, …, N, implying P>0. It then follows
i
| from (7.10) that XTQX |     |     | ≥0, ∀X | ∈N; thus, Q≥0. □ |     |     |     |
| --------------------- | --- | --- | ------ | ----------------- | --- | --- | --- |
Lemma 7.7 relates the generalized graph Laplacian potential with the Laplacian
matrix. In fact, we shall see that it provides a way to construct a Lyapunov function
for digraphs. A similar result for constructing the Lyapunov equation (7.8) can also
be found in [13], as follows.

228 7 Graph Laplacian Potential and Lyapunov Functions for Multi-Agent Systems
Lemma 7.8 [13] Let the Laplacian matrix L be an irreducible singular M-matrix.
Let x>0 and y>0 be the right and left eigenvectors of L associated with eigen-
value λ=0, i.e., Lx=0 and LTy=0. Define
P=diag{p}=diag{y /x},
i i i
Q= PL+LTP.
Then P>0 and Q≥0.
Remark 7.1 When the graph is strongly connected, its Laplacian matrix L is an
irreducible singular M-matrix and rank(L)= N−1 ([13] Theorem 4.31). Then,
the dimension of the null space of L is 1 ([2] Corollary 2.5.5). Since L1 =0,
N
null(L)=span{1 }. Thus in Lemma 7.8, x=α1 , ∀α>0, and α∈. It is clear
N N
then that the methods for constructing the Lyapunov equations in Lemma 7.7 and
Lemma 7.8 are essentially the same. ▋
Lemma 7.9 Let the digraph be strongly connected and its Laplacian potential P
L
be defined by (7.7). Then P =0 if and only if consensus of the multi-agent systems
L
is achieved, i.e., x = x , ∀i, j=1,…,N.
i j
Proof Sufficiency is trivial by noticing the identity (7.9). Necessity is shown as
follows.
Since Q≥0, by Lemma 7.2, P = XTQX =0 implies that X ∈null(Q).
L
Next we shall show null(Q)=span{1 }. For any X ∈null(L), it is clear
N
that XTQX = XT(PL+LTP)X =2XTPLX =0. Lemma 7.2 implies that
null(L)⊆null(Q). When the graph is strongly connected, null(L)=span{1 };
N
then we have span{1 }⊆null(Q). We are left to show that the dimension of the
N
null space of Q is 1. The fact of Q1 =0 and the definition (7.8) implies that Q
N
can be treated as a valid Laplacian matrix of an augmented graph , which has the
same node set as graph  and the weight of edge (v ,v) being a = pa + p a .
j i ij i ij j ji
Obviously, graph  is undirected. Since p ≥0, it is clear that if a >0, then
i ij
a =a >0. Then, the strong connectedness of digraph  implies the connect-
ij ji
edness of the undirected graph . Thus, rank(Q)= N−1 and the dimension of
the null space of Q is 1. Therefore, null(Q)=span{1 }. Then X ∈null(Q), i.e.,
N
X =α1 , α∈ is equivalent to the consensus of the multi-agent system. □
N
The next section shows how the graph Laplacian potential plays an important role
in the Lyapunov analysis of consensus.
7.3 Lyapunov Analysis for Cooperative Regulator
Problems
In this section, Lyapunov analysis is demonstrated for two classes of consensus
problems. Note that we are not attempting to propose new control protocols, but to
provide Lyapunov analysis techniques for existing protocols to show how Lyapunov

7.3  Lyapunov Analysis for Cooperative Regulator Problems  229
functions are related to graph Laplacian potentials. Such Lyapunov functions are
used in the next chapters for the design of novel adaptive control laws for coopera-
tive control that are distributed on communication graphs.
7.3.1   Consensus of Single-Integrator Cooperative Systems
Consider a group of N agents with scalar single-integrator dynamics,
|     |     | x =u, i=1,…,N, |     | (7.11) |
| --- | --- | --------------- | --- | ------ |
|     |     | i i             |     |        |
where  x ∈ is the state and u ∈ is the control input. Consider the standard
| i   |     | i   |     |     |
| --- | --- | --- | --- | --- |
linear consensus protocol (e.g., [8, 11, 12, 14, 15]):
N
|     |     | =−∑a   | −x  |        |
| --- | --- | ------ | --- | ------ |
|     |     | u (x   | ).  | (7.12) |
|     |     | i ij i | j   |        |
|     |     | j=1    |     |        |
X
The  closed-loop  system  can  be  written  collectively  as  =−LX,  where
| X =[x,…,x | ]T. |     |     |     |
| --------- | --- | --- | --- | --- |
| 1         | N   |     |     |     |
It is well known that consensus can be reached using the linear control protocol
(7.12) for undirected graphs, balanced digraphs, strongly connected digraphs, and
digraphs containing a spanning tree. These results exist in the literature [8, 12, 14],
where the analysis is based on eigenvalue properties. Here, we shall provide an al-
ternative analysis using a Lyapunov method and show how graph Laplacian poten-
tial plays a key role in the Lyapunov analysis. We present a technique that extends
consensus/synchronization analysis methods for undirected graphs or balanced di-
graphs to strongly connected digraphs.
Lemma 7.10 If the undirected graph  is connected, consensus of (7.11) is reached
using the control law (7.12).
N
Proof Consider the Lyapunov function candidate V =∑ x2 = XTX. Then
i
i=1
|     |     | V =2XTX =−2XTLX. |     |     |
| --- | --- | ------------------ | --- | --- |
Lemma 7.1 implies V
|     | =−P | ≤0. By LaSalle’s invariance principle [9], the trajec- |     |     |
| --- | --- | ------------------------------------------------------ | --- | --- |
L
tories converge to the largest invariant set S ={X ∈(cid:31)|V(cid:30) =0}. Lemma 7.4 leads to
| S ={X |X =α1 | ,∀α∈}, i.e., consensus is reached.  |     |     | □   |
| ------------ | ------------------------------------ | --- | --- | --- |
N
For a directed graph, generally L≥0 does not hold; thus, the development in Lem-
ma 7.10 fails. However, when the directed graph is balanced, we have L+LT ≥0,
which leads to a method of Lyapunov analysis for consensus.
Lemma 7.11 If the digraph  is balanced and weakly connected, consensus of
(7.11) is reached using the linear control law (7.12).

230 7 Graph Laplacian Potential and Lyapunov Functions for Multi-Agent Systems
Proof Consider the Lyapunov function candidate V =∑N x2 = XTX. Then,
i=1 i
V =2XTX =−2XTLX =−XT(L+LT)X
By Lemma 7.5, V =−P ≤0. By LaSalle’s invariance principle [9], the tra-
L
jectories converge to the largest invariant set S ={X ∈(cid:31)N |V(cid:30) =0}, i.e.,
S ={X ∈N |P =0}. Since digraph  is weakly connected, Lemma 7.6 yields
L
S ={X ∈(cid:25)N |X =α1 ,∀α∈(cid:25)} i.e., consensus is reached. □
N
Note that when a digraph is balanced and weakly connected, it is strongly connected
([4] Lemma 2.6.1), but not vice versa. For a general strongly connected graph, when
it is not balanced, if we still define its Laplacian potential as (7.3), then V ≠−P.
L
Lyapunov analysis methods similar to those just used do not work. To overcome this
drawback, in the next proof we define a generalized Laplacian potential for strongly
connected graphs based on Lemma 7.7. The next Lemma appears in [12], where
an eigenvalue approach for consensus analysis is carried out. In the proof given
here, we introduce a Lyapunov function suitable for consensus analysis on general
strongly connected digraphs.
Lemma 7.12 For strongly connected digraphs, consensus of (7.11) is reached
using the linear control law (7.12) ([12] Corollary 1).
Proof Consider the Lyapunov function candidate
N
V =∑px2 = XTPX, (7.13)
i i
i=1
where P=diag{p} is defined in Lemma 7.7. Then,
i
V =2XTPX =−2XTPLX =−XT(PL+LTP)X =−XTQX.
By Lemma 7.7, Q≥0; hence V =−P ≤0. By LaSalle’s invariance principle, the
L
trajectories converge to the largest invariant set, S ={X ∈(cid:31)N |V(cid:30) =0}. By Lemma
7.9, it is straightforward that S ={X ∈N |X =α1 ,∀α∈}, i.e., the consensus
N
of (7.11) is achieved. □
Remark 7.2 Note that in Lemma 7.10, Lemma 7.11, and Lemma 7.12, the deriva-
tive of the Lyapunov function is exactly the associated negative graph Laplacian
potential -P. We have introduced in the proof of Lemma 7.12 a technique for the
L
Lyapunov analysis of consensus on directed graphs. The method relies on using a
Lyapunov function whose quadratic terms are weighted by the elements p of the
i
first left eigenvector of the graph Laplacian matrix L. This is equivalent to using the
Lyapunov equation (7.8), where P is a diagonal matrix of the p. This highlights the
i
importance of the first left eigenvector elements in studying decreasing flows on
graphs. Through an example in Sect. 7.2.2, we show the importance of the elements
p in preserving passivity properties on digraphs. ▋
i

7.3  Lyapunov Analysis for Cooperative Regulator Problems  231
7.3.2   Synchronization of Passive Nonlinear Systems
This section explores the technique mentioned in Remark 7.2 for analysis of syn-
chronization of passive nonlinear systems [3]. It is shown that analysis of passive
systems on digraphs can be accomplished by using a Lyapunov function based on
storage functions that are weighted by the elements p of the first left eigenvector
i
of the graph Laplacian matrix L, as motivated in Lemma 7.7. This highlights the
importance of the elements p in preserving the passivity properties of systems on
i
digraphs. Similar techniques are used in [6].
Passive systems are important because many mechanical systems built from
masses, springs, and dampers have the passivity property [3, 16] and can be mod-
eled by passive nonlinear systems, such as the robot manipulator. Note also that the
single-integrator dynamics is a special type of passive systems.
Chopra and Spong [3] studied the output synchronization of multi-agent sys-
tems, with each agent modeled by an input affine nonlinear system that is input–
output passive. One of their results assumed that the digraph is strongly connected
and balanced. Using the technique indicated in Remark 7.2, here we relax their
condition to general strongly connected digraphs.
The problem formulation and synchronization result of [3] are briefly presented
as follows. Consider N agents and let the communication graph be unweighted,
strongly connected, and balanced. Each agent i is modeled by a passive nonlinear
system,
|     |     | x = f (x)+g | (x)u  |     |
| --- | --- | ------------ | ----- | --- |
|     |     | i i i        | i i i |     |
y =h(x), (7.14)
|     |     | i i i |     |     |
| --- | --- | ----- | --- | --- |
where  x ∈n is the state, u ∈m is the control input, and  y ∈m is the out-
| i   |     | i   |     | i   |
| --- | --- | --- | --- | --- |
put. The nonlinear functions  (·),  (·), and h(·) are sufficiently smooth with
f g
|     |     | i i | i   |     |
| --- | --- | --- | --- | --- |
f (0)=0 and h(0)=0.
| i   | i   |     |     |     |
| --- | --- | --- | --- | --- |
The control protocol for each agent is the static output feedback,
∑(y (7.15)
|     |     | u = | −y ) |     |
| --- | --- | --- | ---- | --- |
|     |     | i   | j i  |     |
j∈Ni
The group of agents are said to output synchronize if lim y (t)−y (t) =0,∀i, j.
|     |     |     | t→∞ | i j |
| --- | --- | --- | --- | --- |
The following Lemma states an important property of passive systems.
Lemma 7.13 System (7.14) is passive if and only if there exists a continuously
differentiable storage function V :n → with V(x)≥0 and V(0)=0, and a
|            |                     | i   | i i | i   |
| ---------- | ------------------- | --- | --- | --- |
| function S | (x)≥0 such that [3] |     |     |     |
i i
|     | T       |               | T            |     |
| --- | ------- | ------------- | ------------ | --- |
|     | ∂V    |               | ∂V         |     |
|     | i       |               | i (x)=hT(x). |     |
|     |   f   | (x)=-S (x)and |   g        |     |
|     | ∂x  i | i i i         | ∂x  i i    | i i |
|     | i       |               | i            |     |

232 7  Graph Laplacian Potential and Lyapunov Functions for Multi-Agent Systems
One of the results in [3] is given in the following theorem. An outline of the proof is
presented here to better illustrate our aforementioned technique in Remark 7.2. For
details of the proof of Theorem 7.1, readers are referred to [3].
Theorem 7.1 Consider the system (7.14) with control protocol (7.15) ([3] Theorem 2).
Suppose the communication digraph  is strongly connected and balanced. Then,
the group of agents output synchronize.
Proof Consider the Lyapunov function candidate for the group of N agents defined
as
|     |     |     | V =2(V | +V  | +…+V | )   |     | (7.16) |
| --- | --- | --- | ------ | --- | ---- | --- | --- | ------ |
|     |     |     |        | 1   | 2    | N   |     |        |
where V is the storage function for agent i. Then, using the passivity property in
i
Lemma 7.13 and a balanced digraph property, it is shown in [3] that
|     |     |       | N      | N        |         |      |             |     |
| --- | --- | ----- | ------ | -------- | ------- | ---- | ----------- | --- |
|     |     | =−2∑S |        | )−∑ ∑    |         | )T(y |             |     |
|     | V   |       | i (x i |          | (y i −y | j    | i −y j )≤0. |     |
|     |     |       | i=1    | i=1 j∈Ni |         |      |             |     |
LaSalle’s invariance principle and the strong connectivity of the digraph then imply
| the output synchronization of system (7.14).  |     |     |     |     |     |     |     | □   |
| --------------------------------------------- | --- | --- | --- | --- | --- | --- | --- | --- |
In the next theorem, we extend Theorem 7.1 to weighted, strongly connected di-
graphs. Here, we consider the control protocol based on the output feedback,
N
|     | u = | ∑ a  | (y −y | )=∑a | (y   | −y ),∀i=1,2,…,N. |     | (7.17) |
| --- | --- | ---- | ----- | ---- | ---- | ---------------- | --- | ------ |
|     | i   |      | ij j  | i    | ij j | i                |     |        |
|     |     | j∈Ni |       | i=1  |      |                  |     |        |
This is a general case of (7.15) where the edge weights a  take the values of 0 or 1.
ij
Theorem 7.2 Consider the system (7.14) with control law (7.17). Suppose the com-
munication graph  is a strongly connected digraph. Then, the group of agents
| output synchronize, i.e., y |     |     | = y | ,∀i, j=1,…,N. |     |     |     |     |
| --------------------------- | --- | --- | --- | ------------- | --- | --- | --- | --- |
i j
]T
Proof Since the digraph  is strongly connected, we can define p=[p,…, p
1 N
as in Definition 7.2, such that  pTL=0. Consider the Lyapunov function candidate
|     |     |     | V =2(pV | + p | V +…+ | p V | ),  | (7.18) |
| --- | --- | --- | ------- | --- | ----- | --- | --- | ------ |
|     |     |     |         | 1 1 | 2 2   | N N |     |        |
where V are same storage functions as in Theorem 7.1. Then,
i
N
V(cid:28) =2∑pV(cid:28)
i i
i=1
|     |     |        | N   |       | N   |     |     |     |
| --- | --- | ------ | --- | ----- | --- | --- | --- | --- |
|     |     | =−2∑pS |     | )+2∑p | yTu |     |     |     |
(x
|     |     |        | i   | i i        | i   | i i    |      |        |
| --- | --- | ------ | --- | ---------- | --- | ------ | ---- | ------ |
|     |     |        | i=1 |            | i=1 |        |      |        |
|     |     |        | N   |            | N N |        |      |        |
|     |     | =−2∑pS |     | (x )+2∑∑pa |     | yT(y   | −y ) | (7.19) |
|     |     |        | i   | i i        |     | i ij i | j i  |        |

|     |     |     | i=11 |     | i=1j=1 |     |     |     |
| --- | --- | --- | ---- | --- | ------ | --- | --- | --- |

7.3 Lyapunov Analysis for Cooperative Regulator Problems 233
Since pTL=0 implies that p ∑N a =∑N a p , it follows that
i j=1 ij j=1 ji j
N N
∑∑pa yT(y −y )
i ij i j i
i=1 j=1
N N
=∑p yT∑a (y −y )
i i ij j i
i=1 j=1
N N N
= ∑ a p yTy −∑p yTy ∑a
ij i i j i i i ij
i,j==1 i=1 j=1
N N N
= ∑ a p yTy −∑yTy ∑a p
ij i i j i i ji j
i,j=1 i=1 j=1
N N
= ∑ a p yTy − ∑ aa p yTy
ij i i j ij i j j
i,j=1 i,j=1
N
= ∑ a p yT(y −y )
ij i j i j
i,j=1
Equation (7.19) can be written as
N N N
V(cid:28) =−2∑ pS (x )+ ∑ pa yT(y −y )+ ∑ a p yT(yy −y )
i i i i ij i j i ij i j i j
i=1 i,j=1 i,j=1
N N
=−2∑ pS (x )+ ∑ pa (y −y )T(y −y )
i i i i ij i j j i
i=1 i,j=1
N N
=−2∑∑ pS (x )− ∑ pa (y −y )T(y −y )≤0.
i i i i ij i j i i
i=1 i,j=1
By LaSalle’s invariance principle, the trajectories of system (7.14) converge to the larg-
est invariant set S ={x | pS (x)=0, pa (y −y )T(y −y )=0,∀i, j=1,…,N}.
i i i i i ij i j i j
Since p >0,∀i=1,…,N and the graph is strongly connected, pa (y −y )T ⋅
i i ij i j
(y −y )=0,∀i, j=1,…,N implies that y = y ,∀i, j=1,…,N. □
i j i j
Remark 7.3 Theorem 7.2 extends the result in Theorem 7.1 to general strongly
connected graphs. This is achieved by simply modifying the Lyapunov function
(7.16) to (7.18), which weights the node storage functions by the elements p of the
i
first left eigenvector of the graph Laplacian matrix L. This shows the importance
of the elements p in preserving the passivity properties of multi-agent systems on
i
digraphs. ▋

234 7 Graph Laplacian Potential and Lyapunov Functions for Multi-Agent Systems
References
1. Astrom KJ, Wittenmark B (2008) Adaptive Control, 2nd edn. Dover, Mineola
2. Bernstein D (2009) Matrix Mathematics: Theory, Facts, and Formulas, 2nd edn. Princeton
University Press, Princeton
3. Chopra N, Spong M (2006) Passivity-based control of multi-agent systems. In: Kawamura S,
Svinin M (eds) Advances in Robot Control: From Everyday Physics to Human-Like Move-
ments. Springer-Verlag, Berlin
4. Godsil C, Royle G (2001) Algebraic Graph Theory. Springer-Verlag, New York
5. Horn R, Johnson C (1990) Matrix Analysis. Cambridge University Press, New York
6. Igarashi Y, Hatanaka T, Fujita M, Spong M (2008) Passivity-based output synchronization
and flocking algorithm in SE (3). In: Proc. Amer. Control Conf., Seattle, WA, pp. 723–728
7. Ioannou P, Fidan B (2006) Adaptive Control Tutorial. SIAM Press, Philadelphia
8. Jadbabaie A, Lin J, Morse A (2003) Coordination of groups of mobile autonomous agents
using nearest neighbor rules. IEEE Trans Automat Contr 48(6):988–1001
9. Khalil H (2002) Nonlinear Systems, 3rd edn. Prentice Hall, Upper Saddle River
10. Landau ID, Lozano R, Saad MM (2011) Adaptive Control. Springer-Verlag, Berlin
11. Olfati-Saber R, Murray R (2003) Consensus protocols for networks of dynamic agents. In:
Proc. Amer. Control Conf., Denver, CO, pp. 951–956
12. Olfati-Saber R, Murray R (2004) Consensus problems in networks of agents with switching
topology and time-delays. IEEE Trans Automat Contr 49(9):1520–1533
13. Qu Z (2009) Cooperative Control of Dynamical Systems: Applications to Autonomous Ve-
hicles. Springer-Verlag, London
14. Ren W, Beard R (2008) Distributed Consensus in Multi-Vehicle Cooperative Control: Theory
and Applications. Springer-Verlag, London
15. Ren W, Beard R, Atkins E (2007) Information consensus in multivehicle cooperative control.
IEEE Contr Systs Mag 27(2):71–82
16. Spong M, Hutchinson S, Vidyasagar M (2006) Robot Modeling and Control. Wiley, New
York
17. Zhang H, Lewis FL, Qu Z (2012) Lyapunov, adaptive, and optimal design techniques for co-
operative systems on directed communication graphs. IEEE Trans Ind Elec 59(7):3026–3041

Chapter 8
Cooperative Adaptive Control for Systems
with First-Order Nonlinear Dynamics
In cooperative control systems, the control protocol for each agent is allowed to
depend only on information about itself and its neighbors in the graph topology. We
have confronted this problem for optimal cooperative control design in Part I of the
book. In cooperative adaptive control systems, there is an additional problem. In
adaptive control systems, the control law depends on unknown parameters that are
tuned online in real time to improve the performance of the controller, whereas the
challenge in cooperative adaptive control is to make sure that both the control pro-
tocols and the parameter tuning laws are distributed in terms of the allowed graph
topology. That is, they are allowed to depend only on locally available information
about the agent and its neighbors. We shall see in this chapter that the key to the de-
sign of distributed adaptive tuning algorithms is the selection of suitable Lyapunov
functions that depend on the graph topology. This is closely connected to the selec-
tion of global performance indices that depend on the graph topology in Chap. 5.
The basis for the selection of suitable graph-dependent Lyapunov functions was laid
in the discussion on the graph Laplacian potential in Chap. 7.
In Part I, the agent dynamics were taken as homogeneous, that is, all agents
had the same dynamics. Moreover, the dynamics were assumed to be known and
were used to compute the control protocols. By contrast, in Part II of this book the
agent dynamics are taken as heterogeneous, that is, non-identical. Moreover, they
are unknown, meaning that the dynamics are not allowed to appear in the control
protocols. Finally, the agent dynamics may be affected by unknown disturbances.
Synchronization control protocols for multi-agent systems with heterogeneous un-
known dynamics are designed here using adaptive control techniques.
The results in this chapter were published first in [2].
F. L. Lewis et al., Cooperative Control of Multi-Agent Systems, 235
Communications and Control Engineering, DOI 10.1007/978-1-4471-5574-4_8,
© Springer-Verlag London 2014

236 8 Cooperative Adaptive Control for Systems with First-Order Nonlinear Dynamics
8.1 Synchronization Control Formulation
and Error Dynamics
In this section we formulate the synchronization control problem for multi-agent
cooperative systems linked by an interaction graph structure. Unlike in Part I, the
agent dynamics are heterogeneous, that is, non-identical. Moreover, they are un-
known, meaning that the dynamics are not allowed to appear in the control proto-
cols. This section formulates the basic structure of the distributed control protocols
to confront these problems. First, we develop the error dynamics for synchroniza-
tion, which are key in the design of cooperative control protocols. Based on the er-
ror dynamics, we derive the structure of a distributed control law that is suitable for
synchronization control for heterogeneous agents with unknown dynamics. These
control protocols depend on unknown parameters. In the next section it is shown
how to learn these unknown parameters online to guarantee synchronization by us-
ing adaptive control techniques.
8.1.1 Graph Theory Basics
We start with a review of some graph theory basics. Consider a graph G=(V,E)
with a non-empty finite set of N nodes V ={v,,v } and a set of edges or
1 N
arcs E⊆V ×V. We assume the graph is simple, e.g. no repeated edges and
(v,v)∉E,∀i no self-loops. General directed graphs are considered. Denote the
i i
connectivity matrix as A=[a ] with a >0if (v ,v)∈E and a =0 otherwise.
ij ij j i ij
Note that a =0. The set of neighbors of a node v is N ={v :(v ,v)∈E}, i.e.
ii i i j j i
the set of nodes with arcs incoming to v. Define the in-degree matrix as a diagonal
i
matrix D=[d ] with d = ∑ a the weighted in-degree of node i (i.e. i th row sum
i i ij
j∈Ni
of A). Define the graph Laplacian matrix as L= D−A, which has all row sums
equal to zero. Define do =∑a , the (weighted) out-degree of node i, that is the
i ji
i th column sum of A. j
We assume the communication digraph is strongly connected, i.e. there is a di-
rected path from v to v for all distinct nodes v,v ∈V. Then A and L are irreduc-
i j i j
ible [10]. That is they are not cogredient to a lower triangular matrix, i.e. there is no
permutation matrix U exists such that
* 0
L=U   UT (8.1)
* *
The results of this research can easily be extended to graphs having a spanning tree
(i.e. not necessarily strongly connected) using the Frobenius form shown in (8.1)
[10].

8.1 Synchronization Control Formulation and Error Dynamics 237
8.1.2 Synchronization Control Problem
Consider node dynamics defined for the i th node as
x = f (x)+u +w(t) (8.2)
i i i i i
where x(t)∈R is the state of node i, u (t)∈R is the control input, and w(t)∈R
i i i
is an unknown disturbance acting upon each node. Note that each node may have its
own distinct dynamics. This is referred to as non-identical or heterogeneous agent
dynamics. Standard assumptions for the existence of unique solutions are made, e.g.
f (x) is either continuously differentiable or Lipschitz.
i i
It is assumed that the agent drift dynamics f (x) are unknown. Thus, they are
i i
not available for use in the control protocols designed in this chapter.
It is assumed for ease of notation that the agents’ states are scalars, x(t)∈R. If
i
the states are vectors x(t)∈Rn, the results of this chapter can be extended using
i
standard methods involving the Kronecker products employed in various chapters
in Part I of the book.
The overall global graph dynamics is
x = f(x)+u+w (8.3)
where the overall (global) state vector is x=(x,x ,,x )T ∈RN, global
1 2 N
node dynamics vector is f(x)={f (x ), f (x ),, f (x )}T ∈RN, input
1 1 2 2 N N
u=(u ,u ,,u )∈RN, and w=(w,w ,,w )∈RN.
1 2 N 1 2 N
Definition 8.1 The local neighborhood synchronization error for node i is defined
as [8],[6]
e = ∑a (x −x)+b(x −x) (8.4)
i ij j i i 0 i
j∈Ni
with x the state of a leader or control node, pinning gains b ≥0, and b >0 for at
0 i i
least one agent i who has direct knowledge of the state of the leader [8],[13]. Then,
b ≠0 if and only if there exists an arc from the control node to the i th node in G.
i
We refer to the nodes i for which b ≠0 as the pinned or controlled nodes.
i
Note that (8.4) contains the entirety of the information that is available to any node
i for control purposes.
A desired synchronization trajectory is given as the state x (t) of a leader or
0
control node having non-autonomous command generator dynamics
x = f(x ,t) (8.5)
0 0
A special case is the standard constant consensus value with x =0. The drift term
0
f(x ,t) could represent, e.g. motion dynamics of the control node. That is, we as-
0
sume that the control node can have a time-varying state. The interesting cases are

238 8  Cooperative Adaptive Control for Systems with First-Order Nonlinear Dynamics
when the leader’s trajectory does not converge to zero. These command generator
dynamics can produce a wide variety of reference trajectories, including position
step commands, velocity ramp commands, sinusoidal trajectories, and so on.
The distributed synchronization control design problem confronted herein is as
follows: Design control protocols for all the nodes in G to synchronize to the state
of the control node, i.e. one requires x(t)→x (t),∀i. The control protocols must
|     |     |     |     | i   | 0   |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- |
be distributed in the sense that they can only depend on local information about the
agent and its neighbors in the graph. It is assumed that the dynamics of the control
node is unknown to any of the nodes in G. It is further assumed that both the node
nonlinearities  f (.) and the node disturbances w(t) are unknown. Thus, the syn-
|     |     | i   |     |     | i   |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- |
chronization protocols cannot contain any of the dynamics of agents or leader, and
so must be robust to unmodeled dynamics and unknown disturbances.
In fact, (8.5) is a command generator. Therefore, we are considering a distributed
command generator tracker problem with unknown node dynamics and unknown
command generator dynamics.
8.1.3  Synchronization Error Dynamics
From (8.4), the global error vector for the network is given by

|     |     | e=−(L+B)(x−1x |     | )=−(L+B)(x−x |     | )   |       |
| --- | --- | ------------- | --- | ------------ | --- | --- | ----- |
|     |     |               |     | 0            |     | 0   | (8.6) |
T
| where  | e e | e     | e   | RN and  | x =1x ∈RN. B∈RN×N is a diago- |     |     |
| ------ | --- | ----- | --- | ------- | ----------------------------- | --- | --- |
|        | = 1 | 2 ··· | N ∈ |         | 0 0                           |     |     |
nal matrix with diagonal entries b  and 1 is the N-vector of ones.
|                                                                       | (cid:31) |     | (cid:30) i |     |     |     |     |
| --------------------------------------------------------------------- | -------- | --- | ---------- | --- | --- | --- | --- |
| Differentiating (8.6), one obtains the synchronization error dynamics |          |     |            | −   |     |     |     |

e(cid:31)=−(L+B)(x(cid:31)−x(cid:31) ) =−(L+B)f(x)− f(x ,t)+u+w(t) (8.7)
|     |     |     | 0   |    |     | 0   |    |
| --- | --- | --- | --- | --- | --- | --- | --- |
RN.
| where f(x | 0 ,t) | 1f(x 0 (t),t) |     |     |     |     |     |
| --------- | ----- | ------------- | --- | --- | --- | --- | --- |
|           | =     |               | ∈   |     |     |     |     |
|           | −     | −             |     |     |     |     |     |
Remark 8.1 If the node states are vectors x(t)∈Rn and x (t)∈Rn, then x,e∈RnN
|     |     |     |     | i   |     | 0   |     |
| --- | --- | --- | --- | --- | --- | --- | --- |
and (8.6) becomes

|     |     | e [(L | B) I | ][f(x) | f(x ,t) | u w(t)] | (8.8) |
| --- | --- | ----- | ---- | ------ | ------- | ------- | ----- |
|     |     | ˙ =−  | + ⊗  | n −    | 0       | + +     |       |
−
with ⊗ the Kronecker product. To avoid obscuring the essentials, throughout the
research we take the node states as scalars,  x(t)∈R. If they are vectors, all of
i
the following development is easily modified by introducing the Kronecker prod-
uct terms as appropriate. In fact, a simulation example is presented for the case
x(t)∈R2, namely one-dimensional (1-D) motion control for coupled inertial
i
agents.  ▋
Remark 8.2 Note that

|     |     |     | δ=(x−x |     | )   |     | (8.9) |
| --- | --- | --- | ------ | --- | --- | --- | ----- |
0

8.1  Synchronization Control Formulation and Error Dynamics  239
is the disagreement vector in [9]. We do not use this error herein because it is a
global quantity that cannot be computed locally at each node, in contrast to the
local neighborhood error (8.4). As such, it is suitable for analysis but not for dis-
tributed adaptive controls design using Lyapunov techniques.  ▋
Remark 8.3 We take the communication digraph as strongly connected. Therefore,
if  b ≠0 for at least one i then  (L+B) is an irreducibly diagonally dominant
i
M-matrix and hence nonsingular [10]. It has all poles in the open right-half s-plane.
A milder condition that guarantees (L+B) is nonsingular is the existence of a
| spanning tree with b |     | ≠0 for at least one root node i.  |     |     |     |     | ▋   |
| -------------------- | --- | --------------------------------- | --- | --- | --- | --- | --- |
i
An M-matrix is a square matrix having its off-diagonal entries nonpositive and all
principal minors nonnegative. Based on Remark 8.3, the next result is therefore
obvious from (8.6) and the Cauchy Schwartz inequality. (see also [6]).
Lemma 8.1 Let the graph be strongly connected and B≠0. Then

|     |     |     | δ ≤ e /σ(L+B) |     |     |     |  (8.10) |
| --- | --- | --- | ------------- | --- | --- | --- | ------- |
with σ(L+B) the minimum singular value of (L+B), and e=0 if and only if the
nodes synchronize, that is,
|     |     |     | x(t)= x | (t) |     |     |        |
| --- | --- | --- | ------- | --- | --- | --- | ------ |
|     |     |     | 0       |     |     |     | (8.11) |
8.1.4  Synchronization Control Design
The control problem confronted in this chapter is to design a control strategy so that
local neighborhood error e(t) is bounded to a small residual set. Then according to
Lemma 8.1, all nodes synchronize so that  x(t)-x (t)  is small ∀i. It is assumed
i 0
that the dynamics  f(x ,t) of the control node is unknown to any of the nodes in
0
G. It is assumed further that both the node non-linearities  f (.) and the node distur-
i
bances w(t) are unknown. As such, the synchronization protocols must be robust
i
to unmodeled dynamics and unknown disturbances.
| To achieve this goal, define the input u |     |     |  for node i as |     |     |     |     |
| ---------------------------------------- | --- | --- | -------------- | --- | --- | --- | --- |
i

|     |     |     | u v     | f (x ) |     |     | (8.12) |
| --- | --- | --- | ------- | ------ | --- | --- | ------ |
|     |     |     | i = i − | ˆi i   |     |     |        |
fˆ(x) is an estimate of
| where  |     |     | f (x) and v(t) is an auxiliary control signal to be  |     |     |     |     |
| ------ | --- | --- | ---------------------------------------------------- | --- | --- | --- | --- |
| i      | i   |     | i i                                                  | i   |     |     |     |
designed via Lyapunov techniques in Theorem 8.1. This can be written in vector
form for the overall network of N nodes as

|     |     |     | u v f(x) |     |     |     |        |
| --- | --- | --- | -------- | --- | --- | --- | ------ |
|     |     |     |          | ˆ   |     |     | (8.13) |
= −
|               |     |                 | fˆ(x)={fˆ(x |     | fˆ        | fˆ  |           |
| ------------- | --- | --------------- | ----------- | --- | --------- | --- | --------- |
| where  v=(v,v |     | ,....,v )T ∈RN  | and         | ),  | (x ),..., | (x  | )}T ∈RN.  |
|               | 1 2 | N               |             | 1 1 | 2 2       | N N |           |
Then from (8.7) one gets

|     |     | e (L   | B)[f(x) f(x | 0 ,t) f(x) | v   | w]  | (8.14) |
| --- | --- | ------ | ----------- | ---------- | --- | --- | ------ |
|     |     | ˙ =− + | −           | − ˆ        | + + |     |        |
−

240 8  Cooperative Adaptive Control for Systems with First-Order Nonlinear Dynamics
Following the techniques in [3],[4],[7], assume that the unknown nonlinearities in
(8.2) are locally smooth and thus can be approximated on a compact set Ω ∈R by
i
|               |     |     |     |          | Tϕ   |       |     |        |
| ------------- | --- | --- | --- | -------- | ---- | ----- | --- | ------ |
|               |     |     | f i | (x i ) W | i (x | i ) ε | i   | (8.15) |
|               |     |     |     | =        | i    | +     |     |        |
| with ϕ(x)∈Rνi |     |     |     |          |      |       |     | ∈Rνi   |
 a suitable basis set of ν functions at each node i and W  a
|     | i i |     |     |     | i   |     |     | i   |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
set of unknown coefficients. The approximation error is ε.
i
According to the neural network (NN) approximation literature [3],[4],[7],
a variety of basis sets can be selected, including sigmoids, gaussians, etc. There
ϕ(x)∈Rνi  is known as the NN activation function vector and W ∈Rνi  as the NN
| i   | i   |     |     |     |     |     | i   |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
∈Rνi
weight matrix. The ideal approximating weights W  in (8.15) are assumed
i
unknown. The NN in (8.15) are local at each agent. For computational efficiency,
the intention is to select only a small number ν of NN neurons at each node (see
i
Simulation Examples).
To compensate for unknown nonlinearities, each node will maintain a neural
network locally to keep track of the current estimates for the nonlinearities. The
idea is to use the information of the states from the neighbors of node i to evaluate
the performance of the current control protocol along with the current estimates of
the nonlinear functions. Therefore, select the local node’s approximation f (x ) as
ˆi i
|     |     |     |     | f (x ) | W Tϕ | (x ) |     |        |
| --- | --- | --- | --- | ------ | ---- | ---- | --- | ------ |
|     |     |     |     | ˆi i   | ˆi   | i i  |     | (8.16) |
=
where W Rνi is a current estimate of the NN weights for node i, and ν
|     | ˆi  |     |     |     |     |     |     | i is the  |
| --- | --- | --- | --- | --- | --- | --- | --- | --------- |
∈
number of NN neurons maintained at each node i. The control protocol for agent
i now becomes
|     |     |     |     |       | Tϕ   |      |     |        |
| --- | --- | --- | --- | ----- | ---- | ---- | --- | ------ |
|     |     |     |     | u v   | W    | (x ) |     | (8.17) |
|     |     |     |     | i = i | − ˆi | i i  |     |        |
It will be shown in Theorem 8.1 how to select the estimates of the parameters
W Rνi using the local neighborhood synchronization errors (8.4) to guarantee
ˆi
∈
synchronization.
The global node nonlinearity  f(x) for the entire graph G is now written as
|     |     |     |      |     | WTϕ(x) |     |     |        |
| --- | --- | --- | ---- | --- | ------ | --- | --- | ------ |
|     |     |     | f(x) |     |        | ε   |     | (8.18) |
|     |     |     |      | =   |        | +   |     |        |
T
where WT =diag{W T}, ϕ(x) ϕ 1 T(x 1 ),ϕ 2 T(x 2 ),....,ϕ N T(x N ) , and ε={ε ,ε ,....,ε }T
|     |     | i   | ={  |     |     |     | }   | 1 2 N |
| --- | --- | --- | --- | --- | --- | --- | --- | ----- |
∈RN. The global estimate f(x) is
ˆ

|     |     |     |     | f(x) | WTϕ(x) |     |     | (8.19) |
| --- | --- | --- | --- | ---- | ------ | --- | --- | ------ |
|     |     |     |     | ˆ    | ˆ      |     |     |        |
=
with WT diag WT . Now, the error dynamics (8.14) takes the formv(t)
|     | ˆ   | ˆi  |     |     |     |     |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
|     | =   | { } |     |     |     |     |     |     |

|     |     | e    | (L  | B)[f (x) | v   | w(t) | f(x ,t)] |        |
| --- | --- | ---- | --- | -------- | --- | ---- | -------- | ------ |
|     |     |      |     | ˜        |     |      | 0        | (8.20) |
|     |     | ˙ =− | +   |          | + + | −    |          |        |
−

| 8.2  Adaptive Design and Distributed Tuning Law  |     |     |     |     |     |     | 241 |
| ------------------------------------------------ | --- | --- | --- | --- | --- | --- | --- |
where the parameter estimation error is W W W ˆi and the function estimation
|     |     |     |     | ˜i i |     |     |     |
| --- | --- | --- | --- | ---- | --- | --- | --- |
|     |     |     |     | = −  |     |     |     |
error is

|     |     | f(x) | f(x) | f(x) WTϕ(x) |     | ε   | (8.21) |
| --- | --- | ---- | ---- | ----------- | --- | --- | ------ |
|     |     | ˜    |      | ˆ ˜         |     |     |        |
|     |     | =    | −    | =           | +   |     |        |
with WT WT WT. Therefore, one obtains finally the error dynamics
| ˜   |     | ˆ   |     |     |     |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- |
= −

|     | e    | (L B)[W | Tϕ(x) | v ε   | w(t) | f(x ,t)] | (8.22) |
| --- | ---- | ------- | ----- | ----- | ---- | -------- | ------ |
|     |      |         | ˜     |       |      | 0        |        |
|     | ˙ =− | +       |       | + + + | −    |          |        |
−
with v(t) an auxiliary control yet to be designed.
8.2  Adaptive Design and Distributed Tuning Law
In this section, we show how to select the auxiliary controls v(t) and the tuning
i
laws for the NN weights W ˆi in the protocols (8.17) so as to guarantee that all nodes
synchronize to the desired control node signal, i.e. x(t)→x (t),∀i. It is assumed
|     |     |     |     |     | i   | 0   |     |
| --- | --- | --- | --- | --- | --- | --- | --- |
that the dynamics  f(x ,t) of the control node (which could represent its motion)
0
are unknown to any of the nodes in G. The Lyapunov analysis approaches of [5],[7]
are used, though there are some complications arising from the fact that v(t) and
the NN weight tuning laws must be implemented as distributed protocols. This en-
tails a careful selection of the Lyapunov function. The background for the choice of
suitable Lyapunov functions for cooperative control is given in Chap. 7.
The singular values of a matrix M are denoted  σ (M), with σ(M) the maxi-
i
mum singular value and  σ(M) the minimum singular value. The Frobenius norm
−
is  M tr MTM  with tr{·} the trace. The Frobenius inner product of two
(cid:31)F
| (cid:31) =   | {            | }        |     |     |     |     |     |
| ------------ | ------------ | -------- | --- | --- | --- | --- | --- |
| matrices is  | (cid:31)M ,M | = tr{MTM | }.  |     |     |     |     |
|              | 1            | 2 F      | 1 2 |     |     |     |     |
The following Fact gives two standard results used in neural adaptive control [7].
Fact 8.2 Let the nonlinearities  f(x) in (8.18) be smooth on a compact set Ω∈RN.
Then:
The NN estimation error ε(x) is bounded by  ε ε M on Ω, with ε
M a fixed
(cid:31) (cid:31)≤
bound [3],[7].
Weierstrass Higher-order Approximation Theorem [12] Select the activation
functions ϕ(x) as a complete independent basis (e.g. polynomials). Then NN esti-
mation error ε(x) converges uniformly to zero on Ω as ν , i 1,N. That
i
|     |     |     |     |     |     | →∞ = |     |
| --- | --- | --- | --- | --- | --- | ---- | --- |
is  ξ>0 there exist ν,i=1,N such that ν >ν,∀i implies sup ε(x) <ξ.
| ∀   |     | i   |     | i i |     | x (cid:30)(cid:30) | (cid:30) |
| --- | --- | --- | --- | --- | --- | ------------------ | -------- |
The following standard assumptions are required. Although the bounds men- ∈
tioned are assumed to exist, they are not used in the design and do not have to be
known. They appear in the error bounds in the proof of Theorem 8.1. (Though not
required, if desired, standard methods can be used to estimate these bounds includ-
ing [11].)

242 8  Cooperative Adaptive Control for Systems with First-Order Nonlinear Dynamics
Assumption 8.1
a. The unknown disturbance w  is bounded for all i. Thus the overall disturbance
i
| vector w is also bounded by  |     |     | w ≤w | , with w |  a fixed bound. |     |     |     |
| ---------------------------- | --- | --- | ---- | -------- | --------------- | --- | --- | --- |
|                              |     |     |      | M        | M               |     |     |     |
b. The  unknown  consensus  variable  dynamics  f(x ,t)  is  bounded  so  that
0
−
| f(x ,t) ≤F | ,∀t. |     |     |     |     |     |     |     |
| ---------- | ---- | --- | --- | --- | --- | --- | --- | --- |
| 0          | M    |     |     |     |     |     |     |     |
c. The target trajectory is in a bounded region, e.g.  x (t) < X ,∀t, with  X  a
|     |     |     |     |     |     | 0   | 0   | 0   |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
constant bound.
| d. Unknown ideal NN weight matrix W is bounded by  |     |     |     |     |     | W   | ≤W . |     |
| -------------------------------------------------- | --- | --- | --- | --- | --- | --- | ---- | --- |
|                                                    |     |     |     |     |     | F   | M    |     |
e. NN activation functions ϕ  are bounded ∀i, so that one can write for the overall
i
ϕ φ
| network that  |     | M.  |     |     |     |     |     |     |
| ------------- | --- | --- | --- | --- | --- | --- | --- | --- |
(cid:31) (cid:31)≤
Assumption 8.1.b means that the maximum velocity of the leader node is unknown
but bounded above.
The next definitions extend standard notions [5, 7] to synchronization for dis-
tributed systems.
Definition 8.2 The global neighborhood error e(t)∈RN is uniformly ultimately
bounded (UUB); if there exists a compact set Ω⊂RN so that ∀e(t )∈Ω, there
0
exists a bound B and a time  t (B,e(t )), both independent of  t ≥0, such that
|             |      |     | f   | 0   |     |     | 0   |     |
| ----------- | ---- | --- | --- | --- | --- | --- | --- | --- |
| e(t) ≤B∀t≥t | +t . |     |     |     |     |     |     |     |
0 f
Definition 8.3 The control node trajectory x (t) given by (8.5) is cooperative UUB
0
with respect to solutions of node dynamics (8.2) if there exists a compact set Ω⊂R so
)−x
that ∀(x (t )−x (t ))∈Ω there exists a bound B and a time t (B,(x (t (t ))),
| i 0 | 0 0 |     |     |     |     |     | f i 0 | i 0 |
| --- | --- | --- | --- | --- | --- | --- | ----- | --- |
both independent of t ≥0, such that  x(t)−x (t) ≤B∀i,∀t≥t +t .
|     | 0   |     |     | i   | 0   |     | 0 f |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
The next key constructive result is needed. It extends the discussion about coopera-
tive Lyapunov functions in Chap. 7 to the case of pinning control, that is, to the
cooperative tracker problem. It provides a Lyapunov equation that allows the design
of distributed control protocols that only depend on local information available at
each node about its own state and those of its neighbors. An M-matrix is a square
matrix having nonpositive off-diagonal elements and all principal minors nonnega-
tive.
Lemma 8.2 Lyapunov Functions for Distributed Control on Graphs [10] Let
L be irreducible and B have at least one diagonal entry b >0. Then (L+B) is a
i
nonsingular M-matrix. Define

|     | q   | q        | q   | q T        | (L  | B) 11 |     |        |
| --- | --- | -------- | --- | ---------- | --- | ----- | --- | ------ |
|     |     | 1        | 2   | N          |     | −     |     | (8.23) |
|     |     | =        | ··· |            | = + |       | −   |        |
|     |     | (cid:31) |     | (cid:30)   |     |       |     |        |
|     |     | P=diag{p |     | }≡diag{1/q |     | }     |     |        |
|     |     |          |     |            |     |       |     | (8.24) |
|     |     |          |     | i          | i   |       |     |        |
Then P>0 and the matrix Q defined as
|     |     |     | P(L+B)+(L+B)TP |     |     |     |     |        |
| --- | --- | --- | -------------- | --- | --- | --- | --- | ------ |
|     |     | Q=  |                |     |     |     |     | (8.25) |
is positive definite.

| 8.2  | Adaptive Design and Distributed Tuning Law  |     |     |     |     | 243 |
| ---- | ------------------------------------------- | --- | --- | --- | --- | --- |
The main result of this research is given by Theorem 8.1, which shows how to
design the control protocols (8.17) and tune the NN weights such that the local
neighborhood cooperative errors (8.4) for all nodes are UUB. According to Lemma
8.1, this implies consensus variable  x (t) is cooperative UUB, thereby showing
0
synchronization and cooperative stability for the whole network G.
Theorem 8.1 Distributed Adaptive Control Protocol for Synchronization Con-
sider the networked systems given by (8.2), (8.3) under Assumption 8.1. Let the
communication digraph be strongly connected. Select the auxiliary control sig-
nals in (8.17) as v(t)=ce(t) with the neighborhood synchronization errors e(t)
|     |     | i i |     |     |     | i   |
| --- | --- | --- | --- | --- | --- | --- |
defined in (8.4) so that the local node control protocols are given by

|     | u =ce | - fˆ(x)=c∑a | (x -x)+cb(x | -x)-WˆTϕ(x) |       | (8.26) |
| --- | ----- | ----------- | ----------- | ----------- | ----- | ------ |
|     | i     | i i i       | ij j i      | i 0 i       | i i i |        |
j∈Ni
or
|     |     |     | ce WTϕ(x) |     |     |        |
| --- | --- | --- | --------- | --- | --- | ------ |
|     |     |     | u         |     |     | (8.27) |
= − ˆ
with control gains c>0. Let local node NN tuning laws be given by

|        |                | W˙ˆi     | F ϕ e Tp (d          | b ) κF W                  |     | (8.28) |
| ------ | -------------- | -------- | -------------------- | ------------------------- | --- | ------ |
|        |                |          | i i i i i            | i i ˆi                    |     |        |
|        |                | =−       |                      | + −                       |     |        |
| with F | (cid:29) I , I |  the ν ν |                      | >0 and κ>0 scalar tuning  |     |        |
|        | i i νi         | νi i     | i identity matrix, Π |                           |     |        |
|        | =              | ×        |                      | i                         |     |        |
gains, and p >0 defined in Lemma 8.2. Select κ= 1cσ(Q) and the control gain
|     | i   |     |     | 2   |     |     |
| --- | --- | --- | --- | --- | --- | --- |
c so that
|     |     | cσ(Q)> | 1φσ(P)σ(A) |     |     | (8.29) |
| --- | --- | ------ | ---------- | --- | --- | ------ |
M
2
with P > 0, Q > 0 the matrices in Lemma 8.2 and A the graph adjacency matrix. Then
there exist numbers of neurons ν,i=1,N such that for ν >ν,∀i the overall local
|     |     |     | i   | i i |     |     |
| --- | --- | --- | --- | --- | --- | --- |
cooperative error vector e(t) and the NN weight estimation errors W
 are UUB,
with practical bounds given by (8.47) and (8.48), respectively. Therefore, the con-
trol node trajectory x (t) is cooperative UUB and all nodes synchronize close to
0
x (t). Moreover, the bounds on local consensus errors (8.4) can be made small by
0
increasing the control gains c.
Proof
Part A. We claim that for a fixed ε >0, there exist numbers of neurons ν ,i 1,N
|     |     |     | M   |     |     | i   |
| --- | --- | --- | --- | --- | --- | --- |
¯ =
such that for ν >ν ,∀i the NN approximation error is bounded by  ε ε M. The
|     | i   | i   |     |     | (cid:31) (cid:31)≤ |     |
| --- | --- | --- | --- | --- | ------------------ | --- |
claim is proven in Part b of the Proof 8.1. Consider now the Lyapunov function
candidate

|     |     |     | 1 1      |             |     |        |
| --- | --- | --- | -------- | ----------- | --- | ------ |
|     |     | V = | eTPe+ tr | { WTF−1W} |     | (8.30) |
|     |     |     | 2 2      |             |     |        |

244 8 Cooperative Adaptive Control for Systems with First-Order Nonlinear Dynamics
with e(t) the vector of local neighborhood cooperative errors (8.4),
0<P= PT ∈RN×N the diagonal matrix defined in (8.24), and F-1 a block diagonal
matrix defined in terms of F =diag{F}. Then,
i
V(cid:31) =eTPe(cid:31)+tr
{ W(cid:30)TF−1W(cid:30)(cid:31)}
(8.31)
and from (8.22)
V
˙ =−
eTP(L
+
B)[W
˜
Tϕ(x)
+
ce
+
ε
+
w
−
f(x
0
,t)]
+
tr W
˜
TF
−
1W˙˜
−
(cid:31) ((cid:30)8.32)
V(cid:28) =-ceTP(L+B)e-eTP(L+B){ ε+w- f(x ,t) }
0
-eTP(L+B)W(cid:27)Tϕ(x)+tr { W(cid:27)TF-1W (cid:28)(cid:27) }
(8.33)
V(cid:28) =-ceTP(L+B)e-eTP(L+B){ ε+w- f(x ,t) }
0
+tr { W(cid:27)T ( F-1W (cid:28)(cid:27) -ϕeTP(L+B) )} (8.34)
V(cid:28) =-ceTP(L+B)e-eTP(L+B){ ε+w- f(x ,t) }
0
+tr { W(cid:27)T ( F-1W (cid:28)(cid:27) -ϕeTP(D+B-A) )} (8.35)
Since L is irreducible and B has at least one diagonal entry b >0, then (L+B) is a
i
nonsingular M-matrix. Defining therefore Q according to (8.25) one has
V(cid:28) =- 1 ceTQe-eTP(L+B){ ε+w- f(x ,t) }
2 0
+tr { W(cid:27)T ( F-1W (cid:28)(cid:27) -ϕeTP(D+B) )} +tr { W(cid:27)TϕeTPA } (8.36)
A
Si
d
n
o
c
p
e
t
P
n o
a
w
nd
t h
(
e
D
N
+
N
B
w
)
e
a
i
r
g
e
h
d
t
i
t
a
u
g
n
o
i
n
n
a
g
l
l
a
a
n
w
d
(
W
8 (cid:31)(cid:30) .2 8
h
)
a
o
s
r
t h
W
e
˙˜
f
i
o
=
rm
F
i
i
n
ϕ
(
i e
8
i T
.1 p
9
i
)
(
,
d
o
i
n
+
e h
b
a
i )
s
+ κF i W ˆi.
V(cid:28) =- 1 ceTQe-eTP(L+B){ ε+w(t)- f(x ,t) }
2 0
+κtr { W(cid:27)T(W -W(cid:27)) } +tr { W(cid:27)TϕeTPA } (8.37)
Therefore, for fixed ε M >0
1
V(cid:28) ≤- cσ(Q) e 2+ eσ(P)σ(L+B)(ε +w +F )
2 M M M
+κW W(cid:27) -κW(cid:27) 2 + W(cid:27) eφσ(P)σ(A) (8.38)
M F F F M

8.2 Adaptive Design and Distributed Tuning Law 245
Then
 1cσ(Q) -1φ σ(P)σ(A) e 
V(cid:28) ≤ e W(cid:27)   2 2 M  
 F  -1 2 φ M σ(P)σ(A) κ   W(cid:27) F  
 e 
+[B σ(P)σ(L+B) κW ] 
M M W(cid:27)

 F
with B M ε M w M F M. Write this as
≡ + +
V ≤−zTRz+rTz (8.39)
Then V ≤0 if R is positive definite and
r
z > (8.40)
σ(R)
According to (8.30) one has
1 σ(P) e 2 + 1 W(cid:27) 2 ≤V ≤ 1 σ(P) e 2 + 1 W(cid:27) 2 (8.41)
2 2Π F 2 2Π F
max min
σ(P) 0 
 e 
1  e W(cid:27)  1   ≤V ≤
2 F 0  W(cid:27) 
 Π
max
  F
σ(P) 0 
 e 
1  e W(cid:27)  1   
2 F 0  W(cid:27) 
 Π
min
  F
(8.42)
with Π ,Π the minimum and maximum values of Π. Define variables to
min max i
write 1zTSz≤V ≤ 1zTSz. Then
2 2
1 1
σ(S) z 2 ≤V ≤ σ(S) z 2 (8.43)
2 2
Therefore,
1σ(S) r 2
V > (8.44)
2 σ2(R)

246 8  Cooperative Adaptive Control for Systems with First-Order Nonlinear Dynamics
implies (8.40).
One can write the minimum singular values of R as

|     | 1  |          |  1 |           |  1          |        |
| --- | --- | -------- | ---- | --------- | ------------ | ------ |
|     |    | cσ(Q)+κ | -   | cσ(Q)-κ+ | ϕ2σ2(P)σ2(A) |        |
|     | 2  |          |  2 |           |  M          |        |
|     |     |          |      |           | 4            | (8.45) |
σ(R)=
2
| To obtain a cleaner form for σ(R), select κ= |     |     |     |     | 1cσ(Q). Then |     |
| -------------------------------------------- | --- | --- | --- | --- | ------------ | --- |
2

1
|     |     |       | cσ(Q)- | ϕ   | σ(P)σ(A) |        |
| --- | --- | ----- | ------ | --- | -------- | ------ |
|     |     |       |        | M   |          | (8.46) |
|     |     | σ(R)= |        | 2   |          |        |
2
which is positive under condition (8.29). Therefore, z(t) is UUB [5],[7].
In view of the fact that, for any vector z, one has  z ≥ z ≥≥ z , suffi-
|     |     |     |     |     | 1 2 | ∞   |
| --- | --- | --- | --- | --- | --- | --- |
cient conditions for (8.40) are

B σ(P)σ(L+B)+κW
|     |     |     | M   |     | M   |        |
| --- | --- | --- | --- | --- | --- | ------ |
|     |     | e   | >   |     |     | (8.47) |
σ(R)
or
|     |     |     | σ(P)σ(L+B)+κW |     |     |     |
| --- | --- | --- | ------------- | --- | --- | --- |
B
|     |     | W(cid:27) | > M |     | M   | (8.48) |
| --- | --- | --------- | --- | --- | --- | ------ |
σ(R)
Now Lemma 8.1 shows that the consensus errors δ(t) are UUB. Then  x (t) is
0
cooperative UUB. Note that increasing gain c decreases the bound in (8.47).
Part B: According to (8.39) V σ(R) z 2 r z  and according to (8.43)
˙
|                    |     |     | ≤− −               | (cid:28) (cid:28) | +(cid:28) (cid:28)(cid:28) (cid:28) |        |
| ------------------ | --- | --- | ------------------ | ----------------- | ----------------------------------- | ------ |
|                    |     |     |                    | β√V               |                                     |        |
|                    |     |     | V                  | αV                |                                     | (8.49) |
|                    |     |     | ˙ ≤−               | +                 |                                     |        |
| with α≡2σ(R)/σ(S), |     | β≡  | 2 r / σ(S). Thence |                   |                                     |        |
β β
|     |      | V(0)e-αt/2+ |     | (1-e-αt/2)≤ |       |     |
| --- | ---- | ----------- | --- | ----------- | ----- | --- |
|     | V(t) | ≤           |     |             | V(0)+ |     |
α α
Using (8.43) one has
|     |      |        | σ(S) |          | 2 σ(S) r       |     |
| --- | ---- | ------ | ---- | -------- | -------------- | --- |
|     | e(t) | ≤ z(t) | ≤    | e(0) 2 + | W(cid:27)(0) + |     |
|     |      |        | σ(S) |          | F σ(S)σ(R)     |     |

8.2 Adaptive Design and Distributed Tuning Law 247
Then (8.6) shows that
1
x(t) ≤ e(t) + N x (t)
σ(L+B) 0
x(t) ≤ 1   σ(S) e(0) 2 + W(cid:27)(0) 2 + σ(S) r  + NX ≡r
σ(L+B) σ(S) F σ(S)σ(R) 0 0
(8.50)
where r ≤B σ(P)σ(L+B)+κW . Therefore, the state is contained for all
M M
times t≥0 in a compact set Ω ={x(t)| x(t) ≤r}. According to the Weierstrass
0 0
approximation theorem, given any NN approximation error bound ε M there exist
numbers of neurons ν ,i 1,N such that ν >ν , i implies sup ε(x) <ε .
□ ¯ i = i ¯ i ∀ x ∈ (cid:30)(cid:30) (cid:30) M
Discussion on NN Adaptive Control Proofs for Cooperative Systems If either
(8.47) or (8.48) holds, the Lyapunov derivative is negative and V decreases. There-
fore, these provide practical bounds for the neighborhood synchronization error and
the NN weight estimation error, respectively. Part a of the Proof 8.1 contains the
new material relevant to cooperative control of distributed systems. Part b of the
Proof 8.1 is standard in the neural adaptive control literature (see e.g. [7]). Note
that the set defined by (8.50) depends on the initial errors and the graph structural
properties. Therefore, proper accommodation of large initial errors requires a larger
number of neurons in the NN. The proof of Theorem 8.1 also reveals that, for a
given number of neurons, the admissible initial condition set is bounded [7].
Lyapunov Functions for Distributed Cooperative Control Design It is impor-
tant to select the Lyapunov function candidate V in (8.30) in terms of locally avail-
able variables at each node, e.g. the local neighborhood synchronization error e(t)
in (8.4) and (8.6). It is also essential to select the kernel matrix P to depend on the
graph topology as in Lemma 8.2. This means that any local control signals v(t) and
i
NN tuning laws developed in the proof of Theorem 8.1 are distributed and hence
implementable at each node using information only about the node’s state and those
of its neighbors. The use of the Frobenius norm in the Lyapunov function is also
instrumental, since it gives rise to Frobenius inner products in the proof of Theorem
8.1 that only depend on trace terms, where only the diagonal terms are important.
In fact, the Frobenius norm is ideally suited for the design of distributed protocols.
Equation (8.24) shows that P in (8.30) is chosen diagonal. This is important in
allowing selection of the NN tuning law (8.28) that leads to expression (8.37).
The result of this Lyapunov design is the local node NN tuning law (8.28) which
depends on the local cooperative error e(t). By contrast, standard NN tuning laws
i
[7] depend on a global tracking error, equivalent to the disagreement error vector
δ=(x-x ), which is not available at each node. Note that (8.28) is a distributed
0
version of the sigma-mod tuning law of P. Ioannou.
The parameters p in (8.28) are computed as in Lemma 8.2, which requires
i
global information of the graph. As such, they are not known locally at the nodes.

248 8 Cooperative Adaptive Control for Systems with First-Order Nonlinear Dynamics
However, NN tuning parameters f >0 are arbitrary, so that p f >0 can be arbi-
i i i
trary.
Each node maintains a local NN to provide estimates of its nonlinear dynamics.
The local nature of the NNs, as reflected in the distributed tuning protocols (8.28),
means that the number of neurons ν i at each node can be selected fairly small (see
the Simulation Examples). It is not necessary to select a large centralized NN to ap-
proximate the full global vector of nonlinearities f(x) in (8.18). The total number
N
of neurons in all the neural networks in the graph is ν ν.
i
=
i 1
=
The unknown dynamics of the control node f(x ,t) (cid:31)in (8.5) (which could be,
0
e.g., motion velocity) are treated as a disturbance to be rejected. The proof of The-
orem 8.1 shows that even though these dynamics are unknown, synchronization
of all nodes to the generally time-varying control node state x (t) is guaranteed,
0
within a small error. The simulations corroborate this. The control motion dynam-
ics bound F in Assumption 8.1 appears in the term B appearing in the UUB error
M M
bounds (8.47), (8.48). As F becomes smaller, the bounds decrease.
M
Note that the node control gains c are similar to the pinning gain parameters
defined in [13]. Note from (8.45) that increasing these gains results in a smaller
synchronization error bound (8.47).
Corollary 8.1 Given the setup in Theorem 8.1, suppose the NN estimation errors
in (8.15) are equal to zero. Then under the protocol (8.26), the local neighborhood
errors converge to the residual set defined by
σ(P)σ(L+B)
e ≥2B (8.51)
M cσ(Q)
with B =d +F , the sum of the disturbance bound and the bound on the consen-
M M M
sus variable (control node) dynamics (Assumption 8.1) and P, Q defined in Lemma
8.2. Moreover, the synchronization error norm e(t) convergences to this set expo-
nentially as e(0) e αt/2 with a convergence rate
−
(cid:31) (cid:31)
σ(Q)
α=c
σ(P) (8.52)
The speed of synchronization can be increased by increasing the control gains c in
protocol (8.26).
Proof If the NN estimation errors ε i in (8.15) are zero, then according to the proof
of Theorem 8.1 one has
V = 1eTPe
2
V(cid:28) ≤-1cσ(Q) e 2 + eσ(P)σ(L+ P)B
2 M

8.3  Relation of Error Bounds to Graph Structural Properties 249
which is negative if (8.51) holds. One has for large  e(t) , approximately
|     |     | V = 1eTPe |     |     |     |
| --- | --- | --------- | --- | --- | --- |
2
|     |     | 1cσ(Q) | 2                 |     |     |
| --- | --- | ------ | ----------------- | --- | --- |
|     |     | V      | e                 |     |     |
|     |     | ˙ ≤−2  | (cid:28) (cid:28) |     |     |
−
So that using standard techniques one has
|     |     | V   | αV  |     |     |
| --- | --- | --- | --- | --- | --- |
˙
≤−
with α given by (8.52). Therefore, V(t) V(0)e αt and the errors converge at the
−
|            | αt/2.    |     | ≤   |     |     |
| ---------- | -------- | --- | --- | --- | --- |
| rate  e(0) | e −      |     |     |     | □   |
| (cid:31)   | (cid:31) |     |     |     |     |
According to this corollary and Lemma 8.1, the residual global disagreement vector
error is practically bounded according to the quantity

σ(P)
|     |     | δ ≥2B |     |     | (8.53) |
| --- | --- | ----- | --- | --- | ------ |
M
cσ(Q)
Therefore, the error bounds and the rate of convergence (8.52) are related in a recip-
rocal manner.
Remark 8.4 If the node states are vectors x ∈Rn and x ∈Rn, the control proto-
|     |     |     | i   | 0   |     |
| --- | --- | --- | --- | --- | --- |
cols (8.26) and the error bounds given by (8.47) or (8.48) will remain unaltered. The
| NN weight tuning protocols will then be given by  |     |     |     |     | ▋   |
| ------------------------------------------------- | --- | --- | --- | --- | --- |

|     | W˙ˆi | F ϕ e T(p (d | b ) I ) | κF W | (8.54) |
| --- | ---- | ------------ | ------- | ---- | ------ |
|     |      | i i i i i    | i n     | i ˆi |        |
|     | =−   |              | + ⊗ −   |      |        |
Remark 8.5 It is easy to extend the Theorem 8.1 to the case where the digraph only
| contains a spanning tree using the Frobenius form [10].  |     |     |     |     | ▋   |
| -------------------------------------------------------- | --- | --- | --- | --- | --- |
8.3   Relation of Error Bounds to Graph Structural
Properties
According to the bounds (8.47), (8.48), (8.51) both the synchronization error and
the NN weight estimation error increase with the maximum singular values σ(A),
σ(L+B), and σ(P). It is desired to obtain bounds on these singular values in terms
of graph properties. Recall that  d a  is the (weighted) in-degree of node
|     |     | i = | ij             |     |     |
| --- | --- | --- | -------------- | --- | --- |
|     |     | j N | i              |     |     |
|     |     | ∈   | trix A, and do | =∑a |     |
i, that is, the ith row sum of adjacency  m(cid:31) a  is the (weighted)
|     |     |     |     | i ji |     |
| --- | --- | --- | --- | ---- | --- |
j
out-degree of node i, that is the i th column sum of A. It is direct to obtain upper
bounds on these singular values in terms of graph properties. Recalling several re-
sults from [1], one can easily show the following.

250 8  Cooperative Adaptive Control for Systems with First-Order Nonlinear Dynamics
Lemma 8.3 Bounds on Maximum Singular Values of A and (L + B)
N
|     | σ(A)≤∑d ≡vol(G) |     |     |
| --- | --------------- | --- | --- |
i
i=1
|     | σ(A)≤ max(d | )×max(do) |     |
| --- | ----------- | --------- | --- |
|     | i           | i i i     |     |
N
| σ(L+B)≤∑(b | +d +do) |     |     |
| ---------- | ------- | --- | --- |
|            | i i     | i   |     |
i-1
+do)×max(b
| σ(L+B)≤ | max(b +d |         | +2d ) |
| ------- | -------- | ------- | ----- |
|         | i i      | i i i i | i     |
These results show that the residual synchronization error is bounded above in
terms of the graph complexity expressed in terms of graph volumes (e.g. the sum of
in-degrees) and maximum degree sums.
Note from Lemma 8.2 that the singular values of P and Q are related through the
Lyapunov equation (8.25) and depend on the singular values of L + B. More work
needs to be done to investigate these interrelationships and simplify the bounds
(8.47), (8.48), and (8.51).
8.4  Simulation Examples
This section shows the effectiveness of the distributed adaptive protocol of Theo-
rem 8.1 on several fronts. First, it is compared to standard pinning control [8],[13].
Next, it is shown that the protocol effectively enforces synchronization, using only
a few NN nodes at each node, for unknown non-linear control node dynamics, un-
known non-linear node dynamics, and unknown disturbances at each node.
For this set of simulations, consider the 5-node strongly connected digraph struc-
ture in Fig. 8.1 with a leader node connected to node 3. The edge weights and the
pinning gain in (8.4) were taken equal to 1.
a. Nonlinear Node Dynamics and Disturbances
For the graph structure shown, consider the following node dynamics

|     | x = x3+u  | +d    |        |
| --- | ---------- | ----- | ------ |
|     | 1 1        | 1 1   |        |
|     | x = x2+u  | +d    |        |
|     | 2 2        | 2 2   |        |
|     | x = x4+u  | +d    |        |
|     | 3 3        | 3 3   |        |
|     | x = x     | +u +d |        |
|     | 4 4        | 4 4   |        |
|     | x = x5++u | +d    | (8.55) |
|     | 5 5        | 5 5   |        |
which has nonlinearities and disturbances at each node, all assumed unknown.
Random disturbances with normal distributions are given at the i th node by
d t ). (We use MATLAB symbology.)
i =randn(1)×cos(

8.4 Simulation Examples 251
Fig. 8.1 Five node strongly
connected digraph with one
leader node
3
2
1
0
0 0.05 0.1 0.15 0.2 0.25 0.3
Time(t)
Consider now the control protocol of Theorem 8.1. Take the desired consensus
value of x =2, i.e. x = f(x ,t)=0. The following parameters are used in the
0 0 0
simulation. Control gain c=300, number of neurons at each node: ν =3, κ 0.8,
i =
and F =1500. Figure 8.2 shows how the agent states reach consensus with bound-
i
ed input commands. Figure 8.3 plots the disagreement vector δ=(x-x ) and the
0
NN estimation errors f (x)- fˆ(x). Figure 8.4 shows the NN weights. The initial
i i i i
behavior of NN weight resulted during the search for appropriate NN weights for
i ∀ixsetatS
State dynamics and input
300
200
100
0
−100
−200
−300
0 0.05 0.1 0.15 0.2 0.25 0.3
Time(t)
i ∀iutupnI
Fig. 8.2 Agents’ state dynamics and corresponding input commands

252 8 Cooperative Adaptive Control for Systems with First-Order Nonlinear Dynamics
Error Plot
1
0
−1
−2
0 0.05 0.1 0.15 0.2 0.25 0.3
Time(t)
i ∀iδ
600
400
200
0
−200
0 0.05 0.1 0.15 0.2 0.25 0.3
Time(t)
i ∀
)x(i
ˆf-)x(if
Fig. 8.3 State consensus errors and NN estimation errors
100
80
60
40
20
0
−20
−40
−60
−80
−100
0 0.05 0.1 0.15 0.2 0.25 0.3
Time(t)
i
Wthgiew
NN
ii ∀
Fig. 8.4 NN weights are stable and bounded after initial search mode

8.4 Simulation Examples 253
Table 8.1 Steady-state
values of NN weights closely f i (x) f ˆi (x) = Est(f i (x))
match the actual agent 8 7.9835
dynamics nonlinearities 4 3.8701
evaluated at consensus value 16 15.8063
of x =2 2 1.8051
0
32 31.5649
fˆ(x) estimation. The steady-state consensus error is approximately zero. Table 8.1
i i
shows that at steady state, the NNs closely estimate the nonlinearities. (That is, the
nonlinearities in (8.55) evaluated at the consensus value of x =2. Recall there are
0
small random disturbances w(t)present.)
i
b. Synchronization of Second-Order Multi-Input Dynamics
Consider the node dynamics for node i given by the second-order inertial system
dynamics
q(cid:28) =q +u
1i 2i 1i
q(cid:28) = J-1u -Brq -M gl sin(q ) (8.56)
2i i  2i i 2i i i 1i 
where q i = [q 1i ,q 2i ]T ∈ R2 is the state vector, J i is the inertia, B i r is the damping
coefficient, M is total mass, g is gravitational acceleration, and l is a length pa-
i i
rameter. J ,Br,M ,l are considered unknown and may be different for each node.
i i i i
Note that here we take a control input into each state component of each agent,
so it is not the same as second-order consensus, where u =0. Second-order con-
1i
sensus using adaptive control is considered in Chap. 9.
The desired target state trajectory is generated by the inertial leader node
dynamics
m q +d q +k q =u (8.57)
0 0 0 0 o 0 0
Select the feedback linearization input for the leader
u [K (q sin(βt)) K (q βcos(βt))] d q k q β2m sin(βt)
0 1 0 2 0 0 0 0 0 0
=− − + ˙ − + ˙ + +
(8.58)
for a constant β>0. Then, the target motion q (t) tracks the desired reference
0
trajectory sin(βt).
The cooperative adaptive control law of Theorem 8.1 was simulated. Since the
agent states are of second order, the Kronecker product with I was used as in (8.54).
2
We used three neurons per node.
Figure 8.5 verifies that both components (i.e. position and velocity) of the sec-
ond-order node states synchronize to the leader trajectory. It also shows the control
inputs. Figure 8.6 shows the state consensus error and NN estimation errors. The

254 8 Cooperative Adaptive Control for Systems with First-Order Nonlinear Dynamics
Error Plot
1.5
1
0.5
0
−0.5
0 0.05 0.1 0.15 0.2
Time(t)
i ∀iδ
50
0
−50
−100
0 0.05 0.1 0.15 0.2
Time(t)
i ∀
)x(i
ˆf-)x(if
2
1
0
−1
0 0.05 0.1 0.15 0.2
Time(t)
Fig. 8.6 Consensus errors and NN estimation errors
i
xsetatS
∀i
State dynamics and input
200
0
−200
−400
0 0.05 0.1 0.15 0.2
Time(t)
i ∀iutupnI
Fig. 8.5 State dynamics and control inputs

255
Fig. 8.7 State dynamics and estimated state dynamics
100
80
60
40
20
0
−20
−40
0 0.05 0.1 0.15 0.2
Time(t)
i
WthgiewNN
ii
∀
8.4 Simulation Examples
Fig. 8.8 NN weight dynamics: initial searching and stable mode

256 8 Cooperative Adaptive Control for Systems with First-Order Nonlinear Dynamics
2
1.5
1
0.5
0
−0.5
−1
−1.5
−1.5 −1 −0.5 0 0.5 1 1.5
xi(t)
∀
i
dynamics of the actual and estimated f(x) are shown in Fig. 8.7. In contrast to the
first-order dynamics case of Fig. 8.4, for these second-order systems there are two
sets of NN weights as shown in Fig. 8.8. Figure 8.9 shows the phase-plane plot for
all the nodes along with the target node. It can be seen that the phase-plane trajec-
tories of all nodes, started with different initial conditions, synchronize to the target
node phase plane trajectory, finally forming a Lissajous pattern.
References
1. Bernstein DS (2005) Matrix Mathematics. Princeton University Press, NJ
2. Das A, Lewis FL (2010) Distributed adaptive control for synchronization of unknown non-
linear networked systems. Automatica 46(12):2014–2021
3. K. Hornik, M. Stinchcombe, and H. White. 1989. Multilayer feedforward networks are uni-
versal approximators. Neural Netw. 2(5):359–366
4. Igelnik B, Pao YH (1995) Stochastic choice of basis functions in adaptive function approxima-
tion and the functional-link net. IEEE Trans Neural Netw 6(6):1320–1329
5. Khalil HK (2002) Nonlinear Systems, 3rd ed. Upper Saddle River. Prentice Hall, NJ
6. Khoo S, Xie L, Man Z (2009) Robust finite-time consensus tracking algorithm for multirobot
systems. IEEE Trans Mechatron 14(2):219–228
7. Lewis FL, Jagannathan S, Yesildirek A (1999) Neural Network Control of Robot manipulators
and nonlinear systems. Taylor and Francis, London
8. Li X, Wang X, Chen G (2004) Pinning a complex dynamical network to its equilibrium. IEEE
Trans Circ Syst 51(10):2074–2087
i ∀
)t(ix˙
All5nodestogetherwithleadernode
Fig. 8.9 Synchronized motion phase-plane plot

References 257
9. Olfati-Saber R, Murray RM (2004) Consensus problems in networks of agents with switch-
ing topology and time-delays. IEEE T Automat Contr 49(9):1520–1533
10. Qu Z (2009) Cooperative Control of Dynamical Systems: Applications to Autonomous Ve-
hicles. Springer-Verlag, New York
11. Rovithakis GA (2000) Robustness of a neural controller in the presence of additive and multi-
plicative external perturbations. In: Proc. IEEE Int. Symp. Intelligent Control, Patras, Greece,
pp. 7–12
12. Stone MH (1948) The generalized weierstrass approximation theorem. Math Mag 21(4/5):167–
184/237–254
13. Wang XF, Chen G (2002) Pinning control of scale-free dynamical networks. Physica A
310(3):521–531

Chapter 9
Cooperative Adaptive Control for Systems
with Second-Order Nonlinear Dynamics
In Chap. 8, we designed cooperative adaptive controllers for multi-agent systems
having first-order nonlinear dynamics. In this chapter, we study adaptive control for
cooperative multi-agent systems having second-order nonidentical nonlinear dy-
namics. The study of second-order and higher-order consensus is required to imple-
ment synchronization in most real-world applications such as formation control and
coordination among unmanned aerial vehicles (UAVs), where both position and
velocity must be controlled. Note that Lagrangian motion dynamics and robotic sys-
tems can be written in the form of second-order systems. Moreover, second-order
integrator consensus design (as opposed to first-order integrator node dynamics)
involves more details about the interaction between the system dynamics and con-
trol design problem and the graph structure as reflected in the Laplacian matrix. As
such, second-order consensus is interesting because there one must confront more
directly the interface between control systems and communication graph structure.
We are interested here in the second-order synchronization tracking problem
for heterogeneous nodes with nonidentical unknown nonlinear dynamics with un-
known disturbances. ‘Synchronization control’ means the objective of enforcing
all node trajectories to follow (in a ‘close-enough’ sense to be made precise) the
trajectory of a leader or control node. The communication structures considered are
general directed graphs with fixed topologies. Analysis of digraphs is significantly
more involved than for undirected graphs. The dynamics of the leader or command
node are also assumed nonlinear and unknown. A distributed adaptive control ap-
proach is taken, where cooperative adaptive controllers are designed at each node.
The challenge in cooperative adaptive control is to make sure that both the con-
trol protocols and the parameter tuning laws are distributed in terms of the allowed
graph topology. That is, they are allowed to depend only on locally available infor-
mation about the agent and its neighbors. We shall see in this chapter that the key
to the design of distributed adaptive tuning algorithms is the selection of suitable
Lyapunov functions that depend on the graph topology. This is closely connected
to the selection of global performance indices that depend on the graph topology
in Chap. 5. The basis for the selection of suitable graph-dependent Lyapunov func-
tions was laid in the discussion on the graph Laplacian potential in Chap. 7.
F. L. Lewis et al., Cooperative Control of Multi-Agent Systems, 259
Communications and Control Engineering, DOI 10.1007/978-1-4471-5574-4_9,
© Springer-Verlag London 2014

260 9  Cooperative Adaptive Control for Systems with Second-Order …
In Sect. 9.1, we lay the background for adaptive control design for second-order
multi-agent systems by defining local neighborhood position and velocity errors
that depend on local information in the graph and introducing a sliding error vari-
able. Neural network (NN) structures at each node are used to approximate the un-
known nonlinearities, and a suitable form is developed for a distributed cooperative
control protocol. These cooperative control protocols depend on certain unknown
parameters. In Sect. 9.2, we show how to tune these parameters using adaptive tun-
ing laws that only depend on locally available information at each node. In Sect. 9.3,
simulations are given to show the effectiveness of these distributed adaptive control
protocols in achieving synchronization for multi-agent systems with unknown het-
erogeneous dynamics and unknown disturbances.
The results of this chapter were first published in [2].
9.1   Sliding Variable Cooperative Control Formulation
and Error Dynamics
Consider a graph G=(V,E) with a nonempty finite set of N nodes V ={v,,v }
1 N
and a set of edges or arcs  E ⊆V ×V. We assume the graph is simple, e.g., no
repeated edges and  (v,v)∉E,∀i no self-loops. General directed graphs are
|     |     | i i |     |     |     |
| --- | --- | --- | --- | --- | --- |
considered.  Denote  the  adjacency  or  connectivity  matrix  as  A=[a ],  with
ij
a >0if (v ,v)∈E and a =0 otherwise. Note that a =0. The set of neighbors
| ij  | j i | ij  |     | ii  |     |
| --- | --- | --- | --- | --- | --- |
of a node v  is N ={v :(v ,v)∈E}, i.e., the set of nodes with arcs incoming to v.
|     | i   | j j i |     |     |     |
| --- | --- | ----- | --- | --- | --- |
|     | i   |       |     |     | i   |
Define the in-degree matrix as a diagonal matrix D=diag{d} with d = ∑ a
|     |     |     |     | i   | i ij |
| --- | --- | --- | --- | --- | ---- |
j∈Ni
the weighted in-degree of node i (i.e., i-th row sum of A). Define the graph Lapla-
D−A, which has all row sums equal to zero. Define do
| cian matrix as L= |     |     |     |     | =∑a ,  |
| ----------------- | --- | --- | --- | --- | ------ |
i ji
the (weighted) out-degree of node, that is the i-th column sum of A. j
9.1.1   Cooperative Tracking Problem for Synchronization
of Multi-Agent Systems
Consider second-order node dynamics defined for the i-th node in Brunovsky form
as
x1 x2
=
|     |     | i   | i   |     |     |
| --- | --- | --- | --- | --- | --- |
x2
|                      |      | =           | f (x)+u +w                              |     | (9.1) |
| -------------------- | ---- | ----------- | --------------------------------------- | --- | ----- |
|                      |      | i           | i i i i                                 |     |       |
|                      | =[x1 | x2]T ∈R2, u |                                         |     |       |
| where the state is x |      |             | (t)∈R is the control input, and w(t)∈R  |     |       |
|                      | i    | i i         | i                                       |     | i     |
is a disturbance acting upon each node. Note that each node may have its own
distinct nonlinear dynamics  f (x). Standard assumptions for existence of unique
i i

9.1  Sliding Variable Cooperative Control Formulation and Error Dynamics  261
solutions are made, e.g.,  f (x) either continuously differentiable or Lipschitz. The
i i
overall graph dynamics is
|     | x1 = x2 |          |     |     |       |
| --- | -------- | -------- | --- | --- | ----- |
|     | x2 =    | f(x)+u+w |     |     | (9.2) |

T
where  the  overall  (global)  velocity  vector  is  x2 =x2 x2(cid:31)x2  ∈RN,  the
|     |     |     |  1 | 2 N |     |
| --- | --- | --- | --- | ---- | --- |
T
global position vector is  x1 =x1 x1(cid:31)x1  ∈RN, the global state vector is x =
|     |  1 2 | N  |     |     |     |
| --- | ----- | --- | --- | --- | --- |
x=(x1,x2)T, and the global dynamics vector is f T RN.
|     |     | (x) f 1 | (x 1 ) f 2 | (x 2 ) f N | (x N ) |
| --- | --- | ------- | ---------- | ---------- | ------ |
|     |     | =       |            | ···        | ∈      |
The global control input is u = [u  u  . . . u ]T ∈ RN , and the global disturbance is
|     | 1 2 | N (cid:31) |     |     | (cid:30) |
| --- | --- | ---------- | --- | --- | -------- |
]T
w=[w w (cid:31)w ∈RN.
1 2 N
The state x =[x1 x2]T ∈R2 of a leader or control node satisfies the (generally
0 0 0
nonautonomous) dynamics in Brunovsky form
|     | x1 | x2  |     |     |     |
| --- | --- | --- | --- | --- | --- |
=
0 0
x2
|     |     | = f (x ,t) |     |     | (9.3) |
| --- | --- | ---------- | --- | --- | ----- |
|     | 0   | 0 0        |     |     |       |
This can be regarded as a command or reference generator. A special case is the
standard constant consensus value with  x1 =0 and  x2 absent. Here, we assume
|     |     | 0   | 0   |     |     |
| --- | --- | --- | --- | --- | --- |
that the control node can have a time-varying (nonautonomous) flow field. This
command generator captures a wide variety of possible reference trajectories in-
cluding unit step position commands, unit ramp velocity commands, sinusoidal tra-
jectories, and more.
The synchronization tracking control problem confronted herein is as follows:
Design control protocols u  for all the nodes in G to synchronize to the state of the
i
control node, i.e., one requires xk(t)→xk(t),k
=1,2,∀i.
|     | i   | 0   |     |     |     |
| --- | --- | --- | --- | --- | --- |
It is assumed that the dynamics  f (x ,t) of the control node is unknown to any
0 0
of the nodes in G. It is assumed further that both the node nonlinearities  (·) and
f
i
the node disturbances  w(t) are unknown. Thus, the synchronization protocols
i
must be robust to unmodeled dynamics and unknown disturbances.
If the states xk
 are not scalars, this analysis carries over using standard methods
i
involving the Kronecker product term [1]. See Remark 8.1 in Chap. 8.
We shall proceed by analyzing the error dynamics of a suitable defined coopera-
tive control error.
Definition 9.1 The local neighborhood tracking synchronization errors for node i
are defined as [7], the local position error
( −x1)
| e1 = | ∑a x1 | +b ( x1 | −x1) |     | (9.4) |
| ---- | ----- | ------- | ---- | --- | ----- |
| i    | ij    | j i i   | 0 i  |     |       |

j∈Ni

262 9  Cooperative Adaptive Control for Systems with Second-Order …
and the local velocity error
|     |         | ( −x2) | ( −x2)  |       |
| --- | ------- | ------ | ------- | ----- |
|     | e2 = ∑a | x2     | +b x2   | (9.5) |
|     | i       | ij j   | i i 0 i |       |
j∈Ni
with pinning gains b ≥0, and b >0 for at least one i. Then, b ≠0 if and only if
|     | i   | i   | i   |     |
| --- | --- | --- | --- | --- |
there exist an arc from the control node to the i-th node in G. We refer to the nodes
| i for which b ≠0 as the pinned or controlled nodes. |     |     |     |     |
| --------------------------------------------------- | --- | --- | --- | --- |
i
Note that (9.4) and (9.5) represent all the information that is available to any node i
for control purposes on a distributed graph topology.
9.1.2  Sliding Mode Tracking Error
Define the consensus disagreement error vector
T T
|     | δ=δ1 δ2 | =x1−1x1 | x2 −1x2   | (9.6) |
| --- | --------- | -------- | ---------- | ----- |
|     |          |        | 0 0       |       |
with 1∈RN being the vector of ones. From (9.4), the global position error vector
for network G is given by
|     | e1     | ( x1 −1x1) | B)d1   |       |
| --- | ------ | ---------- | ------ | ----- |
|     | = −(L+ | B)         | = −(L+ | (9.7) |
0
and the global velocity error is
( −1x2)
|     | e2 = −(L+ | B) x2 | = −(L+ B)d2  | (9.8) |
| --- | --------- | ----- | ------------ | ----- |
0
where B = diag{b} is the diagonal matrix of pinning gains, and
i
| ek ∈RN,k =1,2,∀i. |     |     |     |     |
| ----------------- | --- | --- | --- | --- |
i
We take the communication digraph as strongly connected. Then, if b ≠0 for at
i
least one i then (L+B) is an irreducibly diagonally dominant M-matrix and hence
nonsingular [10]. It has all poles in the open right-half s-plane. A milder condition
that guarantees  (L+B) as nonsingular is the existence of a spanning tree with
b ≠0 for at least one root node i.
i
Then, the form of (9.7) and (9.8) directly yields the next result.
Lemma 9.1 Let the graph be strongly connected and B≠0. Then
|     | dk ≤ | ek /s(L+ | B),      k =1, 2  | (9.9) |
| --- | ---- | -------- | ----------------- | ----- |
with σ(L+B) the minimum singular value of (L+B), and e=0 if and only if the
nodes synchronize, that is,
|     | xk(t)= | xk(t),k |         |        |
| --- | ------ | ------- | ------- | ------ |
|     |        |         | =1,2,∀i | (9.10) |
|     | i      | 0       |         |        |

9.1  Sliding Variable Cooperative Control Formulation and Error Dynamics  263
This lemma shows that if the local neighborhood position and velocity tracking
errors e1, e2 are small, then the consensus disagreement errors are small and synchro-
nization is reached. Therefore, in the following we shall focus on making e1, e2  small.
9.1.3  Synchronization Control Design and Error Dynamics
Differentiating (9.7) and (9.8) yields
|     |     | e(cid:28)1 |         | ( x2 -1x2) |     |        |
| --- | --- | ---------- | ------- | ---------- | --- | ------ |
|     |     |            | =-(L+B) |            |     | (9.11) |
0
and
|     |     |                    |     | (              | )        |        |
| --- | --- | ------------------ | --- | -------------- | -------- | ------ |
|     |     | e(cid:28)2 =-(L+B) |     | x(cid:28)2 -1f | (x ,t)   | (9.12) |
0 0
| Note that e1 | =e2. Define a sliding mode error for node i as |     |           |       |     |        |
| ------------- | ---------------------------------------------- | --- | --------- | ----- | --- | ------ |
|               |                                                |     | r =e2+λe1 |       |     | (9.13) |
|               |                                                |     | i         | i i i |     |        |
or written globally as
=e2+Λe1
|     |     |     | r   |     |     | (9.14) |
| --- | --- | --- | --- | --- | --- | ------ |
where Λ=diag(λ)>0. The next result follows directly.
i
Lemma 9.2 The velocity error is bounded according to
|     |     |     | e2 ≤ r | +σ(Λ) | e1   | (9.15) |
| --- | --- | --- | ------ | ----- | ---- | ------ |
Now differentiating r one obtains the error dynamics
|     |                  | (          |        | )           | ( -1x2) |     |
| --- | ---------------- | ---------- | ------ | ----------- | ------- | --- |
|     | r(cid:28)=-(L+B) | x(cid:28)2 | -1f (x | ,t) -Λ(L+B) | x2      |     |
0 0 0
|     | =-(L+B)(f(x)+u+w)+(L+B)1f |     |     |     | (x ,t)+Λe2  | (9.16) |
| --- | ------------------------- | --- | --- | --- | ----------- | ------ |
0 0
Following the techniques in [4, 5, 9], we assume that the unknown nonlinearities in
(9.1) are smooth and thus can be approximated on a compact set S∈R by
|     |     |     | f (x )=WTϕ(x | )+ε   |     | (9.17) |
| --- | --- | --- | ------------ | ----- | --- | ------ |
|     |     |     | i i          | i i i | i   |        |
with  ϕ (x ) Rηi a suitable basis set of η i functions at each node, with η i be-
| i i                             |     |     |                                              |     |     |     |
| ------------------------------- | --- | --- | -------------------------------------------- | --- | --- | --- |
|                                 | ∈   |     | Rηi being a set of unknown coefficients. Ac- |     |     |     |
| ing the number of neurons and W |     |     | i                                            |     |     |     |
∈
cording to the Weierstrass higher-order approximation theorem [11], a polynomial
basis set suffices to approximate f (x ) as well as its derivatives, when they exist.
|     |     |     | i i |     |     |     |
| --- | --- | --- | --- | --- | --- | --- |
Moreover, the approximation error  ε i 0 uniformly as η i . According to
|     |     |     |     | →   | →∞  |     |
| --- | --- | --- | --- | --- | --- | --- |
the NN approximation literature [5], a variety of basis sets can be selected, includ-
Rηi is known as the NN activation
| ing sigmoids, Gaussians, etc. There,  |     |     | ϕ   | i (x i ) |     |     |
| ------------------------------------- | --- | --- | --- | -------- | --- | --- |
∈
fu n c t io n   v e c to r  a nd   W R η i  a s  t h e   N N   w e i gh t   m at rix .   T h e n  it i s  sh o w n   t h a t  ε   i s
|     |     | i   |     |     |     | i   |
| --- | --- | --- | --- | --- | --- | --- |
b o u n d e d   o n  a  c o m p a ct  s ∈ et.  T h e  i d e a l   ap p r ox i m a t i ng  w e i g h t s  ∈ η  in   ( 9 . 1 7 )  a r e
|     |     |     |     |     | W i R i |     |
| --- | --- | --- | --- | --- | ------- | --- |
assumed to be unknown. The intention is to select only a small number η of NN
i
neurons at each node (see Simulations).

264 9  Cooperative Adaptive Control for Systems with Second-Order …
Here, to avoid distractions from the main issues being introduced, we assume
a linear-in-the-parameters NN, i.e., the basis set of activation functions is fixed
and only the output weights are tuned. It is straightforward to use a two-layer NN
whereby the first- and second-layer weights are tuned. Then one has a nonlinear-in-
the-parameters NN and the basis set is automatically selected in the NN. Then, the
below development can easily be modified as in [9].
To compensate for unknown nonlinearities, each node will maintain a local NN
to keep track of the current estimates for the nonlinearities. The idea is to use the
information of the states from the neighbors of node i to evaluate the performance
of the current control protocol along with the current estimates of the nonlinear
functions. Therefore, select the local node’s approximation f ˆi (x i ) as
|     |     |     | fˆ(x | )=WˆTϕ(x | )     |     |     | (9.18) |
| --- | --- | --- | ---- | -------- | ----- | --- | --- | ------ |
|     |     |     | i    | i        | i i i |     |     |        |
where Wˆ ∈Rη  is a current estimate of the NN weights for node i, and η
|     | i   |     |     |     |     |     |     | i is the  |
| --- | --- | --- | --- | --- | --- | --- | --- | --------- |
i
number of NN neurons maintained at each node i. It will be shown in Theorem 9.1
how to select the estimates of the parameters W Rηi using the local neighbor-
ˆi
∈
hood synchronization errors (9.4, 9.5).
The global node nonlinearity  f(x) for graph G is now written as
|                |     |    | T   |          |           |                                              |                |        |
| -------------- | --- | --- | --- | -------- | ---------- | -------------------------------------------- | -------------- | ------ |
|                |     | W   |     |          |            | ϕ (x )                                      |  ε          |        |
|                |     |    | 1   |          |           | 1 1                                          | 1              |        |
|                |     |     |     |          |            |                                             |             |        |
|                |     |    | WT  |          |           | ϕ(x                                          | ) ε            |        |
|                |     |     |     | 2        |            |  2 2                                        |   2         |        |
| f(x)=WTϕ(x)+ε= |     |    |     |          |           |                                              |                | (9.19) |
|                |     |     |     | (cid:30) |            |  (cid:29)                                   | + (cid:29)  |        |
|                |     |    |     |          |           |                                              |                |        |
|                |     |     |     |          |            |                                             |             |        |
|                |     |    |     |          | (cid:30)  | (cid:29)                                     | (cid:29)       |        |
|                |     |     |     |          |            |                                             |             |        |
|                |     |    |     |          |           |                                             | )           |        |
|                |     |     |     |          | T        |  ϕ (x                                       |  ε          |        |
|                |     |   |     |          | W          | (cid:23) (cid:22)N(cid:21) (cid:22)N(cid:20) | N              |        |
N
ϕ(x)
| and the global estimate  |                | fˆ(x) as |      |     |          |                              |                   |        |
| ------------------------ | -------------- | -------- | ---- | --- | -------- | ---------------------------- | ----------------- | ------ |
|                          |                |          |  Wˆ | T   |          |                             |                   |        |
|                          |                |          |      |     |          | ϕ                           | (x )             |        |
|                          |                |          |     | 1   |          |                             | 1 1               |        |
|                          |                |          |      | WˆT |          |                             |                  |        |
|                          |                |          |     |     |          |  ϕ(x                        | )                 |        |
|                          |                |          |      | 2   |          |                             | 2 2              |        |
|                          | fˆ(x)=WˆTϕ(x)= |          |     |     |          |                             |                   |        |
|                          |                |          |      |     | (cid:30) |                             | (cid:29)         | (9.20) |
|                          |                |          |     |     |          |                            |                  |        |
|                          |                |          |     |     | (cid:30) |                            | (cid:29)         |        |
|                          |                |          |     |     |          |                            | )                |        |
|                          |                |          |      |     |          | Wˆ T  ϕ                   | (x               |        |
|                          |                |          |    |     |          | N (cid:23) (cid:22)N(cid:21) | (cid:22)N(cid:20) |        |
ϕ(x)
|     |     |     |     |     |     |     |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
Consider the control protocol
=-fˆ(x
|     |     |     | u   |     | )+µ(t) |     |     |        |
| --- | --- | --- | --- | --- | ------ | --- | --- | ------ |
|     |     |     | i   | i i | i      |     |     | (9.21) |
or in global form
u=-fˆ(x)+µ(t)
(9.22)

9.2 Cooperative Adaptive Design and Distributed Tuning Laws 265
with µ(t) being an auxiliary input for the i th node yet to be specified. Then using
i
(9.22) the global error dynamics (9.16) becomes
r(cid:28)=-(L+B)(f(cid:27)(x)+µ(t)+w)+(L+B)1f (x ,t)+Λe2 (9.23)
0 0
where
f(cid:27)(x)= f(x)- fˆ(x)=W(cid:27)ϕ(x)
is the function approximation error with the weight estimation errors defined as
W(cid:27) =diag ( W -Wˆ ,W -Wˆ ,(cid:31)(cid:31),W -Wˆ )T .
1 1 2 2 N N
9.2 Cooperative Adaptive Design and Distributed
Tuning Laws
It is now shown how to select the auxiliary controls µ(t) and tuning laws for the
i
NN weight parameters Wˆ ∈Rη i so as to guarantee that all nodes synchronize to
i
the desired control node signal, i.e., x (t)→x (t),∀i. Both the auxiliary controls
i 0
and tuning laws are only allowed to depend on information about node i and its
neighbors in the graph. It is assumed that the dynamics f(x ,t) of the control
0
node (which could represent its motion) are unknown to any of the nodes in G. It
is assumed further that the node nonlinearities f (x) and disturbances w(t) are
i i i
unknown.
The Lyapunov analysis technique approach of [8, 9], is used here, though there
are some complications arising from the fact that µ(t) and the NN weight tuning
i
laws must be implemented as distributed protocols. This entails a careful selection
of the Lyapunov function. The Lyapunov function must depend on the graph topol-
ogy properties. This is closely connected to the selection of global performance
indices that depend on the graph topology in Chap. 5. The basis for the selection
of suitable graph-dependent Lyapunov functions was laid in the discussion on the
graph Laplacian potential in Chap. 7.
The maximum and minimum singular values of a matrix M are denoted σ(M)
and σ(M), respectively. The Frobenius norm is M = tr{MTM} with tr{⋅} the
F
trace. The Frobenius inner product of two matrices is M ,M = tr{M TM }.
1 2 F 1 2
The following Fact gives two standard results used in neural adaptive control [9].
Fact 9.1 Let the nonlinearities f(x) in (9.2) be smooth on a compact set Ω⊂RN.
Then:
a. The NN estimation errorε(x) is bounded by ε ≤ε onΩ, with ε being a
M M
fixed bound [5, 9].

266 9  Cooperative Adaptive Control for Systems with Second-Order …
b. Weierstrass higher-order approximation theorem. Select the activation functi-
onsϕ(x) as a complete independent basis (e.g., polynomials). Then the NN esti-
mation errorε(x) converges uniformly to zero on Ω as η→∞,i=1,N. That
i
is,∀ξ>0 there existη,i=1,N  such that η>η,∀i implies sup ε(x) <ξ
|     |     |     |     | i   |     | i   | i   | x∈Ω |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
[11].
The following standard assumptions are required. Although the bounds mentioned
are assumed to exist, they are not used in the design and do not have to be known.
They appear in the error bounds in the proof of Theorem 9.1.
Assumption 9.1
a. The unknown disturbancew  is bounded for all i. Thus the overall disturbance
i
vector w is also bounded by  w ≤w  with w  being a fixed bound.
|                                    |     |     |     |     |     | M               | M    |     |     |
| ---------------------------------- | --- | --- | --- | --- | --- | --------------- | ---- | --- | --- |
| b. Unknown ideal NN weight matrixW |     |     |     |     |     |  is bounded by  | W ≤W | .   |     |
|                                    |     |     |     |     |     |                 | F    | M   |     |
c. NN activation functionsϕ are bounded by∀i, so that one can write for the ove-
i
|     | rall network that  |     | ϕ ≤φ | .   |     |     |     |     |     |
| --- | ------------------ | --- | ---- | --- | --- | --- | --- | --- | --- |
M
d. The  unknown  consensus  variable  dynamics f (x ,t)  are  bounded  so
0 0
|     | that  f | (x ,t) | ≤F ,∀t, respectively. |     |     |     |     |     |     |
| --- | ------- | ------ | --------------------- | --- | --- | --- | --- | --- | --- |
|     |         | 0 0    | M                     |     |     |     |     |     |     |
e. The target trajectory is bounded so that  x1(t) < X1, x2(t) < X2,∀t.
|     |     |     |     |     |     | 0   | 0 0 | 0   |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
The definition for robust practical stability, or uniform ultimate boundedness, is
standard and the following definitions extend it to multi-agent systems.
Definition 9.2 Any vector time function  y(t) is said to be uniformly ultimately
bounded (UUB) [9] if there exist a compact set Ω⊂RN so that ∀y(t )∈Ω there
0
exist a bound B  and a time t (B ,y(t )) such that  x(t)−y(t) ≤B ∀t≥t +t .
|     |     | m   |     | f   | m   | 0   |     | m   | 0 f |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
Definition  9.3 The  control  node  state  x (t)  is  said  to  be  cooperative  uni-
0
formly ultimately bounded (CUUB) if there exist a compact set  Ω⊂R so that
∀(x (t )−x (t )∈Ω there exist a bound B  and a time t (B ,x(t ),x (t )) such
|       | i 0    | 0 0 |            |     |      | m   | f m | 0   | 0 0 |
| ----- | ------ | --- | ---------- | --- | ---- | --- | --- | --- | --- |
| that  | x(t)−x | (t) | ≤B ∀i,∀t≥t |     | +t . |     |     |     |     |
|       | i      | 0   | m          |     | 0 f  |     |     |     |     |
The next key constructive result is needed. An M-matrix is a square matrix hav-
ing nonpositive off-diagonal elements and all principal minors nonnegative (see
Chap. 2 and [10]). The Laplacian matrix L is irreducible if and only if the digraph
is strongly connected. That is, L is not cogredient to a lower triangular matrix, i.e.,
there is no permutation matrix U such that
|     |     |     |     |     |     | * 0 |     |     |     |
| --- | --- | --- | --- | --- | --- | ----- | --- | --- | --- |
UT
L=U
|     |     |     |     |     |     | * * |     |     |     |
| --- | --- | --- | --- | --- | --- | ----- | --- | --- | --- |
Lemma 9.3 [10] Let L be irreducible and B have at least one diagonal entry
b >0. Then (L+B) is a nonsingular M-matrix. Define
i
|     |     |     | q=[q |     |          | ]T =(L+B)−1 |     |     |        |
| --- | --- | --- | ---- | --- | -------- | ----------- | --- | --- | ------ |
|     |     |     |      | q   | (cid:31) | q           | 1   |     | (9.24) |
|     |     |     |      | 1   | 2        | N           |     |     |        |
P=diag{p}≡diag{1/q}
|     |     |     |     |     |     | i   | i   |     | (9.25) |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | ------ |

9.2  Cooperative Adaptive Design and Distributed Tuning Laws  267
Then P>0 and the symmetric matrix Q defined as
|     |     |     |     | Q= P(L+B)+(L+B)TP |     |     |     | (9.26) |
| --- | --- | --- | --- | ----------------- | --- | --- | --- | ------ |
is positive definite.
In fact, this result holds if the digraph has a spanning tree and the pinning gain b is
i
nonzero for at least one root node i.
This result provides the main tool for selecting a Lyapunov function for coopera-
tive control such that the resulting control protocols and the adaptive tuning laws
are both distributed in the sense that they respect the graph topology and use only
local information available from each agent and from its neighbors. This result ex-
tends the discussion in Chap. 7 about Lyapunov functions for cooperative control
on graphs to the case of pinning control, that is, to the cooperative tracker problem.
It will further be seen in the upcoming proof that it is important that the matrix P
is diagonal.
The main result of the chapter is now presented.
Theorem 9.1 Distributed Adaptive Control Protocol for Synchronization [2]
Consider the networked systems given by (9.2) under the Assumption 1. Let the
communication digraph be strongly connected. Select the auxiliary control signal
µ (t) in (9.21) so that the local node control protocols are given by
i
|     |     |     |     |       | fˆ(x | λ     | e2  |        |
| --- | --- | --- | --- | ----- | ---- | ----- | --- | ------ |
|     |     |     |     | u =cr | - )+ | i     |     | (9.27) |
|     |     |     |     | i i   | i i  | +b    | i   |        |
|     |     |     |     |       |      | d i i |     |        |
with λ =λ>0∀i, control gains c>0, and r(t) defined in (9.13). Then
|     | i   |     |                          |     |     | i   |     |        |
| --- | --- | --- | ------------------------ | --- | --- | --- | --- | ------ |
|     |     |     | u=cr-WˆTϕ(x)+λ(D+B)-1e2  |     |     |     |     | (9.28) |
Select the local node NN tuning laws
|     |     |     | Wˆ(cid:28) | =-FϕrTp | +b)-κFWˆ |     |     | (9.29) |
| --- | --- | --- | ---------- | ------- | -------- | --- | --- | ------ |
(d
|                        |       |              | i                                 | i   | i i i i             | i   | i i                   |     |
| ---------------------- | ----- | ------------ | --------------------------------- | --- | ------------------- | --- | --------------------- | --- |
|                        |       |  being the η |                                   | ×η  |                     |     | >0 and κ>0 being sca- |     |
| with F                 | =Π I  | , I          |                                   |     |  identity matrix, Π |     |                       |     |
|                        | i i η | i η i        |                                   | i   | i                   |     | i                     |     |
| lar tuning gains, and  |       |              | p >0 defined in Lemma 9.3. Select |     |                     |     |                       |     |
i
σ(D+B)
λ=
|     |     |     |     |     |     |     |     | (9.30) |
| --- | --- | --- | --- | --- | --- | --- | --- | ------ |
σ(P)σ(A)
and select the control gain c and NN tuning gain κ so that
|     |     |     |     |       | 2  1 |     |     |     |
| --- | --- | --- | --- | ----- | ----- | ---- | --- | --- |
|     |     |     | i.  | c=    |  +λ  |  >0 |     |     |
|     |     |     |     | σ(Q) | λ     |     |     |     |
1
ϕ σ(P)σ(A)≤κ≤λ-1
|     |     |     | ii. | m   |     |     |     | (9.31) |
| --- | --- | --- | --- | --- | --- | --- | --- | ------ |
2

268 9  Cooperative Adaptive Control for Systems with Second-Order …
with P>0, Q>0 defined in Lemma 9.3 and A the graph adjacency matrix.
|     |     |     | η,i=1,N |  such that for η | >η,∀i the  |
| --- | --- | --- | ------- | ---------------- | ---------- |
Then there exist numbers of neurons
|     |     |     | i   | i   | i   |
| --- | --- | --- | --- | --- | --- |
overall sliding mode cooperative error vector  r(t), the local cooperative error
vectors  e1(t),e2(t), and the NN weight estimation errors  W  are UUB, with
practical bounds given by (9.52–9.54), respectively. Moreover, the consensus
|     | (t)=x1 | x2 T |     |     |     |
| --- | ------- | ----- | --- | --- | --- |
variable x  is cooperative UUB and all nodes synchronize so that
0  0 0
| x1(t)−x1(t) | x2(t)−x2(t) |                                              |     |     |     |
| ----------- | ----------- | -------------------------------------------- | --- | --- | --- |
|             | →0,         | →0. Moreover, the bounds (9.52–9.54) can be  |     |     |     |
| i 0         |             | i 0                                          |     |     |     |
made small by manipulating the NN and control gain parameters.
Proof The proof has two parts.
Part A: We claim that for any fixed ε >0, there exist numbers of neurons
M
η,i=1,N such that for η>η,∀i the NN approximation error is bounded by
| i   |     | i i |     |     |     |
| --- | --- | --- | --- | --- | --- |
ε ≤ε . The claim is proven in Part B of the proof. Consider now the Lyapunov
M
function candidate
|          |                                                         | 1         | 1 WTF−1W+ | 1       |        |
| -------- | ------------------------------------------------------- | --------- | ----------- | ------- | ------ |
|          |                                                         | V = rTPr+ |             | (e1)Te1 | (9.32) |
|          |                                                         | 2         | 2           | 2       |        |
|          | PT >0 defined as in Lemma 9.3 and a constant matrix F−1 |           |             |         | F−T    |
| with  P= |                                                         |           |             |         | = >0.  |
Then
|     |     | V(cid:31)        | { W(cid:30)TF−1W(cid:30)(cid:31)} |                  |        |
| --- | --- | ---------------- | --------------------------------- | ---------------- | ------ |
|     |     | =rTPr(cid:31)+tr |                                   | +(e1)Te(cid:31)1 | (9.33) |

Using (9.23) and (9.28)
  r(cid:31)=−(L+B)(f(cid:30)(x)+cr+w)+(L+B)1f ,t)+A(D+B)−1Λe2
|     |     |     |     | (x  | (9.34) |
| --- | --- | --- | --- | --- | ------ |
|     |     |     |     | 0 0 |        |
Therefore,
|     | V(cid:31) =−rTP(L+B)(W(cid:30)Tϕ(x)+ε+w+cr)+rTP(L+B)1f |     |     |     |     |
| --- | ------------------------------------------------------ | --- | --- | --- | --- |
0 (x 0 ,t)
{ (cid:31)(cid:30) }
|     | +rTPA(D+B)−1Λe2+tr |     | W(cid:30)TF−1W | +(e1)Te2 | (9.35) |
| --- | ------------------ | --- | -------------- | -------- | ------ |
|     |                    |     |                |          |        |
V(cid:31) =−rTP(L+B)cr−rTP(L+B)W(cid:30)Tϕ(x)−rTP(L+B)(ε+w)
|     | +rTP(L+B)1f | (x ,t)+rTPA(D+B)−1Λe2 |     |     |     |
| --- | ----------- | --------------------- | --- | --- | --- |
0 0
|     | {                  | (cid:31)(cid:30) } |     |     |         |
| --- | ------------------ | ------------------ | --- | --- | ------- |
|     | +tr W(cid:30)TF−1W | +(e1)T(r−Λe1)      |     |     |  (9.36) |
|     |                    |                    |     |     |         |

9.2 Cooperative Adaptive Design and Distributed Tuning Laws 269
V(cid:28) =-crTP(L+B)r-rTP(L+B){ε+w-1f (x ,t)}
0 0
+rTPA(D+B)-1 Λe2+tr  W(cid:27)T ( F-1W (cid:28)(cid:27) -ϕ(x)rTP(L+B) ) + ( e1)T r- ( e1)T Λe1
 
(9.37)
V(cid:28) =-crTP(L+B)r-rTP(L+B){ε+w-1f (x ,t)}+rTPA(D+B)-1 Λ ( r-Λe1)
0 0
+tr   W(cid:27)T ( F-1W (cid:28)(cid:27) -ϕ(x)rTP(L+B) )  + ( e1)T r- ( e1)T Λe1 (9.38)
V(cid:28) =-crTP(L+B)r-rTP(L+B){ε+w-1f (x ,t)}
0 0
+tr  W(cid:27)T ( F-1W (cid:28)(cid:27) -ϕ(x)rTP(D+B) ) +trW(cid:27)Tϕ(x)rTPA
   
+rTPA(D+B)-1 Λr-rTPA(D+B)-1 Λ2e1+ ( e1)T r- ( e1)T Λe1 (9.39)
Since L is irreducible and B has at least one diagonal entry b >0, then (L+B) is a
i
nonsingular M-matrix. Thus, according to Lemma 9.3, one can write
1
V(cid:28) =- crTQr-rTP(L+B){ε+w-1f (x ,t)}
0 0
2
+tr  W(cid:27)T ( F-1W (cid:28)(cid:27) -ϕ(x)rTP(D+B) ) +trW(cid:27)Tϕ(x)rTPA
   
+rTPA(D+B)-1 Λr-rTPA(D+B)-1 Λ2e1+ ( e1)T r- ( e1)T Λe1 (9.40)
with Q=QT >0.
Adopt the NN weight tuning law W (cid:28)(cid:27) = FϕrTp (d +b)+κFWˆ. Taking norms
i i i i i i i i i
on both sides in (9.40) one has
1
V(cid:28) ≤- cσ(Q) r 2 +σ(P)σ(L+B)B r +κW W(cid:27)
2 M M F
-κW(cid:27) 2 +φ σ(P)σ(A) W(cid:27) r +
F M F
σ(P)σ(A)σ(Λ)
r 2 +

1+
σ(P)σ(A)σ ( Λ2)
 r e1 -σ(Λ) e1 2 (9.41)
σ(D+B)  σ(D+B) 
 
where B =(ε +w +F ). Then
M M M M

270 9 Cooperative Adaptive Control for Systems with Second-Order …

1
 σ(P)σ(A)σ ( Λ2)
 σ(Λ) 1+ 
 2 σ(D+B) 
 

 1  σ(P)σ(A)σ ( Λ2) 1 σ(P)σ(A)σ(Λ)
V(cid:28)≤-   e1 r W(cid:27) F   2 1+ σ(D+B)    2 cσ(Q)- σ(D+B)   ...
  

1
 0 φ σ(P)σ(A)
 2 M


0  e1   e1 
   
1
...
2
φ
M
σ(P)σ(A)



r 

+0 σ(P)σ(L+B)B
M
κW
M
 

r 

κ    W(cid:27) F     W(cid:27) F 
(9.42)
Write (9.42) as
V ≤−zTHz+hTz (9.43)
Clearly V ≤0 iff H ≥0 and
h
z > (9.44)
σ(H)
According to (9.32) this defines a level set of V(z), so it is direct to show that V ≤0
for V large enough such that (9.44) holds [6]. To show this, according to (9.32)
one has
1 σ(P) e 2 + 1 W(cid:27) 2 + 1 e1 2 ≤V ≤ 1σ(P) e 2 + 1 W(cid:27) 2 + 1 e1 2 (9.45)
2 2Π F 2 2 2Π F 2
max min
σ(P)  e1 
  
1 1
 e1 r W(cid:27)   r ≤V ≤
2 F Π  
 max  W(cid:27) 
 1 F
(cid:23)(cid:22)(cid:22)(cid:22)(cid:21)(cid:22)(cid:22)(cid:22)(cid:20)
S
1
σ(P)  e1 
  
1 1
 e1 r W(cid:27)   r 
2 F Π   (9.46)
 min  W(cid:27) 
 1 F
(cid:23)(cid:22)(cid:22)(cid:22)(cid:21)(cid:22)(cid:22)(cid:22)(cid:20)
S
2

9.2  Cooperative Adaptive Design and Distributed Tuning Laws  271
with Π ,Π  being the minimum and maximum values of P. Equation (9.46)
| min | max |     |     |     |     |     | i   |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
is equivalent to
|     |     |     |     | 1    |      | 1    |     |        |
| --- | --- | --- | --- | ---- | ---- | ---- | --- | ------ |
|     |     |     |     | zTSz |      | zTSz |     |        |
|     |     |     |     |      | ≤V ≤ |      |     | (9.47) |
|     |     |     |     | 2    |      | 2    |     |        |
σ( )
| where S | = S |  and S | = s(S | ). Then |     |     |     |     |
| ------- | --- | ------ | ----- | ------- | --- | --- | --- | --- |
|         | 1   |        |       | 2       |     |     |     |     |

|     |     |     | 1    | 2   |      | 1      | 2   |        |
| --- | --- | --- | ---- | --- | ---- | ------ | --- | ------ |
|     |     |     | s(S) | z   | ≤V ≤ | s(S) z |     | (9.48) |
|     |     |     | 2    |     |      | 2      |     |        |
Therefore,
2
|     |     |     |     |     | s(S) | h   |     |     |
| --- | --- | --- | --- | --- | ---- | --- | --- | --- |
1
|     |     |     |     | V > |     |     |     | (9.49)  |
| --- | --- | --- | --- | --- | --- | --- | --- | ------- |
s2(H)
2
implies (9.44).
For a symmetric positive definite matrix, the singular values are equal to its
eigenvalues. Define
|         |          | σ(D+B) |     | 2     |  1 |            | 1             |     |
| ------- | -------- | ------ | --- | ----- | --- | ----------- | ------------- | --- |
| Λ=λI,λ= |          |        | ,c= | σ(Q) |     | +λ  ,andγ= | ϕ σ(P)σ(A).   |     |
|         | σ(P)σ(A) |        |     |       |  λ |            | 2 m           |     |
Then (9.42) can be written as
|     |           |     |     |           |                                           |       | e1         |     |
| --- | --------- | --- | --- | --------- | ----------------------------------------- | ------ | ----------- | --- |
|     |           |     |     |           | λ                                        | 1 0   |             |     |
|     |           |     |     |           |                                           |       |            |     |
|     | V(cid:28) | ≤- | e1  | W(cid:27) |                                         |      |            |     |
|     |           |     |     | r         | 1                                         | λ γ    | r           |     |
|     |           |    |     |           | F                                       |      |            |     |
|     |           |     |     |           | 0                                       | γ κ | W(cid:27)  |     |
|     |           |     |     |           | (cid:23)(cid:22)(cid:21)(cid:22)(cid:20) |        | F          |     |
H
|     |     |     |                |     |     |      |  e1  |        |
| --- | --- | --- | -------------- | --- | --- | ---- | ------ | ------ |
|     |     |     |                |     |     |      |      |        |
|     |     | +   | 0 σ(P)σ(L+B)B |     |     | κW   |  r  | (9.50) |
|     |     |     |               |     |     | M M |        |        |
|     |     |     |                |     |     |      |      |        |
W(cid:27)
|     |     |     |     |     |     |     |    |     |
| --- | --- | --- | --- | --- | --- | --- | ---- | --- |
|     |     |     |     |     |     |     |  F |     |
The transformed H-matrix is symmetric and positive definite under assumption
given by (9.31). Therefore, from Geršgorin circle criterion

|     |     |     |     | σ(H)≥κ-γ |     |     |     | (9.51) |
| --- | --- | --- | --- | -------- | --- | --- | --- | ------ |
with 0<γ≤κ≤λ-1. Therefore z(t) is UUB [6].
In view of the fact that, for any vector z, one has  z ≥ z ≥≥ z , sufficient
∞
|     |     |     |     |     |     | 1   | 2   |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
conditions for (9.44) are:

|     |     |     |     | B σ(P)σ(L+B)+κW |     |     |     |        |
| --- | --- | --- | --- | --------------- | --- | --- | --- | ------ |
|     |     |     | r > | M               |     | M   |     | (9.52) |
1
|     |     |     |     | κ-  | ϕσ(P)σ(A) |     |     |     |
| --- | --- | --- | --- | --- | --------- | --- | --- | --- |
|     |     |     |     |     | 2 m       |     |     |     |

272 9  Cooperative Adaptive Control for Systems with Second-Order …
or
σ(P)σ(L+B)+κW
B
|     |     |     | e1 M |     |     | M   |     |     |        |
| --- | --- | --- | ---- | --- | --- | --- | --- | --- | ------ |
|     |     |     | >    |     |     |     |     |     | (9.53) |
1
κ- ϕσ(P)σ(A)
|     |     |     |     | 2   | m   |     |     |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
or
σ(P)σ(L+B)+κW
B
|     |     |     | W(cid:27) > | M   |     | M   |     |     |        |
| --- | --- | --- | ----------- | --- | --- | --- | --- | --- | ------ |
|     |     |     |             | 1   |     |     |     |     | (9.54) |
ϕσ(P)σ(A)
κ-
|     |     |     |     | 2   | m   |     |     |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
Note that this shows UUB of  r(t),e(t),W(t). Therefore, from Lemma 9.2, the
1
boundedness of r and e1 implies bounded e2. Now Lemma 9.1 shows that the con-
sensus error vector δ(t) is UUB. Then x (t) is cooperative UUB.
0
Part B: See [3].
| According to (9.43) V |      |     |             | 2               |                             |     |       |     |        |
| ---------------------- | ---- | --- | ----------- | --------------- | --------------------------- | --- | ----- | --- | ------ |
|                        |      | ≤   | −s(H)       | z + h           | z  and according to (9.48)  |     |       |     |        |
|                        |      |     | V ≤        | −αV +           | β V                         |     |       |     | (9.55) |
| withα≡2σ(H)/σ(S),      |      | β≡  | 2 h         | / σ(S). Thence  |                             |     |       |     |        |
|                        |      |     |             | β               |                             |     |       | β   |        |
|                        | V(t) | ≤   | V(0)e-αt/2+ |                 | (1-e-αt/2)≤                 |     | V(0)+ |     |        |
|                        |      |     |             |                 |                             |     |       |     | (9.56) |
|                        |      |     |             | α               |                             |     |       | α   |        |
Using (9.48) one has

|         | σ(S)   |     |          |              |           | 2 σ(S)   |     | h   |     |
| ------- | ------ | --- | -------- | ------------ | --------- | -------- | --- | --- | --- |
| e1(t) ≤ | z(t) ≤ |     | e(0) 2 + | W(cid:27)(0) | 2 + e1(0) | +        |     | ≡ρ  |     |
|         | σ(S)   |     |          |              | F         | σ(S)σ(H) |     |     |     |
and
|        | σ(S)   |     | 2      |              | 2       | 2 σ(S)   |     | h   |        |
| ------ | ------ | --- | ------ | ------------ | ------- | -------- | --- | --- | ------ |
| r(t) ≤ | z(t) ≤ |     | e(0) + | W(cid:27)(0) | + e1(0) | +        |     | ≡ρ  | (9.57) |
|        | σ(S)   |     |        |              | F       | σ(S)σ(H) |     |     |        |
Then from (9.7)
1
|     |     | x1(t) |        |     | e1(t) | x1  |       |     |        |
| --- | --- | ----- | ------ | --- | ----- | --- | ----- | --- | ------ |
|     |     |       | ≤      |     |       | + N | (t)   |     | (9.58) |
|     |     |       | σ(L+B) |     |       | 0   |       |     |        |
ρ
|     |     |     | x1(t) ≤ |     | +   | NX 1 ≡h | 1   |     |        |
| --- | --- | --- | ------- | --- | --- | ------- | --- | --- | ------ |
|     |     |     |         |     |     | 0       | 0   |     | (9.59) |
σ(L+B)
Similarly from (9.57) and using (9.15) in Lemma 9.2
|     |     |     | e2(t) | ≤λe1(t) |     |      |     |     |     |
| --- | --- | --- | ----- | ------- | --- | ---- | --- | --- | --- |
|     |     |     |       |         | +   | r(t) |     |     |     |
≤ρ(1+λ)
|     |     |     |     |     |     |     |     |     | (9.60) |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | ------ |

| 9.3  | Simulation Example  |     |     |     |     |     |     | 273 |
| ---- | ------------------- | --- | --- | --- | --- | --- | --- | --- |
This implies
|     |     |     | x2(t) | ρ(1+λ) |     | NX2 ≡h2 |     |        |
| --- | --- | --- | ----- | ------ | --- | ------- | --- | ------ |
|     |     |     |       | ≤      | +   |         |     | (9.61) |
|     |     |     |       | σ(L+B) |     | 0 0     |     |        |

where  X2 = x2(t)  and  h ≤B σ(P)σ(L+B)+κW . Therefore, the state is
|     | 0   | 0   |     | M   |     | M   |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
contained for all times t≥0 in a compact set Ω ={x(t)| x1(t) <h1, x2(t) <h2}.
|     |     |     |     |     |     | 0   | 0   | 0   |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
According to the Weierstrass approximation theorem (Fact 9.1), given any NN ap-
proximation error bound ε  there exist numbers of neurons η,i=1,N  such that
|                     |     |     | M    |     |     |     | i   |     |
| ------------------- | --- | --- | ---- | --- | --- | --- | --- | --- |
| η >η,∀i implies sup |     |     | ε(x) | <ε  | .   |     |     | □   |
| i                   | i   |     | x∈Ω  |     | M   |     |     |     |
Discussion on NN Adaptive Control Proofs for Cooperative Systems If any one
of (9.52), (9.53), or (9.54) holds, the Lyapunov derivative is negative and V decrea-
ses. Therefore, these provide practical bounds for the neighborhood synchroniza-
tion error and the NN weight estimation error.
The elements  p  of the positive definite matrix  P=diag{p} required in the
| NN tuning law (9.29) are computed as P−11=(L+B)−1 |     | i   |     |     |     |     | i   |     |
| ------------------------------------------------- | --- | --- | --- | --- | --- | --- | --- | --- |
1 (see Lemma 9.3), which
requires global knowledge of the graph structure unavailable to individual nodes.
However, due to the presence of the arbitrary diagonal gain matrix F >0 in (9.29),
i
| one can choose  |     | pF >0 arbitrary without loss of generality. |     |     |     |     |     |     |
| --------------- | --- | ------------------------------------------- | --- | --- | --- | --- | --- | --- |
|                 |     | i i                                         |     |     |     |     |     |     |
It is important to select the Lyapunov function candidate V in (9.32) as a function of
locally available variables, e.g., the local sliding mode error r(t) and cooperative neigh-
borhood error e(t) in (9.14) and (9.7), respectively. This means that any local auxiliary
1
control signals µ(t) and NN tuning laws developed in the proof are distributed and hence
i
implementable at each node. The use of the Frobenius norm in the Lyapunov function
is also instrumental, since it gives rise to Frobenius inner products in the proof that only
depend on trace terms, where only the diagonal terms are important. In fact, the Frobe-
nius norm is ideally suited for the design of distributed protocols. Finally, it is important
in developing distributed control protocols that the matrix P of Lemma 9.3 is diagonal.
9.3  Simulation Example
For this set of simulations, consider the five-node strongly connected digraph struc-
ture in Fig. 9.1 with a leader node connected to node 3. The edge weights and the
pinning gain in (9.4) were taken equal to 1.
Consider the node dynamics for node i given by the second-order Lagrange form
dynamics
|     |     | q(cid:28) | = q |     |     |     |     |     |
| --- | --- | --------- | --- | --- | --- | --- | --- | --- |
1i 2i
|     |     |           |       |      |        |        |     |        |
| --- | --- | --------- | ----- | ---- | ------ | ------ | --- | ------ |
|     |     |           | J−1u | −Brq |        | )     |     |        |
|     |     | q(cid:28) | =     |      | −M gl  | sin(q  |     | (9.62) |
|     |     | 2i        | i     |  i  | i 2i i | i 1i  |     |        |
T
|         | =q |      | ∈R2 is the state vector,  |     |     |                                          |     |     |
| ------- | --- | ----- | ------------------------- | --- | --- | ---------------------------------------- | --- | --- |
| where q |    | ,q   |                           |     |     | J  is the total inertia of the link and  |     |     |
|         | i 1 | i 2 i |                           |     |     | i                                        |     |     |
the motor,  Br is overall damping coefficient,  M  is total mass,  g is gravitational
|     | i   |     |     |     |     | i   |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |

274 9 Cooperative Adaptive Control for Systems with Second-Order …
Fig. 9.1 Five-node digraph
with one leader node
acceleration, and l is the distance from the joint axis to the link center of mass for node.
i
J ,Br,M, and l are considered unknown and may be different for each node.
i i i i
The desired target node dynamics is taken as the inertial system
m q +d q +k q =u (9.63)
0 0 0 0 0 0 0
Select the feedback linearization input
u =-K (q -sin(βt))+K (q(cid:28) -βcos(βt))+d q(cid:28) +k q +β2m sin(βt) (9.64)
0  1 0 2 0  0 0 0 0 0
for a constant β>0. Then, the target motion q (t) tracks the desired reference
0
trajectory sin(βt).
The cooperative adaptive control protocols of Theorem 9.1 were implemented at
each node. As is standard in neural and adaptive control systems, reasonable positive
values were initially chosen for all control and NN tuning parameters. Generally, the
simulation results are not too dependent on the specific choice of parameters as long
as they are selected as detailed in the Theorem 9.1 and assumptions, e.g., positive.
The number of NN hidden layer units can be fairly small with good performance
resulting, normally in the range of 5–10. As in most control systems, however, the
performance can be improved by trying a few simulation runs and adjusting the
parameters to obtain good behavior. In online implementations, the parameters can
be adjusted after some simulation studies to obtain better performance. For NN
1
activation functions we use log-sigmoid of the form with positive slope
1+e−kt
parameter k. The number of neurons used at each node was finally selected as 3.
So, ϕ ≈1 and γ ≈0.04. NN gain parameter was selected as κ=1.5. According to
m
(9.31) the pinning gain should be selected large and it was taken as c=1000.
In the simulation plots, we show tracking performance of positions (q ) and ve-
1i
locities (q ) for all i. At steady state all q and q are synchronized and follow the
2i 1i 2i
second-order single-link leader trajectory given by q and q , respectively.
0 0

275
4
3
2
1
0
0 0.1 0.2 0.3 0.4 0.5 0.6 0.7 0.8 0.9 1
Time(t)
Figure 9.2 shows the tracking performance of the system. One can see from the
figure that positions and velocities of all the five nodes are synchronized in two
different final values which are given by the final values of [q ,q ]T. More specifi-
0 0
cally, q ’s are synchronized with q and q ’s are synchronized with q at steady
1i 0 2i 0
state. The figure also shows the inputs u for all agents while tracking.
i
Figure 9.3 describes the position and velocity consensus disagreement error vec-
tors, namely (q −q ,q −q )T,∀i and also the NN estimation error in terms of
1i 0 2i 0
f(x)− ˆ f(x)T∀i. One can see that all the errors are minimized almost to zero.
 i i 
Figure 9.4 describes the comparison of unknown dynamics f (x) with estimated
i
dynamics ˆ f(x). The figure also shows that the steady-state values of f (x) and
ˆ f(x) are al i most equal. Figure 9.5 describes the dynamics of all the NN i weights
i
over time which also describes the effectiveness of the tuning law. As stated in
Chap. 8, please note that the simulation response can be varied for the choice of
number of neurons. In this example, the number of neurons = 3 for each node.
Figure 9.6 is the phase plane plot of all agents, i.e., the plot of q ∀i (along the
1i
x-axis) and q ∀i (along the y-axis). At steady state, the Lissajous pattern formed
2i
by all five nodes is the target node’s phase plane trajectory.
i ∀ixsetatS
State dynamics and input
200
100
0
−100
−200
−300
0 0.1 0.2 0.3 0.4 0.5 0.6 0.7 0.8 0.9 1
Time(t)
i ∀iutupnI
9.3 Simulation Example
Position
Velocity
Fig. 9.2 Tracking performance (position and velocity) and control input

276 9 Cooperative Adaptive Control for Systems with Second-Order …
Error Plot
3
2
1
0
−1
0 0.2 0.4 0.6 0.8 1
Time(t)
i
δ
∀i
150
100
50
0
−50
−100
0 0.2 0.4 0.6 0.8 1
Time(t)
i
)x(ˆf-)x(f
i
i
∀
Velocity Error
Position Error
Fig. 9.3 Disagreement vector and NN estimation error vector
State Dynamics
0
−1
−2
−3
−4
0 0.2 0.4 0.6 0.8 1
Time(t)
i
)x(f
∀
i
Estimated State Dynamics
100
0
−100
−200
−300
0 0.2 0.4 0.6 0.8 1
Time(t)
i
)x(ˆf
i
∀
Fig. 9.4 Comparison of f(x) and ˆ f(x)

277
20
0
−20
−40
−60
−80
0.05 0.1 0.15
Time(t)
i∀
WthgiewNN
ii
Fig. 9.5 Stable NN weight dynamics for all nodes
1.5
1
0.5
0
−0.5
−1
−1.5
−2
−2.5
−3
−3.5
−3.5 −3 −2.5 −2 −1.5 −1 −0.5 0 0.5 1 1.5
x(t) i
i ∀
i ∀
)t(ix˙
9.3 Simulation Example
All5nodestogetherwithleadernode
Sync. Motion
Fig. 9.6 Phase plane plot for all the nodes

278 9 Cooperative Adaptive Control for Systems with Second-Order …
References
1. Das A, Lewis FL (2010) Distributed adaptive control for synchronization of unknown non-
linear networked systems. Automatica 46(12):2014–2021
2. Das A, Lewis FL (2011) Cooperative adaptive control for synchronization of second-order
systems with unknown nonlinearities. Int J Robust Nonlinear Control 21(13):1509–1524
3. Ge SS, Wang C (2004) Adaptive neural control of uncertain MIMO nonlinear systems. IEEE
Trans Neural Netw 15(3):674–692
4. Ge SS, Hang CC, Zhang T (1998) Stable Adaptive Neural Network Control. Springer, Berlin
5. Hornik K, Stinchombe M, White H (1989) Multilayer feedforward networks are universal
approximations. Neural Netw 2(5):359–366
6. Khalil HK (2002) Nonlinear Systems, 3rd edn. Prentice Hall, Upper Saddle River, NJ
7. Khoo S, Xie L, Man Z (2009) Robust finite-time consensus tracking algorithm for multirobot
systems. IEEE Trans Mechatron 14(2):219–228
8. Lewis FL, Yesildirek A, Liu K (1996) Multilayer neural net robot controller with guaranteed
tracking performance. IEEE Trans Neural Netw 7(2):388–399
9. Lewis FL, Jagannathan S, Yesildirek A (1999) Neural Network Control of Robot Manipulators
and Nonlinear Systems. Taylor and Francis, London
10. Qu Z (2009) Cooperative Control of Dynamical Systems: Applications to Autonomous Vehic-
les. Springer-Verlag, New York
11. Stone MH (1948) The generalized weierstrass approximation theorem. Math Mag 21
(4/5):167–184/237–254

Chapter 10
Cooperative Adaptive Control
for Higher-Order Nonlinear Systems
Cooperative control on communication graphs for agents that have unknown non-
linear dynamics that are not the same is a challenge. The interaction of the commu-
nication graph topology with the agent’s system dynamics is not easy to investigate
if the dynamics of the agents are heterogeneous, that is, not identical, since the
Kronecker product cannot be used to simplify the analysis. Therefore, the intertwin-
ing of the graph structure with the local control design is more severe and makes
the design of guaranteed synchronizing controls very difficult. That is to say, the
communication graph structure imposes more severe limitations on the design of
controllers for systems that have nonlinear and nonidentical dynamics, making it
more challenging to guarantee the synchronization of all agents in the network.
In this chapter, we continue to study adaptive control for the cooperative tracking
problem, where it is desired for all agents to synchronize to the state of a target or
command generator node. For implementation using local neighborhood informa-
tion on a communication graph, it is required not only for the control law to be dis-
tributed but also for the adaptive parameter tuning laws to be distributed. We have
seen in Chaps. 8 and 9 how to design adaptive controllers for multi-agent systems
with first-order [1] and second-order [2] nonlinear dynamics on general directed
graphs. However, many practical systems have higher-order dynamics. Therefore,
in this chapter we study synchronizing controls design for nonlinear systems in
chained or Brunovsky form, where all agents have unknown dynamics that may not
be the same for each agent.
The extension of adaptive control to higher-order dynamics in this chapter is
not straightforward. In cooperative adaptive controller for multi-agent systems on
graphs, it is required not only for the control law to be distributed, but also for the
adaptive tuning laws to be distributed. This requires the careful crafting of a suit-
able Lyapunov function that automatically yields a distributed adaptive controller
depending only on local neighborhood information. In Chap. 7 some techniques for
Lyapunov design for cooperative control were given. It was seen that for undirected
graphs, and even balanced graphs, it is not difficult to extend Lyapunov techniques
to multi-agent systems on graphs. However, for the case of general directed graphs
it was seen that the Lyapunov function must be carefully constructed, and must
F. L. Lewis et al., Cooperative Control of Multi-Agent Systems, 279
Communications and Control Engineering, DOI 10.1007/978-1-4471-5574-4_10,
© Springer-Verlag London 2014

280 10 Cooperative Adaptive Control for Higher-Order Nonlinear Systems
generally contain information about the graph topology, e.g., in the form of the ele-
ments of the first left eigenvector of the graph Laplacian matrix.
We show in this chapter how to craft a Lyapunov function suitable for adaptive
control on graphs of higher-order multi-agent systems with heterogeneous nonlinear
dynamics. We use two Lyapunov equations, one that captures the local system dy-
namics of each agent, and one that captures the graph topology. The two Lyapunov
equations are solved independently, so that the local controls design is decoupled
from the detailed communication graph topology. Yet, the interplay of these two
design equations in the Lyapunov proof yields cooperative adaptive control laws,
where both the control protocols and the tuning laws depend only on distributed
neighbor information.
In Sect. 10.1, we formulate the adaptive cooperative tracker problem for higher-
order multi-agent systems on graphs. An error dynamics is derived and a Lyapunov
equation that depends on the graph topology is defined. In Sect. 10.2, a distributed
control protocol is developed based on a suitable sliding mode error. A second Ly-
apunov equation is introduced to capture the stability properties of this sliding error
dynamics. Local function approximator structures are introduced to estimate the
unknown nonlinear dynamics. In Sect. 10.3, we develop cooperative control adap-
tive tuning laws that depend only on distributed information locally available in the
graph. The Lyapunov function that we use to derive the tuning laws involves both
the Lyapunov equations, one depending on the graph topology and one on the slid-
ing error dynamics. A simulation example in Sect. 10.4 verifies proper performance
of the cooperative adaptive controller.
The results of this chapter were first published in [17].
10.1 Sliding Variable Control Formulation and Error
Dynamics
In this section, we lay the foundation for the design of adaptive cooperative control-
lers for a class of nonlinear agent dynamics in Brunovsky form. Basic definitions
are given and the local neighborhood error dynamics are introduced. Some require-
ments on the graph topology are laid out, and a Lyapunov equation is given that
contains information about the graph topological structure.
10.1.1 Synchronization for Nonlinear Higher-Order
Cooperative Systems
We consider the case of multi-agent control on a communication graph where each agent
has higher-order unknown nonlinear dynamics in Brunovsky form. The agent dynamics
need not be identical. This class of systems is important for several reasons. First, most
existing works on multi-agent systems study the first- or second-order systems with

10.1  Sliding Variable Control Formulation and Error Dynamics  281
linear dynamics. However, in engineering, many systems are modeled by higher-order
dynamics. For example, a single-link, flexible-joint manipulator is well modeled by a
fourth-order nonlinear system [7]. The jerk (i.e., derivative of acceleration) systems,
described by third-order differential equations, are of particular interest in mechanical
engineering. An interesting property of nonlinear jerk systems is their possible chaotic
behavior. Due to the challenges in designing cooperative controls for systems distrib-
uted on communication networks, it is not straightforward to extend results for first- and
second-order systems to a system with higher-order dynamics, and a great deal of study
has been devoted to higher-order linear multi-agent systems [6, 12, 16, 18, etc.].
The communication network considered in this chapter is a directed graph with a
fixed topology, denoted by G =(V,E), where  ={v,…,v } is a nonempty set of
1 N
nodes/agents and E ⊆V×V is a set of edges/arcs. Its associated adjacency matrix
]∈N×N, where a
is A=[a >0 if (v ,v)∈ , i.e., there is an edge from node j to
| ij  | ij  | j i |     |     |
| --- | --- | --- | --- | --- |
=∑N
node i, otherwise a =0. Define d a  as the weighted in-degree of node
| ij  | i   | j=1 ij |     |     |
| --- | --- | ------ | --- | --- |
D=diag{d}∈N×N as the in-degree matrix. The graph Laplacian matrix
i and
i
is L=[l ]= D−A. Let 1=[1,…,1]T with appropriate dimension, which satisfies
ij
| L1=0. Define  ={1,…,N}. |     |     |     |     |
| ------------------------ | --- | --- | --- | --- |
Consider a group of N (N ≥2) agents with nonidentical dynamics distributed on
a directed communication network . The dynamics of the i-th agent is described in
the nonlinear Brunovsky form,
x(cid:31) = x
|     | i,1 | i,2 |     |     |
| --- | --- | --- | --- | --- |
x(cid:31) = x
|     | i,2         | i,3          |     |        |
| --- | ----------- | ------------ | --- | ------ |
|     | (cid:30)    |              |     | (10.1) |
|     | x(cid:31) = | f (x)+u +ζ , |     |        |
|     | i,M         | i i i i      |     |        |
|     |             |              |     |        |
]T ∈M is the state vec-
| where x ∈ is the m-th state of node i, x |     | =[x ,…,x |     |     |
| ----------------------------------------- | --- | -------- | --- | --- |
| i,m                                       |     | i i,1    | i,M |     |
tor of node i,  f (x):M → is locally Lipschitz with  f (0)=0, and it is assumed
| i i |     |     | i   |     |
| --- | --- | --- | --- | --- |
∈ is the control input/protocol; and ζ
| to be unknown; u |     |     | ∈(cid:25) is an external dis- |     |
| ---------------- | --- | --- | ----------------------------- | --- |
| i                |     |     | i                             |     |
turbance, which is unknown but bounded. The development can be extended to the
vector case x ∈n by using the Kronecker product.
i,m
Equation (10.1) can be written collectively in global form for all the agents as
|     | x(cid:31)1 = | x2  |     |     |
| --- | ------------ | --- | --- | --- |
|     | x(cid:31)2 = | x3  |     |     |
(10.2)
(cid:30)
|     | x(cid:31)M = | f(x)+u+ζ, |     |     |
| --- | ------------ | --------- | --- | --- |

where  xm =[x ,…,x ]T ∈N ;  f(x)=[f (x ),…, f (x )]T ∈N ;
| 1,m | N,m |     | 1 1 | N N |
| --- | --- | --- | --- | --- |
u=[u ,…,u ]T ∈N; and ζ=[ζ ,…,ζ ]T ∈(cid:25)N. Specifically, for example, when
| 1 N | 1   | N   |     |     |
| --- | --- | --- | --- | --- |
M =3, x1, x2, and x3 represent the global position, velocity, and acceleration vec-
tors, respectively.

282 10  Cooperative Adaptive Control for Higher-Order Nonlinear Systems
The time-varying dynamics of a leader or target node, labeled 0, is described by
x(cid:31) = x
0,1 0,2
x(cid:31) = x
0,2 0,3
(cid:30)
|     |     |     | x(cid:31) | = f (t,x ), |     | (10.3) |     |
| --- | --- | --- | --------- | ----------- | --- | ------ | --- |
|     |     |     | 0,M       |  0 0        |     |        |     |

where x ∈ is the m-th state variable and x =[x ,…,x ]T ∈M  is the state
|     | 0,m |     |     | 0 0,1 | 0,M |     |     |
| --- | --- | --- | --- | ----- | --- | --- | --- |
):[0,∞)×M
vector of the leader node;  f (t,x → is piecewise continuous in
|     |     |     | 0 0 |     |     |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- |
t and locally Lipschitz in x  with  f (t,0)=0 for all t≥0 and all x ∈M . The
|     |     | 0   | 0   |     |     | 0   |     |
| --- | --- | --- | --- | --- | --- | --- | --- |
leader dynamics  f (t,x ) is unknown to all follower nodes (10.1). System (10.3) is
0 0
assumed to be forward complete, i.e., for every initial condition, the solution x (t)
0
exists for all t≥0.
The leader node dynamics (10.3) can be considered as an exosystem that gener-
ates a desired command trajectory. As such, the leader is a command generator.
Define the m-th order disagreement variable for node i, disagreeing from the
leader node 0, as δ = x -x . Then, the global m-th order disagreement vari-
|     |     | i,m i,m | 0,m |     |     |     |     |
| --- | --- | ------- | --- | --- | --- | --- | --- |
able is
δm xm
|     |     |     | =   | -x , |     |     |     |
| --- | --- | --- | --- | ---- | --- | --- | --- |
0,m
| where δm |     | ]T   | ∈(cid:25)N and  |            | ]T ∈(cid:25)N. The perfect  |     |     |
| -------- | --- | ---- | --------------- | ---------- | --------------------------- | --- | --- |
|          | =[δ | ,…,δ |                 | x =[x ,…,x |                             |     |     |
|          | 1,m | N,m  |                 | 0,m 0,m    | 0,m                         |     |     |
cooperative tracking problem, also known as the synchronization problem, is de-
scribed as follows.
Problem 10.1 Cooperative Tracking Problem Design controllers  u  for all
i
|                                  |               |     | x                   | (t)→x (t) as  | t→∞ for all  | i∈ |       |
| -------------------------------- | ------------- | --- | ------------------- | ------------- | ------------ | --- | ----- |
| the nodes in graph , such that  |               |     |                     |               |              |     |  and  |
|                                  |               |     | δm i,m              | 0,m           |              |     |       |
| m=1,…,M                          | , namely, lim |     | =0 for all m=1,…,M. |               |              |     |       |
t→∞
Here, it should be noted that due to the existence of unknown nonlinearities  f
and disturbances ζ, the objective is to relax the requirement for the tracking errors  i
i
δm to be within a small neighborhood of zero. This is illustrated by the following
definition, which extends the standard concept of uniform ultimate boundedness
[7, 9] to cooperative control systems with higher-order dynamics.
Definition  10.1  Cooperative  Uniform  Ultimate  Boundedness For  any
m=1,…,M, the tracking error δm is said to be cooperatively uniformly ultimately
bounded (CUUB) if there exists a compact set Ωm ⊂N with the property that
{0}⊂Ωm, so that for any δm(t )∈Ωm, there exist a bound Bm and a finite time
0
|           | (Bm,δ1(t | ),…,δM(t |                             |     |              | δm(t) | ≤Bm |
| --------- | -------- | -------- | --------------------------- | --- | ------------ | ----- | --- |
| instant T | m        | 0        | 0 )), both independent of t |     | , such that  |       | ,   |
0
| ∀t≥t | +T . |     |     |     |     |     |     |
| ---- | ---- | --- | --- | --- | --- | --- | --- |
|      | 0 m  |     |     |     |     |     |     |
If the tracking error δm is CUUB, then x (t) is bounded within a neighborhood of
i,m
x (t), for all i∈  and t≥t +T . This describes a practical scenario of “close
| 0,m |     |     | 0 m |     |     |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- |
enough” synchronization.

10.1  Sliding Variable Control Formulation and Error Dynamics  283
10.1.2  Local Neighborhood Error Dynamics
In this chapter, it is assumed that only local distributed state information on
the communication graph is available for controller design. More precisely, for
the i-th node, the only obtainable information is its neighborhood synchronization
errors [8],
|     |     | e   | = ∑a | (x     | −x )+b(x |       | −x ), m=1,…,M, |     | (10.4) |
| --- | --- | --- | ---- | ------ | -------- | ----- | -------------- | --- | ------ |
|     |     | i,m |      | ij j,m | i,m      | i 0,m | i,m            |     |        |
j∈Ni

where b ≥0 is the weight of the edge from the leader node 0 to node i (i∈).
i
Then, b >0 if and only if there is an edge from the leader node to node i, which
i
implies that the leader node can send commands to node i. Only a few nodes may
be connected to the leader.
Define em =[e ,…,e ]T and  B=diag{b}∈N×N. Noticing that  L1=0, a
|     |     |     | 1,m | N,m |     |     |     |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
straightforward computation of (10.4) gives the global form em i =−(L+B)(xm
−x ),
0,m
as detailed below:
|     |      |             | ∑ a     | (x −x  | )+b(xx |       | −x )  |     |     |
| --- | ---- | ------------ | ------- | ------ | ------ | ----- | ------ | --- | --- |
|     |      |              |         | 1j j,m | 1,m    | 1 0,m | 1,m    |     |     |
|     |      |             | j∈ N    |        |        |       |       |     |     |
|     |  e  |            | 1       |        |        |       |       |     |     |
|     |     | 1, m        | ∑       |        |        |       |        |     |     |
|     |  e  |            | a       | (x −x  | )+b    | (x    | −x )  |     |     |
|     | em  | 2 , m       | 2j      | j,m    | 2,m    | 2 0,m | 2,m    |     |     |
|     | =   | =          | j ∈ N 2 |        |        |       |       |     |     |
|     |     | (cid:29)   |         |        |        |       |       |     |     |
(cid:29)
|     |         |          |           |            |        |          |       |               |       |
| --- | -------- | ---------- | --------- | ---------- | ------ | -------- | ------ | ------------- | ----- |
|     | e       |           |           |            |        |          |        |               |       |
|     |  N,m   |           | ∑ a       | (x −−x     | )+b    | (x       | −x )  |               |       |
|     |          |            | Nj        | j,m        | N,m    | N 0,m    | N,m    |               |       |
|     |          |  j∈NN    |           |            |        |          |      |               |       |
|    | ∑ a      | x         |  ∑ a     | x         |        |          |        |               |       |
|    | 1j       | j,m       |          | 1j 1,m    |        |          |        |               |       |
|    | j ∈ N1   |           |  j ∈ N   |           |        |          |        |               |       |
|    |          |           |  1       |           |  b 1  |          |       |               |       |
|    | ∑ a      | x         |  ∑ a     | x         |       |          |       |               |       |
|    | 2j       | j,m      |          | 2j 2,m    |       | b        |       |               |       |
|     |          |            |           |            |       | 2        |  −xm) |               |       |
| =  | j ∈ N 2  |  −        |  j ∈ N 2 |           | +     |          |  (x   |               |       |
|    |          |           |          |           |       | (cid:30) |  0,m  |               |       |
|    | (cid:31) |           |          | (cid:31)  |        |          |        |               |       |
|    |          |           |          |           |       |          |       |               |       |
|    |          |           |         |           |       |          | b     |               |       |
|    | ∑ a      | x         |  ∑ a     | x         |       |          | N     |               |       |
|     | Nj       | j,m        |           | Nj N,m     |        |          |        |               |       |
|    | j∈NN     |           |  j∈NN   |           |        |          |        |               |       |
|    |          |           |           |           |        |          |        |               |       |
|     |          |            |           |            | ∑ a   |          |        |              |       |
|     |          |            |           |            |  1j   |          |        |              |       |
|     |          |            |           |            |  j∈N1 |          |        |              |       |
|    | a a 11   | 2 (cid:29) | a       | x 1 , m   |       |          |        |   x 1 , m  |       |
|    | 1 1      |            | 1 N     |           |       | ∑        |        |            |       |
|    | a a      | (cid:29)   | a       | x         |        |          | a 2j   |  x          |       |
|    | 2 1      | 2 2        | 2 N     | 2 , m     |       |          |        |   2 , m    | −−xm) |
| =  |          |            |         |  −        |       | j ∈N2    |        |    +B(x    |       |
(cid:31) (cid:31) (cid:30) (cid:31)  (cid:31)     (cid:31)  0,m
|                  |       |          |              |              |   |         | (cid:30) |            |     |
| ----------------- | ----- | -------- | ------------- | ------------ | --- | ------- | -------- | ----------- | --- |
|                  |       |          |             |             |    |         |          |          |     |
| a                | a     | (cid:29) | a  xx       |             |    |         |          |  x       |     |
|                  | N 1 N | 2        | N N         | N , m       |     |         | ∑        | a  N , m  |     |
|                   |       |          |               |              |    |         |          | Nj         |     |
|                   |       |          |               |              |    |         | j∈NN     |            |     |
|                   |       |          |               |              |    |         |          |            |     |
| = Axm−Dxm+B(x     |       |          | −xm)=−Lxm+B(x |              |     | −xm)+Lx |          |             |     |
|                   |       |          | 0,m           |              |     | 0,m     | 0,m      |             |     |
| =−(L+B)xm+(L++B)x |       |          |               | =−(L+B)(xm−x |     |         |          |             |     |
|                   |       |          | 0,m           |              |     | 0,m ).  |          |             |     |
Thus, one has the error dynamics in global form

284 10  Cooperative Adaptive Control for Higher-Order Nonlinear Systems
|     |     | e(cid:31)1 =e2 |     |     |
| --- | --- | -------------- | --- | --- |
e(cid:31)2 =e3
(cid:30)
|     |     | e(cid:31)M =−(L+B)(f(x)+u+ζ−f | ),  | (10.5) |
| --- | --- | ----------------------------- | --- | ------ |
0
| where  f =[f                                          | (t,x ),…, | f (t,x )]T ∈(cid:25)N. |     |     |
| ----------------------------------------------------- | --------- | ---------------------- | --- | --- |
| 0                                                     | 0 0       | 0 0                    |     |     |
| 10.1.3   Communication Graph Structure and the Graph  |           |                        |     |     |
Lyapunov Equation
Define the augmented graph as G ={V,E}, where  ={v ,v,…,v } is the node
|     |     |     | 0 1 N |     |
| --- | --- | --- | ----- | --- |
set and E ⊆V×V  is the edge set. The following assumption holds throughout this
chapter.
Assumption 10.1 Communication Graph Topology The augmented graph  
contains a spanning tree with the root node being the leader node 0.
Assumption 10.1 is a necessary condition for solving the cooperative tracking prob-
lem. See Remarks 3.2 and 3.3 for details.
The following two technical lemmas play important roles in the proof of The-
orem 10.1, the main result of this chapter. In particular, Lemma 10.1 constructs
a Lyapunov equation that captures the graph structure, which we call the graph
Lyapunov equation.
Lemma 10.1 Graph Lyapunov Equation Define
|     |     | ]T =(L+B)−11, |     |        |
| --- | --- | ------------- | --- | ------ |
|     |     | q=[q,…,q      |     | (10.6) |
1 N
|     |     | P=diag{p}=diag{1/q}, |     | (10.7) |
| --- | --- | -------------------- | --- | ------ |
|     |     | i                    | i   |        |
|     |     | Q= P(L+B)+(L+B)TP.   |     | (10.8) |

Then, P>0 and Q>0 [11].
Proof First, we show that the matrix  L+B is nonsingular. Under Assumption
10.1, at least one node in  can get information directly from the leader node,
i.e., b >0 for at least one i∈ . Without loss of generality, it is assumed that
i
there are exactly two nodes r  and r  such that b >0 and b >0. Then, for the
|     |     | 1 2 | r1 r2 |     |
| --- | --- | --- | ----- | --- |
|≥∑N
matrix L+B, |l +b l  for all i∈  and the strict inequality holds for
|     | ii i | ij  |     |     |
| --- | ---- | --- | --- | --- |
j=1,j≠i
i∈{r,r}. Assumption 10.1 implies that, for any other node i which does not have
1 2
direct access to the leader node (i.e., i∈N (cid:30){r,r}), there must be a directed path
i 2

| 10.2  Distributed Control Structure  |     |     |     |     | 285 |
| ------------------------------------ | --- | --- | --- | --- | --- |
originated from either node r  or node r . According to [14], L + B is nonsingular.
1 2
Then, L + B is a nonsingular M-matrix and Lemma 10.1 follows from the same
| development as in ([11] Theorem 4.25).  |     |     |     |     | □   |
| --------------------------------------- | --- | --- | --- | --- | --- |
]T =(L+B)−11
It is noted that the reciprocals of the elements of vector q=[q,…,q
1 N
contain information related to that contained in the elements of the left eigenvector
| p of the graph Laplacian matrix, i.e.,  |     | pTL=0. |     |     |     |
| --------------------------------------- | --- | ------ | --- | --- | --- |
Lemma 10.2 One has
|     | ||δm ||≤||em | ||/σ(L+B), | m=1,…,M, |     | (10.9) |
| --- | ------------ | ---------- | -------- | --- | ------ |

where σ(L+B) is the minimum singular value of the matrix L + B.
Proof L + B is nonsingular under Assumption 10.1. Noticing that em =-(L+B)δm,
| it follows that δm | =-(L+B)-1em. Therefore, |     |                    |     |     |
| ------------------ | ----------------------- | --- | ------------------ | --- | --- |
|                    | ||δm ||=||(L+B)-1em     |     | ||≤||em ||/σ(L+B). |     |     |
|                    |                         |     |                    |     | □   |
Remark 10.1 Lemma 10.2 implies that, if the graph has a spanning tree, then
|| is bounded, ||δm
| as long as ||em |     | || is bounded. Moreover, em |     | →0 implies that  |     |
| --------------- | --- | --------------------------- | --- | ---------------- | --- |
δm →0, i.e., x →x , and synchronization to the leader is achieved. Therefore,
i,m 0,m
we focus henceforth on designing a controller such that the local neighborhood
| error ||em || is bounded.  |     |     |     |     | ▋   |
| -------------------------- | --- | --- | --- | --- | --- |
10.2  Distributed Control Structure
In this section, we design a control protocol structure that is distributed in the sense
that it depends only on local neighbor information. As such, this is allowable for
multi-agent control in that it obeys the restrictions imposed by the communication
graph structure. Sliding mode error variables are introduced to streamline the con-
troller design. A Performance Lyapunov Equation is given that is complementary
to the Graph Lyapunov Equation (10.8). Neural network (NN) approximators are
introduced at each node to estimate the unknown agent nonlinearities.
| 10.2.1   Sliding Mode Error Variables and Performance   |     |     |     |     |     |
| ------------------------------------------------------- | --- | --- | --- | --- | --- |
Lyapunov Equation
Introduce a sliding mode error variable r for each follower node i=1,…,N as
i
|     | r =λe +λe | +(cid:31)+λ | e +e , i∈.   |     | (10.10) |
| --- | --------- | ----------- | ------------- | --- | ------- |
|     | i 1 i,1   | 2 i,2       | M-1 i,M-1 i,M |     |         |

286 10  Cooperative Adaptive Control for Higher-Order Nonlinear Systems
The  design  gain  parameters  (cid:31)  are  chosen  such  that  the  polynomial
i
 is Hurwitz. To ease the design, one can obtain such (cid:31) by
i
solving the equation sM-1+λ sM-2+…+λ=ΠM-1(s-α) for all s∈, where α
|     |     | M-1 | 1 i=1 | i   | i   |
| --- | --- | --- | ----- | --- | --- |
are arbitrary positive real numbers.
The cooperative tracking control objective is to keep the sliding mode errors r
i
on or near the sliding surface r =0. If r =0, then e →0 exponentially as t→∞.
|     |     | i   | i   | i   |     |
| --- | --- | --- | --- | --- | --- |
If r  is bounded, then, e  will be bounded. Define the global sliding mode error
| i   |     | i   |     |     |     |
| --- | --- | --- | --- | --- | --- |
]T
| r =[r,…,r | . Then, |     |     |     |     |
| --------- | ------- | --- | --- | --- | --- |
| 1         | N       |     |     |     |     |
Define
E =[e1,…,eM−1]∈N×(M−1),
1
E(cid:31) =[e2,…,eM]∈(cid:30)N×(M−1),
|     |     | E = |     |     |     |
| --- | --- | --- | --- | --- | --- |
2 1
|     |     | =[0,…,0,1]T | ∈M−1, |     |     |
| --- | --- | ----------- | ------ | --- | --- |
l
and
|     |  0           | 1 0               | (cid:31) 0                                |     |     |
| --- | ------------- | ----------------- | ------------------------------------------ | --- | --- |
|     |              |                   |                                           |     |     |
|     |  0           | 0 1               | (cid:31) 0                                |     |     |
|     |              |                   |                                           |     |     |
|     | Λ=  (cid:29) | (cid:29) (cid:29) | (cid:30) (cid:29)  ∈(cid:25)(M-1)×(M-1). |     |     |

|     |    |       |              |     |     |
| --- | --- | ----- | ------------- | --- | --- |
|     | 0   | 0 0   | (cid:31) 1    |     |     |
|     |    |       |              |     |     |
|     |    |       |              |     |     |
|     | -λ | -λ -λ | (cid:31) -λ  |     |     |
|     |    | 1 2 3 | M-1          |     |     |
Then, one has
|     |     | E = EΛT | +rlT. |     | (10.11) |
| --- | --- | ------- | ----- | --- | ------- |
|     |     | 2       | 1     |     |         |
Since Λ is Hurwitz, given any positive number β, there exists a matrix P >0, such
1
that the following performance-related Lyapunov equation holds:
|     |     | ΛTP      |     |     |         |
| --- | --- | -------- | --- | --- | ------- |
|     |     | +PΛ=−βI, |     |     | (10.12) |
|     |     | 1        | 1   |     |         |
where I ∈(M−1)×(M−1) is the identity matrix.
Remark 10.2 Graph Lyapunov Equation and Performance Lyapunov Equa-
tion It is emphasized that the Performance Lyapunov Equation (10.12) captures
information about the local control design, and the Graph Lyapunov Equation (10.8)
captures information about the communication graph topology. Both are needed in
| the Lyapunov proof of the main result in Sect. 10.3.  |     |     |     |     | ▋   |
| ----------------------------------------------------- | --- | --- | --- | --- | --- |

| 10.2  | Distributed Control Structure  |     |     |     |     |     |     |     | 287 |
| ----- | ------------------------------ | --- | --- | --- | --- | --- | --- | --- | --- |
The dynamics of the sliding mode error r is
e(cid:28)M-1+e(cid:28)M
r(cid:28)=λe(cid:28)1+λe(cid:28)2+(cid:31)+λ
|     |     |                     | 1   | 2   | M-1 |                     |     |     |         |
| --- | --- | ------------------- | --- | --- | --- | ------------------- | --- | --- | ------- |
|     |     | =λe2+λe3+(cid:31)+λ |     |     |     | eM -(L+B)(f(x)+u+ζ- |     | f ) |         |
|     |     |                     | 1   | 2   | M-1 |                     |     | 0   |         |
|     |     | =ρ-(L+B)(f(x)+u+ζ-  |     |     |     | f                   | ),  |     | (10.13) |
0
where

|               |     |     | ρ=λe2+λe3+(cid:31)+λ |     |     |     | eM = E λ |     | (10.14) |
| ------------- | --- | --- | -------------------- | --- | --- | --- | -------- | --- | ------- |
|               |     |     |                      | 1   | 2   |     | M-1 2    |     |         |
| with λ=[λ,…,λ |     |     | ]T.                  |     |     |     |          |     |         |
|               |     | 1   | M-1                  |     |     |     |          |     |         |
The next lemma shows that (ultimate) boundedness of r  implies the (ultimate)
i
boundedness of e, ∀i=1,…,N.
i
Lemma 10.3 For all i=1,…,N, suppose
|     |     |     |     | |r(t)|≤ψ, |     | ∀t≥t  | ,   |     |     |
| --- | --- | --- | --- | --------- | --- | ----- | --- | --- | --- |
|     |     |     |     |           | i   | i     | 0   |     |     |
|     |     |     |     | |r(t)|≤ξ, |     | ∀t≥T, |     |     |     |
|     |     |     |     |           | i   | i     | i   |     |     |
for some bounds ψ >0, (cid:31)>0, and time T >t . Then, there exist bounds Ψ >0,
|             |               |     | i    | i                                  |        | i    | 0   |     | i       |
| ----------- | ------------- | --- | ---- | ---------------------------------- | ------ | ---- | --- | --- | ------- |
| Ξ           | >0 and time ∆ |     | >t   | , such that                        |        |      |     |     |         |
| i           |               |     | i 0  |                                    |        |      |     |     |         |
| Proof Let  |               | =[e | ,…,e | ]T. Then, equation (10.10) implies |        |      |     |     |         |
|             |               | i   | i,1  | i,M−1                              |        |      |     |     |         |
|             |               |     |      |                                    |  =Λ | +lr. |     |     | (10.15) |
|             |               |     |      |                                    | i      | i    | i   |     |         |

Using a similar development as in [4] Lemma 2.1, it is straightforward to show
that if r(t) is bounded, i.e., |r(t)|≤  for t≥t , then (t) is bounded. Equation
|     | i   |     |     |     |     |     | 0 i |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
(10.15) further implies that  (t) is bounded, for t≥t . Therefore, e(t) is bounded,
|     |     |     |     | i   |     |     | 0   | i   |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
i.e., ||e ||≤Ψ ,∀t≥t  for some Ψ >0. Similarly, we can show that if r(t) is ulti-
|                                              | i   | i   | 0   |     | i   |     |     |     | i   |
| -------------------------------------------- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| mately bounded, e(t) is ultimately bounded.  |     |     |     |     |     |     |     |     | □   |
i
| 10.2.2  |     | Local NN Approximators for Unknown Nonlinearities |     |     |     |     |     |     |     |
| ------- | --- | ------------------------------------------------- | --- | --- | --- | --- | --- | --- | --- |
Their function approximation property makes NNs a useful tool for solving control
problems [10]. It is well known that a two-layer NN is a universal approximator [5].

288 10 Cooperative Adaptive Control for Higher-Order Nonlinear Systems
σ
σ
ϕ
σ
Fig. 10.1 A two-layer neural network
A two-layer NN with v neurons in the hidden layer is depicted in Fig. 10.1 with the
mathematic expression,
z=ϕ(WTσ(VTy)), (10.16)
where y=[y ,…, y ]T is the input vector; σ=[σ,…,σ ]T is the activation func-
1 n 1 v
tion vector for the hidden layer; V ∈n×v is the input layer weights matrix; W ∈v
is the output layer weights vector; and ϕ is the activation function for the output
layer. According to the NN approximation literature [5], for different applications,
a variety of NN activation functions can be selected, such as sigmoids, and Gauss-
ians/radial basis function (RBF). A list of frequently used activation functions can
be found in Fig. 1.1.3 in [10].
To avoid distraction from the main issues being introduced, in this chapter, we
adopt a linear-in-parameters (LIP) NN, i.e., the hidden layer activation functions
σ(⋅) and the input layer weights matrix V are fixed, the output layer activation
i
function is simply a summation function, and only the output weights W are tuned.
The following development can be extended to a two-layer nonlinear-in-parameters
NN as in [10].
It is assumed that the unknown nonlinearity f (x) in system (10.1) can be ex-
i i
pressed on a prescribed compact set, Ω⊂M, by
(10.17)

| 10.2  Distributed Control Structure  |     |     |     |     |     |     | 289 |
| ------------------------------------ | --- | --- | --- | --- | --- | --- | --- |
where (cid:31)(x)∈(cid:31)vi  is a suitable set of v  basis functions, W ∈vi is the ideal NN
| i   | i   |     |     | i   |     | i   |     |
| --- | --- | --- | --- | --- | --- | --- | --- |
weights, and   is the NN approximation error. This means that each agent keeps
i
an NN to approximate its own unknown nonlinearities. Note that the notation ϕ is
abused without making confusion.
Remark 10.3 By the Stone–Weierstrass approximation theorem [15], in a com-
pact set Ω, given any positive number ε, there exists a large enough positive inte-
i
ger v*, such that for any v ≥v*, one can always find an ideal weight vector W
| i   |     | i   | i   |     |     |     | i   |
| --- | --- | --- | --- | --- | --- | --- | --- |
and a suitable basis set ϕ(⋅), which makes Eq. (10.17) satisfy the property that
i
| max | | |≤ε.  |     |     |     |     |     | ▋   |
| ------ | ----- | --- | --- | --- | --- | --- | --- |
| xi∈Ω   | i i   |     |     |     |     |     |     |
Assume that the ideal weights vector W  in Eq. (10.17) is unknown. Then, let each
i
node maintain an NN locally to keep track of the current estimates for its unknown
nonlinearities. Since the NNs are maintained locally at each node, they only need
to approximate the local nonlinearities in the dynamics of that node. Therefore, the
number of neurons needed at each node is reduced compared to centralized neural
adaptive control.
| Define the approximation of  |     |     | f (x) as |     |     |     |     |
| ---------------------------- | --- | --- | -------- | --- | --- | --- | --- |
|                              |     |     | i i      |     |     |     |     |
)=WˆT
|     |     |     | fˆ (x | (t)ϕ | (x ), |     | (10.18) |
| --- | --- | --- | ----- | ---- | ----- | --- | ------- |
|     |     |     | i i   | i    | i i   |     |         |

where W(t)∈(cid:31)vi (or   for convenience) is the actual value of the NN weights
i
vector for the i-th node and must be determined using only the local information
available to node i in the graph (in fact, by the distributed NN weights tuning law
(10.23)). Note that fˆ (x ) is the actual output of the NN maintained by node i.
i
i
|     |     |     |     |     |     | ∑ N | vi, and |
| --- | --- | --- | --- | --- | --- | --- | ------- |
Define =[,…, ]T ∈(cid:25)N, ϕ(x)=[ϕT(x ),…,ϕT (x )]T ∈(cid:25) i =1
|     | 1   | N   |     | 1   | 1   | N N |     |
| --- | --- | --- | --- | --- | --- | --- | --- |
|     |     | W  |     |    |     |     |     |
1
|     |     |    |          |    |              |           |     |
| --- | --- | --- | -------- | --- | ------------ | --------- | --- |
|     |     |    | W        |    | ∑           | N        |     |
|     |     |    | 2        |    | ∈(cid:25) i | =1 vi ×N |     |
|     | W   | =   |          |     |              | ,         |     |
|     |     |    | (cid:30) |    |              |           |     |
|     |     |    |          |    |              |           |     |
|     |     |    |          |    |              |           |     |
|     |     |    |          | W  |              |           |     |
|     |     |    |          | N  |              |           |     |
|     |     | Wˆ |          |    |              |           |     |
1
|     |     |    |          |           |     |              |     |
| --- | --- | --- | -------- | ---------- | --- | ------------ | --- |
|     |     |     | Wˆ       |            |  ∑ | N           |     |
|     | Wˆ  |    | 2        | ∈(cid:25) |    | i =1 vi  ×N |     |
|     |     | =   |          |            |     | .            |     |
|     |     |    | (cid:30) |           |     |              |     |
|     |     |    |          |           |     |              |     |
Wˆ
|                                |     |    |                        | N  |     |     |     |
| ------------------------------ | --- | --- | ---------------------- | --- | --- | --- | --- |
| Then, the global nonlinearity  |     |     | f(x) can be written as |     |     |     |     |
(10.19)

and its approximation is
(10.20)

290 10  Cooperative Adaptive Control for Higher-Order Nonlinear Systems
The error of the NN weights vector is defined as
W(cid:31)
=W −W.
It is important to note that matrices W, W, and W are all block diagonal, a fact
that is used later in the proof of Theorem 10.1 to obtain cooperative tuning laws of
distributed form.
| Remark 10.4 Denote  |     |     |     |     |  and W | =||W | ||. According to the  |     |     |
| ------------------- | --- | --- | --- | --- | ------ | ---- | --------------------- | --- | --- |
|                     |     |     |     |     |        | iM   | i                     |     |     |
definitions of (cid:31), W, and , it is observed that there exist positive numbers Φ , W ,
M M
and  , such that ||φ||≤Φ , ||W , and ||||≤ , where ||·||  is the Frobe-
|             |                                   |     |     | || ≤W |     |     | F   |     |     |
| ----------- | --------------------------------- | --- | --- | ----- | --- | --- | --- | --- | --- |
| M           |                                   |     | M   | F M   |     | M   |     |     |     |
| nius norm.  |                                   |     |     |       |     |     |     |     | ▋   |
| 10.2.3      | Distributed Control Law Structure |     |     |       |     |     |     |     |     |
This section presents the structure of the distributed adaptive control protocols u
i
in (10.1). These must be distributed in the sense that they only depend on the local
neighbor information available to each agent. Then, they are allowable in the sense
that they obey the restrictions imposed by the communication graph structure.
To proceed, we require the following standard assumptions.
Assumption 10.2
a. There exists a positive number X >0 such that ||x (t)||≤ X , ∀t≥t .
|     |     |     |     | M   |     | 0   | M   | 0   |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
b. There exists a continuous function g(·):M →, such that | f (t,x )|≤|g(x )|,
|     |     |     |     |     |     |     | 0 0 |     | 0   |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
∈M, ∀t≥t
| ∀x  |     | .   |     |     |     |     |     |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| 0   |     | 0   |     |     |     |     |     |     |     |
c. For each node i, the disturbance   is unknown, but bounded. Thus, the overall
i
global disturbance vector   is also bounded by   where   can be unknown.
Remark 10.5 Since node 0 acts as a command generator, Assumption 10.2 a) is
reasonable in practical applications. According to Assumption 10.2 b), it is straight-
forward to show that there exists a positive number F  such that | f (t,x )|≤F ,
|       |            |          |     |         |     | M     | 0   | 0   | M   |
| ----- | ---------- | -------- | --- | ------- | --- | ----- | --- | --- | --- |
| ∀x ∈Ω | , and ∀t≥t | , whereΩ |     | ={x ∈M | ||x | ||≤ X | }.  |     | ▋   |
| 0 0   |            | 0        |     | 0 0     | 0   | M     |     |     |     |
Remark 10.6 The bounds X ,  , F , W , and   (as in Assumption 10.2 a), c),
|     |     |     | M   | M   | M   | M   |     |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
Remark 10.5 and Remark 10.4, respectively) are actually not used in the controller
design. Thus they do not have to be known. They are only required for the stability
analysis. The bound Φ  (in Remark 10.4) is needed to choose the design parameter
M
c as in condition (10.25). Since generally we can choose some squashing functions
as the basis set, such as sigmoids, Gaussians, and hyperbolic tangents, Φ  can be
M
| explicitly computed.  |     |     |     |     |     |     |     |     | ▋   |
| --------------------- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
According to Remark 10.3, v  neurons are used at each node i. Design the distrib-
i
uted control law for each node i as
1
|     |     |      |       |             | )-WˆT(t)φ(x |     |       | (10.21) |     |
| --- | --- | ---- | ----- | ----------- | ----------- | --- | ----- | ------- | --- |
|     | u   | =    | (λe   | +(cid:31)+λ | e           |     | )+cr, |         |     |
|     | i   | d +b | 1 i,2 | M           |   -1 i,M    | i   | i i i |         |     |
|     |     | i    | i     |             |             |     |       |         |     |

10.3 Distributed Tuning Laws for Cooperative Adaptive Control 291
where c is the control gain. This is a distributed protocol that only depends on local
information available in the graph about node i and its neighbors. This can be writ-
ten collectively for all the agents as
u=(D+B)-1ρ-WˆTφ(x)+cr. (10.22)
Remark 10.7 When M =1 and M =2, the control law (10.21) reduces to the con-
trol law for the first-order nonlinear system and the second-order nonlinear system,
as presented in Chaps. 8 and 9, respectively. ▋
10.3 Distributed Tuning Laws for Cooperative Adaptive
Control
For cooperative adaptive control, both the control law structure and the adaptive
parameter tuning laws must be distributed, that is, they are only allowed to depend
on local neighbor information. A suitable distributed control protocol structure was
developed in the previous section. Developing distributed adaptive tuning laws for a
multi-agent system is a challenge and depends on constructing a suitable Lyapunov
function that captures both the controller design at each node and the communica-
tion graph topology. This is achieved in the proof of the upcoming main theorem
by using both the Graph Lyapunov Equation (10.8) and the Performance Lyapunov
Equation (10.12).
Let the NN parameter adaptive tuning laws be taken as
W (cid:28)ˆ i =-F i ϕ i r i p i (d i +b i )-κF iWˆ i , (10.23)
or collectively as
Wˆ(cid:28) =-FϕrP(D+B)-κFWˆ, (10.24)
where design parameters F = FT ∈vi×vi are arbitrary positive definite matrices
i i
and F =diag{F,...,F }; κ is a positive scalar tuning gain; and P is defined in
1 N
Lemma 10.1. Note the control law (10.21) and NN tuning law (10.23) are imple-
mented using only local information available for node i. As such, they are allow-
able in terms of obeying the communication restrictions imposed by the graph to-
pology.
The main result of this chapter is given by the following theorem. It shows that
under the proposed cooperative control laws and NN tuning laws, the tracking er-
rors δm are CUUB, thereby showing synchronization in the sense of CUUB for
the whole graph . Then, all agents synchronize to the state of the control node
dynamics (10.3).
The result depends on Assumptions 10.1 and 10.2. Interestingly, the former con-
cerns the communication graph topology, while the latter concerns the local agent
dynamics.

292 10  Cooperative Adaptive Control for Higher-Order Nonlinear Systems
Theorem 10.1 Consider the distributed systems (10.1) and the leader node dynam-
ics (10.3). Suppose Assumptions 10.1 and 10.2 hold. Let the distributed control
laws be (10.21) and the distributed NN tuning laws be (10.23). Let the control gain
c satisfy
|     |     |     |        | γ2 |       |     |     |         |
| --- | --- | --- | ------ | --- | ------ | --- | --- | ------- |
|     |     |     | 2      |     | 2      |     |     |         |
|     |     |     | c>     | +   | g2+h , |     |     | (10.25) |
|     |     |     |        |    |       |     |     |         |
|     |     |     | σ(Q)κ |     | β     |     |     |         |

|     |     |     | (σ(P)σ(A) |     |     | )   |     |     |
| --- | --- | --- | --------- | --- | --- | --- | --- | --- |
with γ=-1Φ σ(P)σ(A), g=-1 ||Λ|| ||λ||+σ(P) , and h= σ(P)σ(A) ||λ||
| 2   | M   |     | 2 σ(D+B) |     | F   | 1   |     | σ(D+B) |
| --- | --- | --- | -------- | --- | --- | --- | --- | ------ |
where P is defined in (10.12) for any β>0 and Q is defined as in Lemma 10.1.
1
Then:
1. the tracking errors δm, for all m=1,...,M, are CUUB, which implies that all
nodes in graph  synchronize to the leader node 0 with bounded residual errors.
| 2. the states x(t) are bounded ∀t≥t |     |     |     |  for all i∈. |     |     |     |     |
| ----------------------------------- | --- | --- | --- | ------------- | --- | --- | --- | --- |
|                                     | i   |     |     | 0             |     |     |     |     |
Proof
1. For all i=1,...,N, given fixed positive numbers ε, there exist numbers of neu-
i
rons  v*, such that when  v ≥v*, the NN approximation errors satisfy || ||≤ε.
| i   |     |     | i i |     |     |     |     | i i |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
Then by Remark 10.4, one has ||W || ≤W , ||φ||≤Φ , and ||||≤ .
|     |     |     | F   | M   | M   |     | M   |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
Consider the Lyapunov function candidate
|     |     |     | =V  | +V  | +V  |     |     |         |
| --- | --- | --- | --- | --- | --- | --- | --- | ------- |
|     |     |     | V   |     | ,   |     |     | (10.26) |
|     |     |     |     | 1 2 | 3   |     |     |         |
where V = 1 rTPr, V = 1 tr{W(cid:27)TF-1W(cid:27)}, and V = 1 tr{E P (E )T}.
2
| 1                                     | 2   | 2   |     |     | 3 2 | 1 1 1 |     |     |
| ------------------------------------- | --- | --- | --- | --- | --- | ----- | --- | --- |
| First, we compute the derivative of V |     |     |     | :   |     |       |     |     |
1
|     |     |     |     |     |     |     |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
V(cid:28) =rTPr(cid:28)=rTP[ρ-(L+B)(f(x)+u+ζ-
|     |     |     |     |     |     | f   | )]  | (10.27) |
| --- | --- | --- | --- | --- | --- | --- | --- | ------- |
|     | 1   |     |     |     |     | 0   |     |         |
For notational simplicity, denote  f(x) as  f,  fˆ(x) as  fˆ, and φ(x) as φ in the
sequel. Substituting (10.22) into (10.27), and considering (10.19) and (10.20), and
L= D−A, one has
|     |                |     |     |     |                   |         |     |     |
| --- | -------------- | --- | --- | --- | ----------------- | ------- | --- | --- |
|     | =rTP[ρ-(L+B)(f |     |     |     | +(D+B)-1ρ-        | fˆ+cr)] |     |     |
|     | V(cid:28)      |     | +ζ- | f   |                   |         |     |     |
|     | 1              |     |     | 0   |                   |         |     |     |
|     | =rTP[-(L+B)(f  |     |     |     | fˆ+cr)+A(D+B)-1ρ] |         |     |     |
|     |                |     | +ζ- | f - |                   |         |     |     |
0
|     | =rTP[-(L+B)(W(cid:27)Tφ++ζ- |     |     |     | +cr)+A(D+B)-1ρ] |     |     |     |
| --- | ---------------------------- | --- | --- | --- | --------------- | --- | --- | --- |
f 0
|     | =-rTP(L+B)W(cid:27)φ-rTP(L+B)(+ζ- |     |     |     |     | f ) |     |     |
| --- | ---------------------------------- | --- | --- | --- | --- | --- | --- | --- |
0
-crTP(L+B)r+rTPA(D+B)-1ρ
|     | =-rTP(L+B)(+ζ- |     |     | )-crTP(L+B)r |     |     |     |     |
| --- | --------------- | --- | --- | ------------ | --- | --- | --- | --- |
f
0
-rTP(D+B)W(cid:27)Tφ+rTPAW(cid:27)Tφ+rTPA(D+B)-1ρ.
(10.28)

10.3  Distributed Tuning Laws for Cooperative Adaptive Control  293
xTy=tr{yxT}, ∀x,y∈N, and considering Eq. (10.8), one
Noting the fact that
can write V  as
1
V(cid:28) =-rTP(L+B)(+ζ-
| 1   |     | f 0 ) |     |
| --- | --- | ----- | --- |
1
- crTQr-tr{W(cid:27)TφrTP(D+B)}
2
+tr{W(cid:27)TφrTPA} TPA(D+B)-1ρ.
+r (10.29)

-Wˆ(cid:28) =-Wˆ(cid:28)
(cid:28)(cid:27) =W(cid:28)
Since W , considering (10.24), one has
1
| =-rTP(L+B)(+ζ-      |     | crTQr |     |
| -------------------- | --- | ----- | --- |
| V(cid:28) +V(cid:28) |     | f )-  |     |
| 1 2                  |     | 0 2   |     |
-tr{W(cid:27)TφrTP(D+B)}+tr{W(cid:27)TφrTPA}
+rTPA(D+B)-1ρ-tr{W(cid:27)TF-1Wˆ(cid:28)
}
1
| =- crTQr-rTP(L+B)(+ζ- |     | f   | )   |
| ---------------------- | --- | --- | --- |
0
2
+κtr{W(cid:27)TWˆ}+tr{W(cid:27)TφrTPA}+rTPA(D+B)-1ρ.
(10.30)

Considering (10.14) and (10.11), one can further write Eq.  (10.30) as
1 crTQr-rTP(L+B)(+ζ-
| V(cid:28) +V(cid:28) =-        |     |                          | f ) |
| ------------------------------ | --- | ------------------------ | --- |
| 1 2 2                          |     |                          | 0   |
| +κtr{W(cid:27)TW}-κ||W(cid:27) |     | ||2 +tr{W(cid:27)TφrTPA} |     |
F
+rTPA(D+B)-1EΛTλ+rTPA(D+B)-1rlTλ
(10.31)
   1
Let T = +ζ +F . Then,
M M M M
V(cid:28) +V(cid:28)
1 2
| 1 cσ(Q)||r||2   |     | ||r||-κ||W(cid:27) | ||2 |
| --------------- | --- | ------------------ | --- |
| ≤- +σ(P)σ(L+B)T |     |                    |     |
| 2               |     | M                  | F   |
σ(P)σ(A)
| +Φ σ(P)σ(A)||W(cid:27) | ||  | ||r||+ | ||r||2||l||||λ|| |
| ---------------------- | --- | ------ | ---------------- |
| M                      | F   |        |                  |
σ(D+B)
σ(P)σ(A)
| +||r|| | ||E | || ||Λ|| ||λ||+κW | ||W(cid:27) || |
| ------ | --- | ----------------- | -------------- |
|        | 1   | F F               | M F            |
σ(D+B)

294 10 Cooperative Adaptive Control for Higher-Order Nonlinear Systems
1 σ(P)σ(A) 
=- cσ(Q)- ||λ|| ||r||2 -κ||W(cid:27) ||2
 2 σ(D+B)   F
+Φ σ(P)σ(A)||W(cid:27) || ||r||+κW ||W(cid:27) || +σ(P)σ(L+B)T ||r||
M F M F M
σ(P)σ(A)
+ ||Λ|| ||λ||||E || ||r||.
σ(D+B) F 1 F (10.32)
Next, we compute the derivative of V :
3
1
V(cid:28) 3 = 2 tr{E(cid:28) 1 P 1 (E 1 )T +E 1 P 1 (E(cid:28) 1 )T}=tr{E 2 P 1 (E 1 )T}. (10.33)
Substituting (10.11) into (10.33) and considering (10.12) gives
V(cid:28)
3
=tr{E
1
ΛTP
1
(E
1
)T}+tr{rlTP
1
(E
1
)T}
1
= tr{E (ΛTP +PΛ)(E )T}+tr{rlTP(E )T}
1 1 1 1 1 1
2
β
=- tr{E (E )T}+tr{rlTP(E )T}.
1 1 1 1 (10.34)
2
Thus, noting ||l||=1, one has
β
V(cid:28)
3
≤-
2
||E
1
||2
F
+σ(P
1
)||l||||r||||E
1
||
F
β
=- ||E||2+σ(P)||r||||E|| .
1 F 1 1 F (10.35)
2
Therefore,
1 σ(P)σ(A) 
V(cid:28) ≤- cσ(Q)- ||λ|| ||r||2 -κ||W(cid:27) ||2
 2 σ(D+B)   F
β
- ||E||2+Φ σ(P)σ(A)||W(cid:27)|| ||r||
1 F M F
2
σ(P)σ(A) 
+ ||Λ|| ||λ||+σ(P) ||r||||E ||
 σ(D+B) F 1   1 F
+σ(P)σ(L+B)T ||r||+κW ||W(cid:27)|| . (10.36)
M M F
Let γ=-1Φ σ(P)σ(A),g =-1 (σ(P)σ(A) ||Λ|| ||λ||+σ(P) ) , and h= σ(P)σ(A) ||λ||.
2 M 2 σ(D+B) F 1 σ(D+B)
Then (10.36) is written as
V(cid:28) ≤-zTKz+ωTz=-V (z), (10.37)
z

10.3  Distributed Tuning Laws for Cooperative Adaptive Control  295
where
|     |     |     |        |      | ,||W(cid:27) |            | T   |     |         |
| --- | --- | --- | ------ | ---- | ------------ | ---------- | --- | --- | ------- |
|     |     |     | z=||E |  || |              | || ,||r|| |  , |     | (10.38) |
|     |     |     |        | 1    | F            | F          |     |     |         |
β
0 g
| 2  |     |    |     |     |     |     |     |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
]T.
| K =0 | κ γ,µ= | 1   | cσ(Q)-h, and ω=[0,κW |     |     |     | ,σ(P)σ(L+B)T |     |     |
| ----- | ------- | --- | -------------------- | --- | --- | --- | ------------ | --- | --- |
|       |         | 2   |                      |     |     | M   |              | M   |     |
|      |         |    |                      |     |     |     |              |     |     |
| g     | γ µ     |     |                      |     |     |     |              |     |     |
|      |         |    |                      |     |     |     |              |     |     |
V (z) is positive definite if the following conditions C1 and C2 hold:
z
C1) K is positive definite.
||ω||
| C2) ||z||> |     | .   |     |     |     |     |     |     |     |
| ---------- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
σ(K)
| According to Sylvester’s criterion, K |     |     |     |     | >0 if |     |     |     |     |
| ------------------------------------- | --- | --- | --- | --- | ----- | --- | --- | --- | --- |
|                                       |     |     |     |     | β>0,  |     |     |     |     |
(10.39)
|     |     |     |     |     | βκ>0, |     |     |     | (10.40) |
| --- | --- | --- | --- | --- | ----- | --- | --- | --- | ------- |

κ(βµ-2g2)-βγ2
|     |     |     |     |     |     | >0. |     |     | (10.41) |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | ------- |
Solving the above system of equations gives the equivalent condition (10.25). Since
||ω|| >||ω||, condition C2) holds if ||z||≥Bd, where
1
|     |     |     | ||ω|| | σ(P)σ(L+B)T |     |      | +κW |     |         |
| --- | --- | --- | ----- | ----------- | --- | ---- | --- | --- | ------- |
|     |     | Bd  | =     | 1 =         |     | M    | M   | .   | (10.42) |
|     |     |     | σ(K)  |             |     | σ(K) |     |     |         |

Therefore, under conditions (10.25), one has
|     |     |     | V  |          |            |     |     |     | (10.43) |
| --- | --- | --- | --- | -------- | ---------- | --- | --- | --- | ------- |
|     |     |     |     | ≤−V (z), | ∀||z||≥Bd, |     |     |     |         |
|     |     |     |     | z        |            |     |     |     |         |
with V (z) being a continuous positive definite function.
z
A straightforward computation of (10.26) implies
|               |     |        | σ(Γ)||z||2≤V |     | ≤σ(T)||z||2, |        |         |         | (10.44)    |
| ------------- | --- | ------ | ------------ | --- | ------------ | ------ | ------- | ------- | ---------- |
|               |     | (σ(P ) | 1 σ(P))      |     |              | (σ(P ) | 1 σ(P)) |         |            |
| where  Γ=diag |     | 1 ,    | ,            | ,   | T =diag      | 1 ,    | ,       | . Then  | following  |
|               |     | 2      | 2σ(F)        | 2   |              | 2      | 2σ(F)   | 2       |            |
Theorem 4.18 in [7], one can draw the conclusion that for any initial value z(t ) (or
0
| equivalently V(t |     | )), there exists a time T |     |     | , such that |     |     |     |     |
| ---------------- | --- | ------------------------- | --- | --- | ----------- | --- | --- | --- | --- |
|                  |     | 0                         |     |     | 0           |     |     |     |     |
σ(T)
|     |     |     | ||z(t)||≤ |     | B d, | ∀t≥t | +T . |     | (10.45) |
| --- | --- | --- | --------- | --- | ---- | ---- | ---- | --- | ------- |
|     |     |     |           |     |      | 0    | 0    |     |         |
σ(Γ)

296 10 Cooperative Adaptive Control for Higher-Order Nonlinear Systems
Let k =min V (z). Then using essentially the same development as in [7], it
||z||≥Bd z
can be shown that
V(t )-σ(T)Bd2
T = 0 . (10.46)
0
k
By definition of z, (10.45) implies that r(t) is ultimately bounded. Hence r(t)
i
(∀i∈) is ultimately bounded. Then by Lemma 10.3, e(t) is ultimately bounded,
i
which implies that em(t) (∀m=1,…,M) is ultimately bounded. Then, following
Lemma 10.2, the synchronization errors δm(t) are CUUB and all nodes in graph
 synchronize, in the sense of Definition 10.1, to the trajectory x (t) of the leader
0
node.
2. It can be shown that the states x(t) are bounded ∀t≥t for all i∈. In fact,
i 0
inequality (10.37) implies
V(cid:28) ≤-σ(K)||z||2 +||ω||||z||. (10.47)
Then combining (10.44) and (10.47) gives
d σ(K) ||ω||
( V)≤- V + . (10.48)
dt 2σ(T) 2 σ(Γ)
Thus, V(t) is bounded ∀t≥t by Corollary 1.1 in [3]. Since (10.26) implies
0
||r||2≤ 2V(t) , there follows the boundedness of r(t), ∀t≥t . By Lemma 10.2 and
σ(P) 0
Lemma 10.3, it is straightforward that δm(t) is also bounded. Noting δm = xm -x
0,m
and considering Assumption 10.2 a), one can see that xm(t), ∀m=1,…,M, is
bounded all the time, i.e., x(t) is bounded, ∀i∈. In other words, x(t) is con-
i i
tained in compact sets Ω for all t≥t , ∀i∈. □
i 0
For higher-order synchronization of cooperative systems, the interplay between
node dynamics and graph structure is more complicated than that for the first- and
second-order cases. This is reflected in the fact that two Lyapunov equations are
involved in the stability analysis. One is for the individual node controller design
(Eq. (10.12)), and the other for the graph structure (Eq. (10.8)).
Remark 10.8 Finite-time convergence Inequality (10.45) and Eq. (10.38) imply
that the sliding mode error r reaches a bounded neighborhood of the origin in finite
i
time T given in (10.46). With the help of Lemma 10.2 and Lemma 10.3, it can be
0
shown that the tracking error δ reaches the final bound in finite time. ▋
i
Remark 10.9 Design issues The parameters p >0 in adaptive tuning laws
i
(10.23) depend on the graph topology through equations (10.6) and (10.7) which
require global information. However, the design parameter F is an arbitrary posi-
i
tive definite matrix, which implies pF is an arbitrary positive definite matrix. This
i i
finally implies that one can pick an arbitrary positive number p >0 for the NN
i
tuning law. Therefore, the proposed controller u is completely distributed, as one
i

| 10.4  Simulation Example  |     |     |     |     | 297 |
| ------------------------- | --- | --- | --- | --- | --- |
Fig. 10.2  Topology of the
|     |     | (cid:19) | (cid:24) | (cid:20) (cid:20) | (cid:21) |
| --- | --- | -------- | -------- | ----------------- | -------- |
augmented graph 
(cid:21)
|     |     | (cid:24) |     | (cid:22) | (cid:23) |
| --- | --- | -------- | --- | -------- | -------- |
|     |     | (cid:24) |     | (cid:23) | (cid:22) |
can see from (10.21) and (10.23). It is also worth noting that although Eq. (10.42)
is the worst case for the ultimate error bound, it provides a practical design tool
for adaptive higher-order synchronization. This bound shows relations between the
graph topology and the control design parameters in reducing the error bound.  ▋
Remark 10.10 Graph Lyapunov Equation and Performance Lyapunov Equa-
tion This proof verifies the performance of the cooperative control laws and the
adaptive tuning laws, both of which are distributed in the sense of depending only
on local neighborhood information. This is accomplished by carefully constructing
the Lyapunov function in the proof to depend on both the Graph Lyapunov Equa-
tion (10.8) and the Performance Lyapunov Equation (10.12). The former appears in
| Lyapunov function V |  and the latter in V |     | .   |     | ▋   |
| ------------------- | -------------------- | --- | --- | --- | --- |
|                     | 1                    |     | 3   |     |     |
Remark 10.11 It is well known in the literature of NN control [3, 10] that the size
of the compact set Ω in Remark 10.3 is not needed for the controller design. It is
commonly assumed to be as large as desired in practical applications, such that state
x  will stay inside Ω, i.e., Ω ⊂Ω, ∀t≥t . In this sense, the results obtained in this
| i   | i   |     | 0   |     |     |
| --- | --- | --- | --- | --- | --- |
chapter are semiglobal. In the case where Remark 10.3 and Remark 10.4 hold for all
| x ∈M, the results will be global.  |     |     |     |     | ▋   |
| ----------------------------------- | --- | --- | --- | --- | --- |
i
10.4  Simulation Example
This simulation example shows the effectiveness of the proposed cooperative adap-
tive controller. Consider a five-node digraph  and a leader node 0 as depicted in
Fig. 10.2. Note that this topology satisfies Assumption 10.1. Each node is modeled
by a third-order nonlinear dynamics. Let the dynamics of the leader node 0 be
x(cid:28) = x
0,1 0,2
x(cid:28) = x
0,1 0,2
|     | x(cid:28) =−x −2x |     | +1+3sin(2t)+6cos(2t) |     |     |
| --- | ----------------- | --- | -------------------- | --- | --- |
|     | 0,3 0,2           | 0,3 |                      |     |     |
11
−1)2(x
|     | − (x  | +x  | +4x     | +3x −1). | (10.49) |
| --- | ----- | --- | ------- | -------- | ------- |
|     | 3 0,1 | 0,2 | 0,1 0,2 | 0,3      |         |
|     |       |     |         |          |         |

298 10  Cooperative Adaptive Control for Higher-Order Nonlinear Systems
| Fig. 10.3  State trajectory of  |     | 6   |     |     |     |
| ------------------------------- | --- | --- | --- | --- | --- |
x
| the leader node 0 |     |     |     |     | 0,1 |
| ----------------- | --- | --- | --- | --- | --- |
x 0,2
edon redael eht fo yrotcejart etats 4
x 0,3
2
0
−2
−4
−6
|     |     | 0   | 5   | 10 15 | 20  |
| --- | --- | --- | --- | ----- | --- |
time (second)
This is modified from the FitzHugh–Nagumo model [13], and selected to illustrate
the higher-order feature of our algorithm. These dynamics satisfy Assumption 10.2.
=[3,4,1]T.
Its state trajectory is shown in Fig. 10.3 with initial condition x
0
The follower nodes are described by third-order nonlinear systems,
|     | x(cid:28) | = x     |     |     |     |
| --- | --------- | ------- | --- | --- | --- |
|     |           | i,1 i,2 |     |     |     |
x(cid:28)
|     |           | i,2 = x i,3 |              |     |     |
| --- | --------- | ----------- | ------------ | --- | --- |
|     | x(cid:28) | = f (x )+u  | +ζ, i=1,…,5, |     |     |
|     |           | i,3 i i i   | i            |     |     |
with
|     | x(cid:28) = x  | sin(x )+cos(x | )2+u +ζ | ,       |     |
| --- | -------------- | ------------- | ------- | ------- | --- |
|     | 1,3 1,2        | 1,1           | 1,3 1   | 1       |     |
|     |                | )2x           |         | )3+u    |     |
|     | x(cid:28) =-(x | +0.01x        | -0.01(x | +ζ ,    |     |
|     | 2,3            | 2,1 2,2       | 2,1     | 2,1 2 2 |     |
|     | x(cid:28) = x  | +sin(x )+u    | +ζ ,    |         |     |
|     | 3,3 3,2        | 3,3 3         | 3       |         |     |
-1)2(x
|     | x(cid:28) =-3(x | +x                       | +x +x   | -1)  |         |
| --- | --------------- | ------------------------ | ------- | ---- | ------- |
|     | 4,3             | 4,1 4,2                  | 4,1 4,2 | 4,3  |         |
|     | -x              | -x +0.5sin(2t)+cos(2t)+u |         | +ζ , |         |
|     |                 | 4,2 4,3                  |         | 4 4  |         |
|     | =cos(x          | )+u +ζ .                 |         |      | (10.50) |
|     | x(cid:28) 5,3   | 5,1 5 5                  |         |      |         |

The disturbances ζ  are taken as random and bounded by |ζ |≤2. Note that the
|     | i   |     |     | i   |     |
| --- | --- | --- | --- | --- | --- |
open-loop system of node 2 (without disturbance) exhibits a chaotic behavior for
the initial value x =[0.325,0.5,0]T, as shown in Fig. 10.4; the open-loop system
2
of node 3 has a finite escape time; the open-loop system of node 4 has the same
structure as the leader node dynamics but with different parameters.

| 10.4  Simulation Example  |     |     |     | 299 |
| ------------------------- | --- | --- | --- | --- |
0.5
0
3,2
x
−0.5
−1
1
| 0.5 |     |     |     | 2   |
| --- | --- | --- | --- | --- |
|     | 0   |     | 1   |     |
0
−0.5
−1
|     | −1  | −2  |     |     |
| --- | --- | --- | --- | --- |
|     | x   |     | x   |     |
|     | 2,2 |     | 2,1 |     |
Fig. 10.4  Three-dimensional plot of node 2 with initial value x =[0.325,0.5,0]T
2
x 105
| 6   |     |     |     |     |
| --- | --- | --- | --- | --- |
u
1
u
| 4   |     |     |     | 2   |
| --- | --- | --- | --- | --- |
u
3
u
4
2
u
5
0
u i 80
−2
60
40
−4
20
−6 0
−20
| 2   | 4   | 6   | 8 10 |     |
| --- | --- | --- | ---- | --- |
−8
| 0   | 5   | 10  | 15  | 20  |
| --- | --- | --- | --- | --- |
time (second)
Fig. 10.5  Control signals u
i

300 10  Cooperative Adaptive Control for Higher-Order Nonlinear Systems
| Fig. 10.6  Node positions in  | 6   |     |     |     |
| ----------------------------- | --- | --- | --- | --- |
| vector x1                     |     |     |     | x   |
1,1
x 2,1
noitisop :1x yrotcejart etats labolg 5
x 3,1
x 4,1
|     | 4   |     |     | x   |
| --- | --- | --- | --- | --- |
5,1
x
0,1
3
2
1
0
|     | 0   | 2 4 | 6 8 | 10  |
| --- | --- | --- | --- | --- |
time (second)
| Fig. 10.7  Node velocities in  | 14  |     |     |     |
| ------------------------------ | --- | --- | --- | --- |
| vector x2                      |     |     |     | x   |
1,2
|     | 12  |     |     | x   |
| --- | --- | --- | --- | --- |
2,2
|     | yticolev :2x yrotcejart etats labolg |     |     | x   |
| --- | ------------------------------------ | --- | --- | --- |
3,2
|     | 10  |     |     | x   |
| --- | --- | --- | --- | --- |
4,2
x
|     | 8   |     |     | 5,2 |
| --- | --- | --- | --- | --- |
x 0,2
6
4
2
0
−2
−4
|     | 0   | 2 4 | 6 8 | 10  |
| --- | --- | --- | --- | --- |
time (second)
Let x (0)=[3,4,1]T,x (0)=[4,1.6,0.9]T,x (0)=[0.325,0.5,0]T, x (0)=[0.4,0,-1]T,
| 0   | 1   | 2   | 3   |     |
| --- | --- | --- | --- | --- |
(0)=[1,1,0]T, and  (0)=[5,-3,2]T. In the simulation, it is observed that
| x   | x   |     |     |     |
| --- | --- | --- | --- | --- |
| 4   | 5   |     |     |     |
NNs with only a small number of neurons give good performance. In this ex-
ample, six neurons are used for each NN. The NN weights are initialized to be
(0)=[0,0,0,0,0,0]T, ∀i. Sigmoid basis functions are used. Design parameter
Wˆ
i
λ =100,λ =20,c=600,κ=0.01,F =2000I  are chosen and p is chosen arbi-
| 1 2 |     | i   |     |     |
| --- | --- | --- | --- | --- |
i
trarily in the NN adaptive tuning law (10.23), as long as it is positive.
The control signals are shown in Fig. 10.5. As one can see, the control force
is very large initially. This is reasonable, because the NN maintained by each fol-
lower node has no prior knowledge of the nonlinear systems and it takes time to
learn the unknown nonlinearities. The state trajectories for each node are shown in

| 10.4  Simulation Example       |     |     |     |     | 301 |
| ------------------------------ | --- | --- | --- | --- | --- |
| Fig. 10.8  Node accelerations  |     | 30  |     |     |     |
x
| in vector x3 |     |     |     |     | 1,3 |
| ------------ | --- | --- | --- | --- | --- |
x
|     |     | noitarelecca :3x yrotcejart etats labolg 20 |     |     | 2,3 |
| --- | --- | ------------------------------------------- | --- | --- | --- |
x
3,3
x
|     |     | 10  |     |     | 4,3 |
| --- | --- | --- | --- | --- | --- |
x
5,3
|     |     | 0   |     |     | x   |
| --- | --- | --- | --- | --- | --- |
0,3
−10
−20
−30
−40
−50
|     |     | 0 2 | 4 6 | 8   | 10  |
| --- | --- | --- | --- | --- | --- |
time (second)
|     | 3   |     |     |     |     |
| --- | --- | --- | --- | --- | --- |
x 10−5
δ 1,1
|     | 2.5 | 1   |     |     |     |
| --- | --- | --- | --- | --- | --- |
δ
2,1
|                              | 2   |     |     | δ   |     |
| ---------------------------- | --- | --- | --- | --- | --- |
| 1,i                          |     | 0   |     | 3,1 |     |
| δ   srorre gnikcart noitisop |     |     |     | δ   |     |
4,1
1.5
δ
|     |     | −1  |     | 5,1 |     |
| --- | --- | --- | --- | --- | --- |
1
0.5
−2
|     |     | 5 10 | 15 20 |     |     |
| --- | --- | ---- | ----- | --- | --- |
0
−0.5
−1
−1.5
−2
|     | 0   | 0.5 1 1.5 | 2 2.5 | 3   |     |
| --- | --- | --------- | ----- | --- | --- |
time (second)
Fig. 10.9  Error components of global position disagreement vector δ1
Figs. 10.6–10.8. Fast tracking ability can be observed. Further, note that the track-
ing errors δ1,δ2, and δ3 do not go to zero, but are bounded by small residual er-
rors. These are shown in Figs. 10.9–10.11. These figures demonstrate the efficiency
of the proposed algorithm in guaranteeing synchronization despite the presence of
complex unknown dynamics.

302 10  Cooperative Adaptive Control for Higher-Order Nonlinear Systems
| 8   |     |     |     |
| --- | --- | --- | --- |
δ
1,2
6
δ 2,2
δ
| 4   |     |     | 3,2 |
| --- | --- | --- | --- |
2,i
| δ   srorre gnikcart yticolev |     |     | δ   |
| ---------------------------- | --- | --- | --- |
4,2
| 2   |     |     | δ   |
| --- | --- | --- | --- |
5,2
0
x 10−5
5
−2
−4
0
−6
−8
−5
|     | 5 10 | 15  | 20  |
| --- | ---- | --- | --- |
−10
| 0 0.5 | 1 1.5 | 2 2.5 | 3   |
| ----- | ----- | ----- | --- |
time (second)
Fig. 10.10  Components of global velocity disagreement vector δ2
|            |     |     |     |
| ---------- | --- | --- | --- |
40
x 10−4
δ 1,3
δ
| 30  |     |     | 2,3 |
| --- | --- | --- | --- |
| 3,i | 2   |     |     |
δ
| δ   srorre gnikcart noitarelecca | 1   |     | 3,3 |
| -------------------------------- | --- | --- | --- |
δ
| 20  |     |     | 4,3 |
| --- | --- | --- | --- |
0
δ
|     | −1  |     | 5,3 |
| --- | --- | --- | --- |
10
−2
|     | 5 10 | 15 20 |     |
| --- | ---- | ----- | --- |
0
−10
−20
−30
| 0 0.5 | 1 1.5 | 2 2.5 | 3   |
| ----- | ----- | ----- | --- |
time (second)
Fig. 10.11  Components of global acceleration disagreement vector δ3

References 303
References
1. Das A, Lewis FL (2010) Distributed adaptive control for synchronization of unknown nonlin-
ear networked systems. Automatica 46(12):2014–2021
2. Das A, Lewis FL (2011) Cooperative adaptive control for synchronization of second-order
systems with unknown nonlinearities. Int J Robust Nonlinear Control 21(3):1509–1524
3. Ge SS, Wang C (2004) Adaptive neural control of uncertain MIMO nonlinear systems. IEEE
Trans Neural Netw 15(3):674–692
4. Ge SS, Zhang J (2003) Neural network control of non-affine nonlinear systems with zero
dynamics by state and output feedback. IEEE Trans Neural Netw 14(4):900–918
5. Hornik K, Stinchcombe M, White H (1989) Multilayer feedforward networks are universal
approximators. Neural Networks 2(5):359–366
6. Jiang F, Wang L, Jia Y (2009) Consensus in leaderless networks of high-order-integrator
agents. In: Proc. Amer. Control Conf., St. Louis, MO, pp. 4458–4463
7. Khalil HK (2002) Nonlinear systems, 3rd edn. Prentice Hall, Upper Saddle River
8. Khoo S, Xie L, Man Z (2009) Robust finite-time consensus tracking algorithm for multirobot
systems. IEEE Trans Mechatron 14(2):219–228
9. Lewis FL, Yesildirek A, Liu K (1996) Multilayer neural net robot controller with guaranteed
tracking performance. IEEE Trans Neural Netw 7(2):388–399
10. Lewis FL, Jagannathan S, Yesildirek A (1999) Neural Network Control of Robot Manipula-
tors and Nonlinear Systems. Taylor and Francis, London
11. Qu Z (2009) Cooperative Control of Dynamical Systems: Applications to Autonomous Vehi-
cles. Springer, London
12. Ren W, Moore KL, Chen Y (2007) High-order and model reference consensus algorithms in
cooperative control of multivehicle systems. J Dyn Syst Meas Control 129(5):678–688
13. Rinzel J (1987) A formal classification of bursting mechanisms in excitable systems. In:
Teramoto E, Yamaguti M (eds) Mathematical Topics in Population Biology, Morphogenesis
and Neurosciences Springer-Verlag, Berlin Heidelberg
14. Shivakumar PN, Chew KH (1974) A sufficient condition for nonvanishing of determinants.
Proc Amer Math Soc 43(1):63–66
15. Stone MH (1948) The generalized Weierstrass approximation theorem. Math Mag 21
(4/5):167–184/237–254
16. Wang J, Cheng D (2007) Consensus of multi-agent systems with higher order dynamics. In:
Proc. Chinese Control Conf., Zhangjiajie, Hunan, pp 761–765
17. Zhang H, Lewis FL (2012) Adaptive cooperative tracking control of higher-order nonlinear
systems with unknown dynamics. Automatica 48(7):1432–1439
18. Zhang H, Lewis FL, Das A (2011) Optimal design for synchronization of cooperative systems:
state feedback, observer and output feedback. IEEE Trans Autom Control 56(8):1948–1952

Index
A Distributed control, 34
Activation function, 206, 240, 263, 288 Distributed observer (see cooperative
Admissible policy, 189 observer)
Agent, 4, 24, 281 Double-integrator, 55
Algebraic graph theory, 24–34 Duality, 90, 127
Algebraic Riccati equation (ARE),
control, 83, 112 E
observer, 89, 125 Edge (see arc), 4, 25
Arc, 4, 25 set, 4
Auxiliary control, 239 weight, 5
Average consensus, 42 Eigenstructure, 28
Exosystem (see command generator,
B leader node)
Bellman equation, 189
Brunovsky form, 260, 261, 281 F
Fiedler eigenvalue, 33
C Formation control, 60
Center of gravity, 46 Frobenius form, 64
Command generator, 77
Communication graph, 4 G
Consensus, 6, 35 Gain margin region, 112, 124
Convergence region, 124 Game theory, 182
Cooperative control, 23 Generalized Laplacian potential, 226
Cooperative dynamic regulator, 91, 128 Geršgorin circle criterion, 29
Cooperative observer, 87, 121 Global neighborhood error, 242
Cooperative regulator, 19, 77 Global performance objective, 188
Cooperative tracker, 19, 109 Graph, 4, 25
Cooperative tracking, 77 augmented, 78, 284
Cooperative uniform ultimate boundedness balanced, 25, 26
(CUUB) (see UUB) bidirectional, 25
Coupled Hamilton-Jacobi (HJ) equations, 195 connected, 25
Coupled Riccati equations, 196 detail balanced, 144
Cross-weighting, 168, 169, 171 diameter, 5
directed, 25
D distance, 17, 18
Directed tree, 25 random, 12
Disagreement error, 81 strongly connected, 25
Discrete-time Riccati equation, 112 undirected, 25
F. L. Lewis et al., Cooperative Control of Multi-Agent Systems, 305
Communications and Control Engineering, DOI 10.1007/978-1-4471-5574-4,
© Springer-Verlag London 2014

306 Index
volume, 26 Neighbor set, 5
weight balanced, 26 Neighborhood
channel capacity, 121 collision, 5
Lyapunov equation, 284 interaction, 5
Graphical game, 183, 187 Neural network (NN), 240, 288
approximation error, 240, 289
I action, 207
In-degree, 25 critic, 206
Inertial system, 253 linear in parameters (LIP), 288
Node, 4, 24
child, 25
K
control (see command generator)
Kronecker product, 44, 54
follower, 77
leader (see command generator)
L
parent, 25
Laplacian potential, 155, 222, 223, 225
root, 25
Leaderless consensus, 19
Leadership, 8
O
Linear time-invariant system (LTI),
Observer error, 123
continuous-time, 53, 77, 158, 184
Optimal
discrete-time, 109
inverse, 149–153
Local performance objective, 188
cooperative control, 153
Lower triangularly complete, 64
cooperative regulator, 153, 158, 168, 172
Linear quadratic regulator (LQR), 142
cooperative tracker, 156, 161, 170, 175
Output disagreement, 122, 128
M
Output synchronization, 231
Mahler measure, 121
Manifold
P
compact, 144
Partial stability, 144–147
e neighborhood, 145
Passive system, 231
neighborhood, 145
Path
noncompact, 144
directed, 25
Matrix
undirected (see directed path), 31, 38
adjacency, 26
Performance criterion, 148–152
column Laplacian, 225
Performance Lyapunov equation, 286
connectivity (see adjacency), 26
Perron-Frobenius Theorem, 65
cyclic, 65
Persistence of excitation (PE), 208
graph, 110
Phase transition, 12, 14
in-degree, 81, 108, 184
Pinning gain, 80, 122, 156
irreducible, 63
Policy evaluation, 182, 202
Laplacian, 26
Policy improvement, 182, 202
M-matrix, 66
Policy iteration (PI), 200–211
out-degree, 225
simple Laplacian, 166
stochastic, 65 R
weighted graph, 110 Reinforcement learning (RL), 182
Motion Control, 238 Reverse digraph, 90
Motion invariants, 45 Reynolds rules, 3
Multiplayer games, 180 Riccati equation (see Algebraic Riccati
equation)
N
Nash equilibrium S
global, 190 Scale-free network, 15
interactive, 192 Second-order consensus, 55
Neighbor, 4 Shape dynamics, 46, 47

Index 307
Single-integrator, 35, 153, 229 U
Sliding mode error, 263, 285 Uniform ultimate boundedness (UUB), 207,
Small-world network, 13–15 242, 266, 282
Spanning tree, 25, 29, 64, 66, 123
Synchronization, 1–8, 77–79, 84–86, 91, V
109, 153 Vertex/vertices, 25
control, 185, 238
error, 185, 237,283
W
region, 85, 112, 124
Weierstrass theorem, 241, 266
T
Topological entropy, 121
Two-mass-spring system, 97