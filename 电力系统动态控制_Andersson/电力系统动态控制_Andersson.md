| Dynamics | and          | Control  | of  |
| -------- | ------------ | -------- | --- |
| Electric | Power        | Systems  |     |
| Lecture  | 227-0528-00, | ITET ETH |     |
G¨oran Andersson
| EEH | - Power Systems | Laboratory |     |
| --- | --------------- | ---------- | --- |
ETH Zu¨rich
|     | February 2012 |     |     |
| --- | ------------- | --- | --- |

ii

Contents
Preface v
1 Introduction 1
1.1 Control Theory Basics - A Review . . . . . . . . . . . . . . . 2
1.1.1 Simple Control Loop . . . . . . . . . . . . . . . . . . . 2
1.1.2 State Space Formulation . . . . . . . . . . . . . . . . . 5
1.2 Control of Electric Power Systems . . . . . . . . . . . . . . . 5
1.2.1 General considerations . . . . . . . . . . . . . . . . . . 5
2 Frequency Dynamics in Electric Power Systems 9
2.1 Dynamic Model of the System Frequency . . . . . . . . . . . 9
2.1.1 Dynamics of the Generators . . . . . . . . . . . . . . . 9
2.1.2 Frequency Dependency of the Loads . . . . . . . . . . 14
2.2 Dynamic Response of Uncontrolled Power System . . . . . . . 17
2.3 The Importance of a Constant System Frequency . . . . . . . 18
2.4 Control Structures for Frequency Control . . . . . . . . . . . 18
3 Primary Frequency Control 21
3.1 Implementation of Primary Control in the Power Plant. . . . 21
3.2 Static Characteristics of Primary Control . . . . . . . . . . . 23
3.2.1 Role of speed droop depending on type of power system 24
3.3 Dynamic Characteristics of Primary Control . . . . . . . . . . 27
3.3.1 Dynamic Model of a One-Area System . . . . . . . . . 27
3.3.2 Dynamic Response of the One-Area System . . . . . . 29
3.3.3 Extension to a Two-Area System . . . . . . . . . . . . 31
3.3.4 Dynamic Response of the Two-Area System . . . . . . 33
3.4 Turbine Modelling and Control . . . . . . . . . . . . . . . . . 36
3.4.1 Turbine Models . . . . . . . . . . . . . . . . . . . . . . 36
3.4.2 Steam Turbine Control Valves . . . . . . . . . . . . . 45
3.4.3 Hydro Turbine Governors . . . . . . . . . . . . . . . . 46
3.5 Dynamic Responses including Turbine Dynamics . . . . . . . 47
iii

iv Contents
4 Load Frequency Control 51
4.1 Static Characteristics of AGC . . . . . . . . . . . . . . . . . . 51
4.2 Dynamic Characteristics of AGC . . . . . . . . . . . . . . . . 54
4.2.1 One-area system . . . . . . . . . . . . . . . . . . . . . 54
4.2.2 Two-area system – unequal sizes – disturbance response 56
4.2.3 Two-area system, unequal sizes – normal control op-
eration . . . . . . . . . . . . . . . . . . . . . . . . . . . 58
4.2.4 Two-area system – equal sizes, including saturations
– disturbance response . . . . . . . . . . . . . . . . . . 60
5 Synchronous Machine Model 61
5.1 Park’s Transformation . . . . . . . . . . . . . . . . . . . . . . 61
5.2 The Inductance Matrices of the Synchronous Machine . . . . 65
5.3 Voltage Equations for the Synchronous Machine. . . . . . . . 67
5.4 Synchronous, Transient, and Subtransient Inductances . . . . 70
5.5 Time constants . . . . . . . . . . . . . . . . . . . . . . . . . . 74
5.6 Simplified Models of the Synchronous Machine . . . . . . . . 76
5.6.1 Derivation of the fourth-order model . . . . . . . . . . 76
5.6.2 The Heffron-Phillips formulation for stability studies . 79
6 Voltage Control in Power Systems 85
6.1 Relation between voltage and reactive power . . . . . . . . . 85
6.2 Voltage Control Mechanisms . . . . . . . . . . . . . . . . . . 87
6.3 Primary Voltage Control . . . . . . . . . . . . . . . . . . . . . 88
6.3.1 Synchronous Machine Excitation System and AVR . . 88
6.3.2 Reactive Shunt Devices . . . . . . . . . . . . . . . . . 93
6.3.3 Transformer Tap Changer Control . . . . . . . . . . . 94
6.3.4 FACTS Controllers . . . . . . . . . . . . . . . . . . . . 95
6.4 Secondary Voltage Control . . . . . . . . . . . . . . . . . . . . 99
7 Stability of Power Systems 101
7.1 Damping in Power Systems . . . . . . . . . . . . . . . . . . . 101
7.1.1 General . . . . . . . . . . . . . . . . . . . . . . . . . . 101
7.1.2 Causes of Damping . . . . . . . . . . . . . . . . . . . . 102
7.1.3 Methods to Increase Damping . . . . . . . . . . . . . . 103
7.2 Load Modelling . . . . . . . . . . . . . . . . . . . . . . . . . . 104
7.2.1 The Importance of the Loads for System Stability . . 104
7.2.2 Load Models . . . . . . . . . . . . . . . . . . . . . . . 104
References 110
A Connection between per unit and SI Units for the Swing
Equation 113
B Influence of Rotor Oscillations on the Curve Shape 115

Preface
These lectures notes are intended to be used in the lecture Dynamics and
Control of Power Systems (Systemdynamik und Leittechnik der elektrischen
Energieversorgung) (Lecture 227-0528-00, D-ITET, ETH Zu¨rich) given at
ETH Zu¨rich in the Master Programme of Electrical Engineering and Infor-
mation Technology.
The main topic covered is frequency control in power systems. The
needed models are derived and the primary and secondary frequency con-
trol are studied. A detailed model of the synchronous machine, based on
Park’s transformation, is also included. The excitation and voltage control
of synchronous machines are briefly described. An overview of load models
is also given.
Zu¨rich, February 2012
G¨oran Andersson
v

vi Preface

1
Introduction
In this chapter a general introduction to power systems control is given.
Some basic results from control theory are reviewed, and an overview of the
| use of different | kinds of power           | plants in | a system is given. |
| ---------------- | ------------------------ | --------- | ------------------ |
| The main         | topics of these lectures | will be   |                    |
| Power            | system dynamics          |           |                    |
•
| Power | system control |     |     |
| ----- | -------------- | --- | --- |
•
| Security | and operational | efficiency. |     |
| -------- | --------------- | ----------- | --- |
•
In order to study and discuss these issues the following tools are needed
| Control | theory (particularly | for linear | systems) |
| ------- | -------------------- | ---------- | -------- |
•
Modelling
•
Simulation
•
| Communication | technology. |     |     |
| ------------- | ----------- | --- | --- |
•
ThestudiedsystemcomprisesthesubsystemsElectricityGeneration, Trans-
mission, Distribution, and Consumption (Loads), andtheassociated control
system has a hierarchic structure. This means that the control system con-
sists of a number of nested control loops that control or regulate different
quantities in the system. Ingeneral the control loops on lower system levels,
e.g. locally in a generator, are characterized by smaller time constants than
the control loops active on a higher system level. As an example, the Auto-
matic Voltage Regulator (AVR),whichregulates thevoltage ofthegenerator
terminals to the reference (set) value, responds typically in a time scale of a
second or less, while the Secondary Voltage Control, which determines the
reference values of the voltage controlling devices, among which the genera-
tors, operates inatimescale of tensof seconds orminutes. Thatmeans that
these two control loops are virtually de-coupled. This is also generally true
forother controls inthesystems,resultinginanumberofde-coupledcontrol
loops operating in different time scales. A schematic diagram showing the
| different time | scales is shown | in Figure | 1.1. |
| -------------- | --------------- | --------- | ---- |
1

2 1. Introduction
Tie Line Power and
Frequency Control
Turbine Control
Voltage Control
Protection
1/10 1 10 100 Time (s)
Figure 1.1. Schematic diagram of different time scales of power system controls.
The overall control system is very complex, but due to the de-coupling
it is in most cases possible to study the different control loops individually.
This facilitates the task, and with appropriate simplifications one can quite
often use classical standard control theory methods to analyse these con-
trollers. For a more detailed analysis, one usually has to resort to computer
simulations.
Acharacteristic ofapower system isthattheload, i.e.theelectric power
consumption, varies significantly over the day and over the year. This con-
sumption is normally uncontrolled. Furthermore, since substantial parts of
the system are exposed to external disturbances, the possibility that lines
etc. could be disconnected due to faults must be taken into account. The
taskofthedifferentcontrolsystemsofthepowersystemistokeepthepower
system within acceptable operating limits such that security is maintained
and that the quality of supply, e.g. voltage magnitudes and frequency, is
within specified limits. In addition, the system should be operated in an
economically efficient way. This has resulted in a hierarchical control sys-
tem structure as shown in Figure 1.2.
1.1 Control Theory Basics - A Review
The de-coupled control loops described above can be analyzed by standard
methods from the control theory. Just to refresh some of these concepts,
and to explain the notation to be used, a very short review is given here.
1.1.1 Simple Control Loop
The control system in Figure 1.3 is considered. In this figure the block G(s)
representsthecontrolled plantandalsopossiblecontrollers. Fromthisfigure

| 1.1. | Control | Theory | Basics | -   | A Review |     |     |
| ---- | ------- | ------ | ------ | --- | -------- | --- | --- |
3
System Control Center
State Estimation
Power Flow Control
Economic Dispatch
Security Assessment
NETWORK
|     |     | Generation          |     | Power Transmission  |                   |     | Loads |
| --- | --- | ------------------- | --- | ------------------- | ----------------- | --- | ----- |
|     |     | (In Power Stations) |     |                     | And Distribution  |     |       |
Tap Changer Control
Turbine Control
|     |     |                 |     | (Direct and Quadature)  |     | Normally not  |     |
| --- | --- | --------------- | --- | ----------------------- | --- | ------------- | --- |
|     |     | Voltage Control |     |                         |     | controlled    |     |
Reactive Power
Compensation
HVDC, FACTS
Figure 1.2. The structure of the hierarchical control systems of a power system.
1
| the | following | quantities | are   | defined | :       |     |     |
| --- | --------- | ---------- | ----- | ------- | ------- | --- | --- |
|     | r(t)=     | Reference  | (set) | value   | (input) |     |     |
•
|     | e(t) | = Control | error |     |     |     |     |
| --- | ---- | --------- | ----- | --- | --- | --- | --- |
•
|     | y(t) | = Controlled | quantity |     | (output) |     |     |
| --- | ---- | ------------ | -------- | --- | -------- | --- | --- |
•
|     | v(t) | = Disturbance |     |     |     |     |     |
| --- | ---- | ------------- | --- | --- | --- | --- | --- |
•
Normally the controller is designed assuming that the disturbance is equal
to zero, but to verify the robustness of the controller realistic values of v
| must | be            | considered. |           |          |     |               |                 |
| ---- | ------------- | ----------- | --------- | -------- | --- | ------------- | --------------- |
|      | In principle  | two         | different | problems |     | are solved in | control theory: |
|      | 1. Regulating | problem     |           |          |     |               |                 |
|      | 2. Tracking   | problem     |           |          |     |               |                 |
1Herethequantitiesinthetimedomainaredenotedbysmallletters,whiletheLaplace
transformed corresponding quantitiesare denotedbycapital letters. Inthefollowing this
conventionisnotalwaysadheredto,butitshouldbeclearfromthecontextifthequantity
s
| is  | expressed | in thetime | or the | domain. |     |     |     |
| --- | --------- | ---------- | ------ | ------- | --- | --- | --- |

1. Introduction
4
v

|     |     | r   |     | e   |     | y   |     |
| --- | --- | --- | --- | --- | --- | --- | --- |
+
|     |     |     | Σ   |     | G(s)  |     |     |
| --- | --- | --- | --- | --- | ----- | --- | --- |
_

H(s)
|     | Figure | 1.3. | Simple | control | system with | control signals. |     |
| --- | ------ | ---- | ------ | ------- | ----------- | ---------------- | --- |
In the regulating problem, the reference value r is normally kept constant
P
and the task is to keep the output close to the reference value even if dis-
turbances occur in the system. This is the most common problem in power
systems, where the voltage, frequency, and other quantities should be kept
at the desired values irrespective of load variations, line switchings, etc.
In the tracking problem the task is to control the system so that the
output y follows the time variation of the input r as good as possible. This
| is sometimes | also | called | the | servo | problem. |     |     |
| ------------ | ---- | ------ | --- | ----- | -------- | --- | --- |
The transfer function from the input, R, to the output, Y, is given by
| (in Laplace | transformed |       | quantities) |     |                 |      |       |
| ----------- | ----------- | ----- | ----------- | --- | --------------- | ---- | ----- |
|             |             |       | Y(s)        |     | C(s)            | G(s) |       |
|             |             | F(s)= |             | =   | =               |      | (1.1) |
|             |             |       | R(s)        |     | R(s) 1+G(s)H(s) |      |       |
In many applications one is not primarily interested in the detailed time
responseofaquantity afteradisturbance,butratherthevaluedirectly after
the disturbance or the stationary value when all transients have decayed.
Then the two following properties of the Laplace transform are important:
|     |     |     | g(t | 0+)= | lim sG(s) |     | (1.2) |
| --- | --- | --- | --- | ---- | --------- | --- | ----- |
|     |     |     |     | →    | s→∞       |     |       |
and
|     |     |     | g(t |     | )= limsG(s) |     | (1.3) |
| --- | --- | --- | --- | --- | ----------- | --- | ----- |
|     |     |     |     | → ∞ | s→0         |     |       |
where G is the Laplace transform of g. If the input is a step function,
Laplace transform = 1/s, and F(s) is the transfer function, the initial and
| stationary | response |     | of the output |     | would be   |     |       |
| ---------- | -------- | --- | ------------- | --- | ---------- | --- | ----- |
|            |          |     | y(t           | 0+) | = lim F(s) |     | (1.4) |
|            |          |     |               | →   | s→∞        |     |       |
and
|     |     |     | y(t |     | ) = limF(s) |     | (1.5) |
| --- | --- | --- | --- | --- | ----------- | --- | ----- |
|     |     |     |     | → ∞ | s→0         |     |       |

1.2. Control of Electric Power Systems 5
1.1.2 State Space Formulation
A linear and time-invariant controlled system is defined by the equations
x˙ = Ax+Bu
(1.6)

y = Cx+Du

The vector x = (x1 x2 ...x
n
)T contains the states of the system, which
uniquely describe the system. The vector u has the inputs as components,
and the vector y contains the outputs as components. The matrix A, of
dimension n n, is the system matrix of the uncontrolled system. The
×
matricesB,C,andDdependonthedesignofthecontrollerandtheavailable
outputs. In most realistic cases D = 0, which means that there is zero
feedthrough, and the system is said to be strictly proper. The matrices A
and B define which states are controllable, and the matrices A and C define
which states are observable. A controller using the outputs as feedback
signals can be written as u = Ky = KCx, assuming D = 0, where the
− −
matrix K defines the feedback control, the controlled system becomes
x˙ = (A BKC)x (1.7)
−
1.2 Control of Electric Power Systems
1.2.1 General considerations
The overall control task in an electric power system is to maintain the bal-
ance between the electric power produced by the generators and the power
consumed by the loads, including the network losses, at all time instants.
If this balance is not kept, this will lead to frequency deviations that if too
large will have serious impacts on the system operation. A complication is
that the electric power consumption varies both in the short and in the long
time scales. Inthe longtime scale, over theyear, the peak loads of aday are
incountries withcold anddark wintershigher inthewinter, socalled winter
peak, while countries with very hot summers usually have their peak loads
in summer time, summer peak. Examples of the former are most European
countries, and of the latter Western and Southern USA. The consumption
varies also over the day as shown in Figure 1.4. Also in the short run the
load fluctuates around the slower variations shown in Figure 1.4, so called
spontaneous load variations.
In addition to keeping the above mentioned balance, the delivered elec-
tricity must conform to certain quality criteria. This means that the voltage
magnitude, frequency, and wave shape must be controlled within specified
limits.
If a change in the load occurs, this is in the first step compensated by
the kinetic energy stored in the rotating parts, rotor and turbines, of the

|     |     |     |     |     |     |     |     |     | 1. Introduction |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --------------- | --- |
6
|     | 100 |     |     |     |     |     | 120          |     |     |     |
| --- | --- | --- | --- | --- | --- | --- | ------------ | --- | --- | --- |
|     | 80  |     |     |     |     |     | 100 weekdays |     |     |     |
weekdays
80
|     | %)   |     |     |          |     | %)  |     |     | h o l i d a y s |     |
| --- | ---- | --- | --- | -------- | --- | --- | --- | --- | --------------- | --- |
|     | 60   |     |     | holidays |     |     |     |     |                 |     |
|     | d (  |     |     |          |     | d ( |     |     | h o l i d a y s |     |
|     | a    |     |     |          |     | a   | 60  |     |                 |     |
|     | o    |     |     |          |     | o   |     |     |                 |     |
|     | L 40 |     |     |          |     | L   |     |     |                 |     |
40
20
20
|     | 0      |        |             |       |            |      | 0      |       |            |       |
| --- | ------ | ------ | ----------- | ----- | ---------- | ---- | ------ | ----- | ---------- | ----- |
|     |        |        |             |       |            |      | 1      | 4 7   | 10 13 16   | 19 22 |
|     |        | 1 4    | 7 10        | 13 16 | 19 22      |      |        |       |            |       |
|     |        |        | Time        |       |            |      |        |       | Time       |       |
|     | Figure | 1.4.   | Typical     | load  | variations | over | a day. | Left: | Commercial |       |
|     | load.; | Right: | Residential |       | load.      |      |        |       |            |       |
generators resulting in a frequency change. If this frequency change is too
large,thepowersuppliedfromthegeneratorsmustbechanged,whichisdone
through the frequency control of the generators in operation. An unbalance
in the generated and consumed power could also occur as a consequence of
that a generating unit is tripped due to a fault. The task of the frequency
control is to keep the frequency deviations within acceptable limits during
these events.
To cope with the larger variations over the day and over the year gener-
ating units must be switched in and off according to needs. Plans regarding
which units should be on line during a day are done beforehand based on
2
load forecasts . Such a plan is called unit commitment. When making such
a plan, economic factors are essential, but also the time it takes to bring a
generator on-line from a state of standstill. For hydro units and gas tur-
bines this time is typically of the order of some minutes, while for thermal
power plants, conventional or nuclear, it usually takes several hours to get
the unit operational. This has an impact on the unit commitment and on
| the | planning | of  | reserves | in  | the system | 3 . |     |     |     |     |
| --- | -------- | --- | -------- | --- | ---------- | --- | --- | --- | --- | --- |
Depending on how fast power plants can be dispatched, they are clas-
sified as peak load, intermediate load, or base load power plants. This
classification is based on the time it takes to activate the plants and on the
2With the methods available today one can make a load forecast a day ahead which
| normally |     | has an | error that | is less | than a | few percent. |     |     |     |     |
| -------- | --- | ------ | ---------- | ------- | ------ | ------------ | --- | --- | --- | --- |
3Inasystemwhereonlyonecompanyisresponsibleforthepowergeneration,theunit
commitmentwasmadeinsuchawaythatthegeneratingcostswereminimized. Ifseveral
powerproducersarecompetingonthemarket,liberalizedelectricitymarket,thesituation
ismorecomplex. Thecompetingcompaniesarethenbiddingintodifferentmarkets,pool,
bi-lateral, etc, and a simple cost minimizing strategy could not be applied. But also in
| thesecases |     | a unit | commitment | must | bemade, | but | according | to  | otherprinciples. |     |
| ---------- | --- | ------ | ---------- | ---- | ------- | --- | --------- | --- | ---------------- | --- |

1.2. Control of Electric Power Systems 7
4
fuelcosts and is usually doneas below . Theclassification is not uniqueand
might vary slightly from system to system.
Peak load units, operational time 1000–2000 h/a
•
– Hydro power plants with storage
– Pumped storage hydro power plants
– Gas turbine power plants
Intermediate load units, operational time 3000–4000 h/a
•
– Fossil fuel thermal power plants
– Bio mass thermal power plants
Base load units, operational time 5000–6000 h/a
•
– Run of river hydro power plants
– Nuclear power plants
In Figure 1.5 the use of different power plants is shown in a load duration
curve representing one year’s operation.
The overall goal of the unit commitment and the economic dispatch is
the
Minimization of costs over the year
•
Minimization of fuel costs and start/stop costs
•
4Thefuelcostsshouldherebeinterpretedmoreasthe“value”ofthefuel. Forahydro
power plant the “fuel” has of course no cost per se. But if the hydroplant has a storage
with limited capacity, it is obvious that the power plant should beused during high load
conditionswhengeneratingcapacityisscarce. Thismeansthatthe“watervalue”ishigh,
which can be interpreted as a high fuel cost.

8 1. Introduction
System Load
Gas turbines
Hydro power reserves
Thermal power (fossil fuel)
Controllable hydro power
Nuclear power
Run of river hydro power
Time
1 year
Figure 1.5. Duration curve showing the use of different kinds of power plants.

2
Frequency Dynamics in Electric Power
Systems
In this chapter, the basic dynamic frequency model for a large power system
is introduced. It is based on the swing equation for the set of synchronous
machines in the system. Certain simplifications lead to a description of the
dominant frequency dynamics by only one differential equation which can
be used for the design of controllers. Also of interest is the frequency de-
pendency of the load in the system, which has a stabilizing effect on the
frequency. Note that no control equipment is present yet in the models pre-
sented in this chapter: the system is shown in ”open loop” in order to un-
derstand the principal dynamic behaviour. Control methods are presented in
the subsequent chapters.
2.1 Dynamic Model of the System Frequency
In order to design a frequency control methodology for power systems, the
elementary dynamic characteristics of the system frequency have to be un-
derstood. For this purpose, a simplified model of a power system with sev-
eral generators (synchronous machines) will be derived in the sequel. The
nominal frequency is assumed to be 50 Hz as in the ENTSO-E Continen-
tal Europe system (former UCTE). Generally, deviations from this desired
valueariseduetoimbalances betweentheinstantaneousgenerationandcon-
sumption of electric power, which has an accelerating or decelerating effect
on the synchronous machines.
2.1.1 Dynamics of the Generators
After a disturbance in the system, like a loss of generation, the frequency
in different parts of a large power system will vary similar to the exemplary
illustration shown in Figure 2.1. The frequencies of the different machines
canberegardedas comparatively smallvariations over anaverage frequency
in the system. This average frequency, called the system frequency, is the
frequencythat can bedefinedfor theso–called centre of inertia (COI)of the
system.
We want to derive a model that is valid for reasonable frequency devia-
tions. For this purpose, the exact version of the swing equation will be used
9

10 2. Frequency Dynamics in Electric Power Systems
50
49.8
49.6
49.4
49.2
49
48.8
0 1 2 3 4 5
)zH(f
t(s)
Figure 2.1. The frequency in different locations in an electric power
system after a disturbance. The thicker solidcurve indicates the aver-
age system frequency. Other curves depict the frequency of individual
generators.
to describe the dynamic behaviour of generator i:
ω0
ω˙ = (T (p.u.) T (p.u.)) , (2.1)
i mi ei
2H −
i
with the usual notation. The indices m and e denote mechanical (turbine)
and electrical quantities respectively. ω is the absolute value of the rotor
i
angular frequency of generator i. The initial condition for eq. (2.1), the
pre-disturbance frequency, is normally the nominal frequency ω
i
(t0) = ω0.
Of main interest is usually the angular frequency deviation ∆ω :
i
∆ω
i
= ω
i
ω0 . (2.2)
−
By deriving eq. (2.2) with respect to the time, one obtains ∆ω˙ = ω˙ . Note
i i
that for rotor oscillations the frequency of ∆ω is often of interest, while the
i
amplitude of ∆ω is the main concern in frequency control. Also note that
i
for the initial condition ∆ω
i
(t0) = 0 holds if eq. (2.1) is formulated for ∆ω.
In order to convert the torques in eq. (2.1) to power values, the relation
P(p.u.) = T(p.u.) ω is used, which yields:
ω0
2
ω
0
∆ω˙ = (P (p.u.) P (p.u.)) , (2.3)
i mi ei
2H ω −
i i
Thepower can also beexpressed in SI–units (e.g. in MW instead of p.u.) by
multiplication with the power base S , which represents the rated power of
Bi

2.1. Dynamic Model of the System Frequency 11
Pset
m
P P
m e
T G
Generator
P
load
Turbine
Load
Figure 2.2. Simplified representationof a power systemconsisting of
a single generator connected to the same bus as the load.
the generator i. Furthermore, eq. (2.3) can be rewritten such that the unit
on both sides is MW:
2H
i
S
Bi
ω0
∆ω˙ = (P P ) . (2.4)
i mi ei
ω0 ω
i
−
Note that this is still the exact version of the swing equation, which is
nonlinear. For further details on different formulations of the swing equa-
tion, please refer to Appendix A. Now, the goal is to derive the differential
equation for the entire system containing n generators. In a highly meshed
system,allunitscanbeassumedtobeconnectedtothesamebus,represent-
ing the centre of inertia of the system. With further simplifications, they
can even becondensed into one single unit. An illustration of this modelling
is depicted in Figure 2.2. A summation of all the equations (2.4) for the n
generators in the system yields
n n
1 ω0
2 H S ∆ω˙ = (P P ) . (2.5)
i Bi i mi ei
i=1
ω0
i=1
ω
i
−
X X
Because of the strong coupling of the generation units, ω = ω can be as-
i

|     |     |     | 2.  | Frequency |     | Dynamics |     | in Electric | Power | Systems |
| --- | --- | --- | --- | --------- | --- | -------- | --- | ----------- | ----- | ------- |
12
P
m
|     |     | a   |     | a/b | (cid:90)2 |     |     | 1   | (cid:90)(cid:32)(cid:90) (cid:14)(cid:39)(cid:90) |     |
| --- | --- | --- | --- | --- | --------- | --- | --- | --- | ------------------------------------------------- | --- |
+
|     |     |     | */*  |     | 0   |     |     |     | 0   |     |
| --- | --- | --- | ---- | --- | --- | --- | --- | --- | --- | --- |
|     | –   |     |      |     | 2HS |     |     | s   |     |     |
B
b
P
e
Figure 2.3. Block diagram of nonlinear frequency dynamics as in eq. (2.11).
| sumed | for all | i. By | defining | the | quantities |     |            |           |     |       |
| ----- | ------- | ----- | -------- | --- | ---------- | --- | ---------- | --------- | --- | ----- |
|       |         |       | H        | ω   |            |     |            |           |     |       |
|       |         |       | i        | i i |            |     |            |           |     |       |
|       |         | ω     | =        |     | Centre     |     | of Inertia | frequency |     | (2.6) |
H
i
P
|     |     | S   | = S |     | Total | rating, |     |     |     | (2.7) |
| --- | --- | --- | --- | --- | ----- | ------- | --- | --- | --- | ----- |
|     |     | B   | P   | Bi  |       |         |     |     |     |       |
i
X
|     |     |     | H   | S    |       |         |     |           |     |       |
| --- | --- | --- | --- | ---- | ----- | ------- | --- | --------- | --- | ----- |
|     |     |     | i   | i Bi |       |         |     |           |     |       |
|     |     | H   | =   |      | Total | inertia |     | constant, |     | (2.8) |
S
|     |     |     | P i  | Bi  |       |            |     |        |     |       |
| --- | --- | --- | ---- | --- | ----- | ---------- | --- | ------ | --- | ----- |
|     |     | P   | = PP |     | Total | mechanical |     | power, |     | (2.9) |
|     |     | m   |      | mi  |       |            |     |        |     |       |
i
X
|     |     | P   | = P |     | Total | electrical |     | power, |     | (2.10) |
| --- | --- | --- | --- | --- | ----- | ---------- | --- | ------ | --- | ------ |
|     |     | e   |     | ei  |       |            |     |        |     |        |
i
X
the principal frequency dynamics of the system can be described by the
| nonlinear | differential |     | equation |     |     |     |     |     |     |     |
| --------- | ------------ | --- | -------- | --- | --- | --- | --- | --- | --- | --- |
2
ω
|     |     |     | ∆ω˙ | =   | 0   | (P  | P   | ) . |     | (2.11) |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | ------ |
|     |     |     |     |     |     | m   | e   |     |     |        |
|     |     |     |     |     | 2HS | ω   | −   |     |     |        |
B
Eq. (2.11) is illustrated as a block diagram in Figure 2.3. For the frequency
| ω in the | centre | of  | inertia | holds | as well   |     |     |     |     |        |
| -------- | ------ | --- | ------- | ----- | --------- | --- | --- | --- | --- | ------ |
|          |        |     |         |       | ω = ω0+∆ω |     | .   |     |     | (2.12) |
In order to obtain a linear approximation of eq. (2.11), ω = ω0 can be
assumed for the right-hand side. This is a valid assumption for realistic
| frequency | deviations |     | in power |     | systems. | This | yields |     |     |     |
| --------- | ---------- | --- | -------- | --- | -------- | ---- | ------ | --- | --- | --- |
ω0
|     |     |     |     | ∆ω˙ = |     | (P  | P ) | .   |     | (2.13) |
| --- | --- | --- | --- | ----- | --- | --- | --- | --- | --- | ------ |
|     |     |     |     |       |     | m   | e   |     |     |        |
|     |     |     |     |       | 2HS | B   | −   |     |     |        |
Thedynamicscan alsobeexpressedintermsof frequencyinstead ofangular
| frequency. | Because |     | of ω | = 2πf | and | ω˙ = 2πf˙ | follows |     |     |     |
| ---------- | ------- | --- | ---- | ----- | --- | --------- | ------- | --- | --- | --- |
f0
|     |     |     |     | ∆f˙= |     | (P  | P ) | .   |     | (2.14) |
| --- | --- | --- | --- | ---- | --- | --- | --- | --- | --- | ------ |
|     |     |     |     |      |     | m   | e   |     |     |        |
|     |     |     |     |      | 2HS |     | −   |     |     |        |
B

| 2.1. Dynamic | Model | of  | the | System | Frequency |     |     |     |     |
| ------------ | ----- | --- | --- | ------ | --------- | --- | --- | --- | --- |
13
A very simple and useful model can be derived if some more assumptions
are made. The overall goal of our analysis is to derive an expression that
gives the variation of ∆ω after a disturbanceof thebalance between P and
m
| P . Therefore, | we  | define |     |     |     |     |     |     |     |
| -------------- | --- | ------ | --- | --- | --- | --- | --- | --- | --- |
e
|     |     |     | P = | P   | = P | m0+∆P |     | ,   | (2.15) |
| --- | --- | --- | --- | --- | --- | ----- | --- | --- | ------ |
|     |     |     | m   |     | mi  |       | m   |     |        |
i
X
where P m0 denotes the mechanical power produced by the generators in
steady state and ∆P denotes a deviation from that value. The total gen-
m
erated power is consumed by the loads and the transmission system losses,
i.e.
|     |     |     | P = | P   | = P | +P   |      | ,   | (2.16) |
| --- | --- | --- | --- | --- | --- | ---- | ---- | --- | ------ |
|     |     |     | e   |     | ei  | load | loss |     |        |
i
X
| which can, | in the | same | way | as in   | eq. (2.15), | be  | written | as  |        |
| ---------- | ------ | ---- | --- | ------- | ----------- | --- | ------- | --- | ------ |
|            |        |      | P = | P e0+∆P |             | +∆P |         |     | (2.17) |
|            |        |      | e   |         | load        |     | loss    |     |        |
with
|               |     |                | P   | = P   | +P    |                  | .   |     | (2.18) |
| ------------- | --- | -------------- | --- | ----- | ----- | ---------------- | --- | --- | ------ |
|               |     |                |     | e0    | load0 | loss0            |     |     |        |
| If the system | is  | in equilibrium |     | prior | to    | the disturbance, |     |     |        |
|               |     |                |     | P     | =P    |                  |     |     | (2.19) |
|               |     |                |     |       | m0    | e0               |     |     |        |
and
|     |     |     | P   | m0 = | P load0 | +P loss0 |     |     | (2.20) |
| --- | --- | --- | --- | ---- | ------- | -------- | --- | --- | ------ |
are valid. Furthermore, the transmission losses after and before the distur-
| bance are | assumed | to  | be equal, | i.e. |        |     |     |     |        |
| --------- | ------- | --- | --------- | ---- | ------ | --- | --- | --- | ------ |
|           |         |     |           | ∆P   | loss = | 0 . |     |     | (2.21) |
If neither the disturbancenor the oscillations in thetransmission system are
too large, these approximations are reasonable. Using eqs. (2.15) – (2.21),
| eq. (2.13) | can now | be  | written | as  |     |     |     |     |     |
| ---------- | ------- | --- | ------- | --- | --- | --- | --- | --- | --- |
ω0
|     |     | ∆ω˙ | =   |     | (∆P | ∆P  | )    | ,   | (2.22) |
| --- | --- | --- | --- | --- | --- | --- | ---- | --- | ------ |
|     |     |     |     |     |     | m   | load |     |        |
|     |     |     |     | 2HS |     | −   |      |     |        |
B
or equivalently
f0
∆f˙=
|     |     |     |     |     | (∆P | m ∆P | load ) | .   | (2.23) |
| --- | --- | --- | --- | --- | --- | ---- | ------ | --- | ------ |
|     |     |     |     | 2HS |     | −    |        |     |        |
B
| Eq. (2.23) | can be | represented |     | by  | the block | diagram |     | in Figure 2.4. |     |
| ---------- | ------ | ----------- | --- | --- | --------- | ------- | --- | -------------- | --- |

|     |     |     | 2.  | Frequency | Dynamics |     | in Electric | Power | Systems |
| --- | --- | --- | --- | --------- | -------- | --- | ----------- | ----- | ------- |
14
(cid:39)P
load
|     |     |     |     | (cid:16) | f   |     | (cid:39)f |     |     |
| --- | --- | --- | --- | -------- | --- | --- | --------- | --- | --- |
0
|     |     |     |     |          | (2HS | )s  |     |     |     |
| --- | --- | --- | --- | -------- | ---- | --- | --- | --- | --- |
|     |     |     |     | (cid:14) |      | B   |     |     |     |
System inertia
(cid:39)P
m
|       | Figure    | 2.4. Linearized |            | model | of the | power     | system frequency | dynamics. |     |
| ----- | --------- | --------------- | ---------- | ----- | ------ | --------- | ---------------- | --------- | --- |
| 2.1.2 | Frequency |                 | Dependency |       | of     | the Loads |                  |           |     |
Loads are either frequency-dependent or frequency-independent. In real
power systems, a frequency dependency of the aggregated system load is
clearly observable. This has a stabilizing effect on the system frequency f,
as will be shown in the sequel. Apart from a component depending directly
on f, large rotating motor loads cause an additional contribution depending
onf˙. Thisisduetothefactthatkineticenergycanbestoredintherotating
| masses | of         | the motors. |          |      |         |          |         |     |        |
| ------ | ---------- | ----------- | -------- | ---- | ------- | -------- | ------- | --- | ------ |
| A      | load model | that        | captures | both | effects | is given | by      |     |        |
|        |            |             | f        | f0   | f       |          | +g(∆f˙) |     |        |
|        |            |             | P        | P =  | ∆P      | = K l    | ∆f      |     | (2.24) |
|        |            |             | load −   | load | load    |          |         |     |        |
where
|     | P f0 | : Load | power | when f | = f0, |     |     |     |     |
| --- | ---- | ------ | ----- | ------ | ----- | --- | --- | --- | --- |
• load
|     | K : Frequency |     | dependency, |     |     |     |     |     |     |
| --- | ------------- | --- | ----------- | --- | --- | --- | --- | --- | --- |
• l
|     | g(∆f˙): | Function | that | models | the | loads | with rotating | masses. |     |
| --- | ------- | -------- | ---- | ------ | --- | ----- | ------------- | ------- | --- |
•
g(∆f˙)
The function will now be derived. The rotating masses have the
| following | kinetic |     | energy: |     |     |     |     |     |     |
| --------- | ------- | --- | ------- | --- | --- | --- | --- | --- | --- |
1
2
|     |     |     |     | W(f)= |     | J(2πf) |     |     | (2.25) |
| --- | --- | --- | --- | ----- | --- | ------ | --- | --- | ------ |
2
The change in the kinetic energy, which is equal to the power P M consumed
| by  | the motor, | is given | by  |     |     |     |     |     |     |
| --- | ---------- | -------- | --- | --- | --- | --- | --- | --- | --- |
dW
|     |     |     |     |     | P M = |     |     |     | (2.26) |
| --- | --- | --- | --- | --- | ----- | --- | --- | --- | ------ |
dt
and
d∆W
|     |     |     |     | ∆P  | =   |     | .   |     | (2.27) |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | ------ |
|     |     |     |     |     | M   | dt  |     |     |        |

| 2.1. Dynamic |     | Model | of the System | Frequency |     |     |     |
| ------------ | --- | ----- | ------------- | --------- | --- | --- | --- |
15
| ∆W can | be approximated |     | by            |     |        |           |     |
| ------ | --------------- | --- | ------------- | --- | ------ | --------- | --- |
|        |                 |     | 2             |     | 2      |           |     |
|        | W(f0+∆f)        |     | = 2π J(f0+∆f) |     | =      |           |     |
|        |                 |     | 2             | 2   | 2      | 2 2       |     |
|        | W0+∆W           |     | = 2π Jf       | +2π | J2f0∆f | +2π J(∆f) |     |
0
|     |     |     |       | 2W0 | W0   | 2    |     |
| --- | --- | --- | ----- | --- | ---- | ---- | --- |
|     |     |     | = W0+ |     | ∆f + | (∆f) |     |
2
|     |     |     |     | f0  | f   | 0   |     |
| --- | --- | --- | --- | --- | --- | --- | --- |
2W0
|     |     | ∆W  |        | ∆f  |     |     |     |
| --- | --- | --- | ------ | --- | --- | --- | --- |
|     |     | ⇒   | ≈ f0   |     |     |     |     |
|     |     |     | 2W0d∆f |     | 2W0 |     |     |
∆f˙
|     |     | ∆P  |        |     | =   |     | (2.28) |
| --- | --- | --- | ------ | --- | --- | --- | ------ |
|     |     | ⇒   | M ≈ f0 | dt  | f0  |     |        |
The frequency dependency of the remaining load can also be written as
|     |     |     | ∂P      |        | 1   |      |        |
| --- | --- | --- | ------- | ------ | --- | ---- | ------ |
|     |     |     | load ∆f | = K ∆f | =   | ∆f . | (2.29) |
l
|     |     |     | ∂f  |     | D   |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- |
l
The values of W0 and D are obviously highly dependent on the structure
l
of the load and can be variable over time. Especially W0 is only a factor
in power systems with large industrial consumers running heavy rotating
machines. The constant D has typical values such that the variation of the
l
| load is | equal to | 0...2 | % per % of | frequency | variation. |     |     |
| ------- | -------- | ----- | ---------- | --------- | ---------- | --- | --- |
Theblock diagram inFigure2.5 represents thedynamicload model. To-
gether with the power system dynamics derived before, we obtain a dynam-
ical system with a ”proportional/differential control” caused by the loads.
However, this effect is too small to be able to keep the frequency within rea-
sonable bounds. As we will see in the next section, the absence of any other
control equipment would lead to unacceptable and remaining frequency de-
| viations | even  | for moderate | disturbances. |     |              |                |     |
| -------- | ----- | ------------ | ------------- | --- | ------------ | -------------- | --- |
| The      | power | system       | model derived | so  | far is shown | in Figure 2.6. |     |

16 2. Frequency Dynamics in Electric Power Systems
1
D
l
(cid:14)
(cid:39)f (cid:39)Pf
load
(cid:14)
2W
0 s
f
0
Figure 2.5. Block diagram of the dynamic load model.
Frequency-dependent loads
(cid:39)P System load change
load
1
D
l
(cid:14) (cid:14)
(cid:39)Pf
load
(cid:14)
(cid:14)
2W
0 s
f (cid:39)P
0 e
Rotating mass loads
(cid:16)
f (cid:39)f
0
(2HS )s
(cid:14) B
System inertia
(cid:39)P Power generation change
m
Figure 2.6. Model of power system without control.

| 2.2. | Dynamic |     | Response | of Uncontrolled |     | Power | System |     |     |     |
| ---- | ------- | --- | -------- | --------------- | --- | ----- | ------ | --- | --- | --- |
17
| 2.2 |     | Dynamic | Response |     | of  | Uncontrolled |     | Power |     | System |
| --- | --- | ------- | -------- | --- | --- | ------------ | --- | ----- | --- | ------ |
Now we will conduct a numerical simulation of the uncontrolled frequency
dynamics after a disturbance. Both loss of generation and loss of load will
beshown,representedbyapositiveresp. negative stepinputonthevariable
∆P load . Table 2.1 displays the parameters used in the simulation. In Figure
2.7, a time plot of the system frequency is shown corresponding to the
different disturbances. Note that this result is purely theoretic as such large
frequency deviations could never occur in a real power system because of
various protection mechanisms. However, it illustrates well the possible
frequency rise or decay and the stabilizing self-control effect caused by the
| frequency |     | dependency | of  | the load. |     |       |      |     |     |     |
| --------- | --- | ---------- | --- | --------- | --- | ----- | ---- | --- | --- | --- |
|           |     |            |     | Parameter |     | Value | Unit |     |     |     |
|           |     |            |     | H         |     | 5     | s    |     |     |     |
|           |     |            |     | S         |     | 10    | GW   |     |     |     |
B
|     |     |     |     | f0  |     | 50  | Hz  |     |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
|     |     |     |     |     |     | 1   | Hz  |     |     |     |
|     |     |     |     | D   | L   | 200 | MW  |     |     |     |
MW
|     |     |     |     | W0  |     | 100 |     |     |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
Hz
|     | Table | 2.1. | Parameters | for | time domain |     | simulation | of power | system. |     |
| --- | ----- | ---- | ---------- | --- | ----------- | --- | ---------- | -------- | ------- | --- |
The plot shows the time evolution of the system frequency for a dis-
| turbance |      | of (top | to bottom) | ∆P   |          | = 1000 | MW, | ∆P    | =   | 500 MW, |
| -------- | ---- | ------- | ---------- | ---- | -------- | ------ | --- | ----- | --- | ------- |
|          |      |         |            |      | load     |        |     | load  |     |         |
|          |      |         |            |      |          | −      |     |       | −   |         |
| ∆P       |      | = 100   | MW (sudden | loss | of load) | and    | ∆P  | = 100 | MW, | ∆P =    |
|          | load | −       |            |      |          |        |     | load  |     | load    |
500MW,∆P load = 1000 MW(suddenincreaseofload orlossofgeneration).
|     |     | 56  |     |     |     |     |     |     |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
−1000 MW
−500 MW
−100 MW
|     |     | 54  |     |     |     |     |     | +100 MW |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- | ------- | --- | --- |
+500 MW
+1000 MW
|     |     | ]zH[ ycneuqerF metsyS 52 |     |     |     |     |     |     |     |     |
| --- | --- | ------------------------ | --- | --- | --- | --- | --- | --- | --- | --- |
50
48
46
44
|     |     | 0   | 10  | 20  |     | 30  | 40  | 50  |     | 60  |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
Time [s]
|     | Figure |     | 2.7. Theoretical |         | frequency | responses | of  | uncontrolled | power |     |
| --- | ------ | --- | ---------------- | ------- | --------- | --------- | --- | ------------ | ----- | --- |
|     | system | (D  | L =1/200         | Hz/MW). |           |           |     |              |       |     |

18 2. Frequency Dynamics in Electric Power Systems
2.3 The Importance of a Constant System Frequency
In the most common case ∆P ∆P is negative after a disturbance, like
m load
−
the tripping of a generator. It is also possible that the frequency rises dur-
ing a disturbance, for example when an area that contains much generation
capacity is isolated. Since too large frequency deviations in a system are
not acceptable, automatic frequency control, which has the goal of keeping
the frequency during disturbances at an acceptable level, is used. Further-
more, the spontaneous load variations in an electric power system result in
a minute–to–minute variation of up to 2%. This alone requires that some
form of frequency control must be used in most systems.
There are at least two reasons against allowing the frequency to deviate
too much from its nominal value. A non–nominal frequency in the system
results in a lower quality of the delivered electrical energy. Many of the
devices that are connected to the system work best at nominal frequency.
Further, too low frequencies (lower than 47 48 Hz) lead to damaging
≈ −
vibrations in steam turbines, which in the worst case have to be discon-
nected. This constitutes an even worse stress on the system and can lead to
a complete power system collapse. In comparison with thermal units, hydro
power plants are more robust and can normally cope with frequencies down
to 45 Hz.
2.4 Control Structures for Frequency Control
In the following two chapters, the control structures that ensure a constant
system frequency of 50 Hz will be described. The automatic control system
consists of two main parts, the primary and secondary control. Tertiary
control, whichismanuallyactivated inordertoreleasetheusedprimaryand
secondary control reserves after a disturbance, is not discussed here. This is
duetothefactthattheutilization oftertiary controlreservesismoresimilar
to the electricity production according to generations schedules (dispatch),
which are based on economic off-line optimizations.
The primary control refers to control actions that are done locally (on
the power plant level) based on the setpoints for frequency and power. The
actual values of these can be measured locally, and deviations from the set
values results in a signal that will influence the valves, gates, servos, etc. in
a primary-controlled power plant, such that the desired active power output
is delivered. In primary frequency control, the control task of priority is
to bring the frequency back to (short term) acceptable values. However,
there remains an unavoidable frequency control error because the control
law is purely proportional. The control task is shared by all generators
participating in the primary frequency control irrespective of the location of
the disturbance. Further explanations follow in chapter 3.

2.4. Control Structures for Frequency Control 19
In the secondary frequency control, also called Load Frequency Control,
thepowersetpointsofthegeneratorsareadjustedinordertocompensatefor
the remaining frequency error after the primary control has acted. Apart
from that, another undesired effect has to be compensated by secondary
control: active power imbalances and primary control actions cause changes
in the load flows on the tie-lines to other areas, i.e. power exchanges not
according to the scheduled transfers. The secondary control ensures by
a special mechanism that this is remedied after a short period of time.
Note that in this control loop the location of the disturbance is considered
when the control action is determined: only disturbances within its own
control zone (area) are ”seen” by the secondary controller. Note that Load
Frequency Control can also be performed manually as in the Nordel power
system. In the ENTSO-E Continental Europe interconnected system, an
automatic scheme is used, which can also be called Automatic Generation
Control. This is further discussed in chapter 4.
The basic control structures described above are depicted in Figure 2.8.
Figure 2.9 shows an illustration of the time spans in which these different
control loops are active after a disturbance. Note that primary and sec-
ondary control are continuously active also in normal operation of the grid
in order to compensate for small fluctuations. Conversely, the deployment
of tertiary reserves occurs less often.
Under-frequencyloadsheddingisaformofsystemprotectionandactson
timescales well under one second. As the activation of this scheme implies
the loss of load in entire regions, it must only be activated if absolutely
necessary in order to save the system. In the ENTSO-EContinental Europe
system, the first load shedding stage is activated at a frequency of 49 Hz,
causing the shedding of about 15 % of the overall load. In many systems,
a rotating scheme for how the load should be shed, if that is necessary, is
devised. Such a scheme is often called rotating load shedding.

|     |     |     | 2.  | Frequency | Dynamics | in  | Electric | Power Systems |
| --- | --- | --- | --- | --------- | -------- | --- | -------- | ------------- |
20
Load Shedding
(emergency control)
|     | (Secondary      |     |            |     | Tie-Line Powers  |     | Electrical system  |     |
| --- | --------------- | --- | ---------- | --- | ---------------- | --- | ------------------ | --- |
|     |  control loop)  |     | Automatic  |     |                  |     |                    |     |
|     |                 |     |            |     |                  |     | (cid:120) Loads    |     |
Generation
|     |     |     |                |     |                   |     | (cid:120) Transmission lines  |     |
| --- | --- | --- | -------------- | --- | ----------------- | --- | ----------------------------- | --- |
|     |     |     | Control (AGC)  |     | System Frequency  |     |                               |     |
|     |     |     |                |     |                   |     | (cid:120) Other generators    |     |
identical for synchronous
|     |     |     |     | machines in steady state  |     |     |     | Power, |
| --- | --- | --- | --- | ------------------------- | --- | --- | --- | ------ |
Frequency
| Setpoint |     | Turbine |     | Valves or  |     |     | Generator  |     |
| -------- | --- | ------- | --- | ---------- | --- | --- | ---------- | --- |
Turbine
| Calculation |     | Governor |     |     | Gates |     |     |     |
| ----------- | --- | -------- | --- | --- | ----- | --- | --- | --- |
Speed
Turbine
| Setpoint from  |     |     |     | Controller |     |     |     |     |
| -------------- | --- | --- | --- | ---------- | --- | --- | --- | --- |
(Internal turbine
power generation
 control loop)
schedule and
tertiary control
(Primary control loop)
Figure 2.8.
|     |     | Basic | structure | of frequency | control | in electric | power | systems. |
| --- | --- | ----- | --------- | ------------ | ------- | ----------- | ----- | -------- |
Power
|     | Primary  |     | Secondary |     | Tertiary |     | Generation   |     |
| --- | -------- | --- | --------- | --- | -------- | --- | ------------ | --- |
|     | Control  |     | Control   |     | Control  |     | Rescheduling |     |
Time
| 30 s     |         |              | 15 min  |           |            | 60 min  |                    |        |
| -------- | ------- | ------------ | ------- | --------- | ---------- | ------- | ------------------ | ------ |
| Figure   | 2.9.    | Temporal     |         | structure | of control | reserve | usage after        | a dis- |
| turbance |         | (terminology |         | according | to ENTSO-E | for     | region Continental |        |
| Europe   | (former |              | UCTE).  |           |            |         |                    |        |

3
Primary Frequency Control
Inthischapter, themechanisms forprimary frequencycontrol are illustrated.
As will be shown, they are implemented entirely on the power plant level. In
an interconnected power system, not all generation units need to have pri-
mary control equipment. Instead, the total amount of necessary primary
control reserves are determined by statistical considerations and the distri-
bution on the power plants can vary. Primary control can also be used in
islanded operation of a single generator. These different applications will be
discussed along with their principal static and dynamic characteristics.
3.1 Implementation of Primary Control in the Power
Plant
For a thermal unit, a schematic drawing of the primary control is shown in
Figure 3.1. The turbine governor (depicted here together with the internal
turbinecontroller) acts on a servomotor in order to adjustthevalve through
which the live steam (coming from the boiler with high pressure and high
temperature) flows to the turbines. In the high pressureturbine, part of the
energy of the steam is converted into mechanical energy. Often the steam is
then reheated before it is injected into a medium pressure or low pressure
turbine, where more energy is extracted from the steam. In practice, these
turbine-generator systems can be very large. In a big thermal unit of rating
1000 MW, the total length of the turbine-generator shaft may exceed 50 m.
The control law, which is shown as a block diagram in Figure 3.2, is a
proportional feedback control. It establishes an affine relation between the
measured frequency and the power generation of the plant in steady state.
Note that the turbine dynamics plays in important role in the overall
dynamical response of the system. However, we will neglect this for the
sake of simplicity in the first three sections of this chapter. In section 3.4.1,
different steam and hydro turbines and their modelling are discussed and
later their effect on the dynamical response will be shown.
Primary control is implemented on a purely local level; there is no co-
ordination between the different units. This is also why the control law
cannot have an integral component: integrators of different power plants
could start ”competing” each other for power production shares, which can
lead to an unpredictable and unreasonable distribution of power generation
on the available plants.
21

|     |     |     |     |     | 3. Primary |     | Frequency | Control |
| --- | --- | --- | --- | --- | ---------- | --- | --------- | ------- |
22
Reheater
Steam
Electricity grid
|        |     |     |     | Mech. |     | Electrical |     |     |
| ------ | --- | --- | --- | ----- | --- | ---------- | --- | --- |
|        |     |     |     | power |     | power      |     |     |
| Boiler |     |     |     |       |     |  G         |     |     |
Steam
|     |  HP  |     | LP  |     |     |     |     |     |
| --- | ---- | --- | --- | --- | --- | --- | --- | --- |
Valve
| Actuation | Control |     |             |     |                 |     |     |     |
| --------- | ------- | --- | ----------- | --- | --------------- | --- | --- | --- |
|           | signals |     |             |     |                 |     | f,P |     |
|           |         |     | Controller/ |     | Measured values |     |     |     |
Servomotor
Governor
f ,P
Reference values
0 0
| Figure    | 3.1. Schematic |        | drawing  | of the   | primary | control | installed    | in  |
| --------- | -------------- | ------ | -------- | -------- | ------- | ------- | ------------ | --- |
| a thermal | unit. HP       | = High | Pressure | Turbine. |         | LP =    | Low Pressure |     |
turbine.
|     |     |     |     |     | P (cid:32)Pset,tot | (cid:14)(cid:72) |     |     |
| --- | --- | --- | --- | --- | ------------------ | ---------------- | --- | --- |
|     |     |     |     |     | m                  | m                |     |     |
Internal
P
| Turbine |     | T   |     |     |     |     | G   | e   |
| ------- | --- | --- | --- | --- | --- | --- | --- | --- |
Turbine shaft
Controller
f
Pset,tot
m
(cid:16)
| (cid:14) | (cid:14)     |     |             |     |                   |      |            |     |
| -------- | ------------ | --- | ----------- | --- | ----------------- | ---- | ---------- | --- |
| Pset     | (cid:39)Pset |     |             |     | (cid:16)(cid:39)f | fset | (cid:32) f |     |
| m0       |              | m K | (cid:32)1/S |     |                   |      | 0          |     |
(cid:14)
Proportional
control law
| Figure   | 3.2. Block | diagram           | describing |     | the primary | control       | law.  | The |
| -------- | ---------- | ----------------- | ---------- | --- | ----------- | ------------- | ----- | --- |
| measured | power      | value corresponds |            | to  | P in        | our notation, | while | in  |
m
| practice | the measurement |     | can be | done on | the | electrical | side. |     |
| -------- | --------------- | --- | ------ | ------- | --- | ---------- | ----- | --- |

| 3.2. Static | Characteristics |     |     | of Primary |     | Control |     |     |     |
| ----------- | --------------- | --- | --- | ---------- | --- | ------- | --- | --- | --- |
23
| 3.2 | Static | Characteristics |     |     | of  | Primary | Control |     |     |
| --- | ------ | --------------- | --- | --- | --- | ------- | ------- | --- | --- |
First, it is of particular interest to study the properties of the primary fre-
quencycontrolinsteady state. Referringtotheblock diagraminFigure3.2,
| the equation |     | describing | the | primary | control | is given | by  |     |     |
| ------------ | --- | ---------- | --- | ------- | ------- | -------- | --- | --- | --- |
1
|           |        |         |         |     | se t    | set,tot)= |       |     |       |
| --------- | ------ | ------- | ------- | --- | ------- | --------- | ----- | --- | ----- |
|           |        | (f0     | f)      | +(P | m 0     | P m       | 0 ,   |     | (3.1) |
|           |        |         | −       | · S |         | −         |       |     |       |
| which     | can be | written | as      |     |         |           |       |     |       |
|           |        |         | f0 f    |     |         | f f0      |       |     |       |
|           | S      | =       | −       | =   |         | −         | Hz/MW | > 0 | (3.2) |
|           |        |         | set,tot |     | set,tot |           |       |     |       |
|           |        | −Pset   | P       |     | −P      | Pset      |       |     |       |
|           |        | m0      | − m     |     | m       | − m0      |       |     |       |
| or in per | unit   | as      |         |     |         |           |       |     |       |
|           |        |         |         |     | f       | f0        |       |     |       |
−
f0
|     |     |     | S   | =   |         | .    |     |     | (3.3) |
| --- | --- | --- | --- | --- | ------- | ---- | --- | --- | ----- |
|     |     |     |     | −P  | set,tot | Pset |     |     |       |
|     |     |     |     |     | m       | m0   |     |     |       |
−
Pset
m0
Under the assumption that the turbine power controller has an integrating
characteristic (ε 0 when t in Figure 3.2), it follows that in steady
|             |     | →set,tot |     | → ∞ |     |     |     |     |     |
| ----------- | --- | -------- | --- | --- | --- | --- | --- | --- | --- |
| state holds | P   | = P      | .   |     |     |     |     |     |     |
|             |     | m m      |     |     |     |     |     |     |     |
The speed droop characteristic, Figure 3.3, yields all possible steady-
set,tot
state operating points (P m , f) of the turbine. The position and slope
se t,
of the straight line can be fixed by the parameters P m 0 f0 and S. We
have chosen to label the horizontal axis with the power P set,tot which for
m
small deviations of the frequency around the nominal value is identical to
the torque T. In the literature the speed droop characteristics is sometimes
| also described |     | by ω | instead | of by | f.  |     |     |     |     |
| -------------- | --- | ---- | ------- | ----- | --- | --- | --- | --- | --- |
f(p.u.)
S(p.u.)
f (p.u.)
0
Pset,tot(p.u.)
|     |     |     |     |     | Pset(p.u.) |     |     | m   |     |
| --- | --- | --- | --- | --- | ---------- | --- | --- | --- | --- |
m0
|     |     | Figure | 3.3. Static | characteristic |     | of primary | control. |     |     |
| --- | --- | ------ | ----------- | -------------- | --- | ---------- | -------- | --- | --- |

|     |     |     |     |     |     | 3. Primary | Frequency |     | Control |
| --- | --- | --- | --- | --- | --- | ---------- | --------- | --- | ------- |
24
| 3.2.1 | Role | of speed | droop | depending |     | on type | of  | power | system |
| ----- | ---- | -------- | ----- | --------- | --- | ------- | --- | ----- | ------ |
We will now study how the frequency control of a generator will act in
three different situations. First, when the generator is part of a large inter-
connected system, and second when the generator is in islanded operation
feeding a load. The third system to be studied is a two machine system.
Generator in Large System If a generator is embedded in a large inter-
connected system, it can be modelled with a very good approximation as
| connected |     | to an infinite | bus. | This | is shown | in Figure | 3.4. |     |     |
| --------- | --- | -------------- | ---- | ---- | -------- | --------- | ---- | --- | --- |
In steady state the frequency is given by the grid frequency f (repre-
G
sentedbytheinfinitebus). Fromthespeeddroopcharacteristics, Figure3.5,
the power produced by the generator can then be determined. The turbine
governor controls thus only the power, not the frequency, see Figure 3.5.
Infinite
Bus
|     |       |     |     | P   | P   | X   |     |     |              |
| --- | ----- | --- | --- | --- | --- | --- | --- | --- | ------------ |
|     |       |     |     | m   | e   | L   |     |     | f (cid:32) f |
| f   | ,Pset | R   | T   | G   |     |     |     |     | G            |
0 m0
U (cid:32)U
G
f ,P
G
|     | Figure | 3.4. | Generator | operating | in  | a large interconnected |     | system. |     |
| --- | ------ | ---- | --------- | --------- | --- | ---------------------- | --- | ------- | --- |
f
|     | f   |     |     |     |     |     | S   |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
0
f
G
f  und Pset are set in the generator
0 m0
|     |     |     | P(cid:32)g(f | )   |     |     |     |     |     |
| --- | --- | --- | ------------ | --- | --- | --- | --- | --- | --- |
G
Pset,tot
m
|     |         |           |             |                 |            | Pset     | Pset,tot(f ) |     |        |
| --- | ------- | --------- | ----------- | --------------- | ---------- | -------- | ------------ | --- | ------ |
|     |         |           |             |                 |            | m0       | m G          |     |        |
|     | Figure  | 3.5.      | Speed droop | characteristics |            | for the  | case when    | the | gener- |
|     | ator is | connected | to an       | infinite        | bus (large | system). |              |     |        |

| 3.2. | Static | Characteristics |     | of Primary | Control |     |     |     |     |
| ---- | ------ | --------------- | --- | ---------- | ------- | --- | --- | --- | --- |
25
Islanded Operation AsdepictedinFigure3.6,thegeneratorfeedsaloadin
islanded operation, which here is assumed to be a purely resistive load. By
a voltage controller the voltage U is kept constant and thus also P . In this
e
case the primary control loop will control the frequency, not the power. The
resulting frequency can be determined from the speed droop characteristics,
Figure 3.7.
|     |         |     |     |     |     | Voltage Control  |     | U2                      |     |
| --- | ------- | --- | --- | --- | --- | ---------------- | --- | ----------------------- | --- |
|     |         |     |     | P   | P   |                  | P   | (cid:32) (cid:32)const. |     |
|     |         |     | T   |     |     |                  |     | e                       |     |
|     | f ,Pset | R   |     | m G | e   |                  |     | R                       |     |
0 m0
|     |     |     |     |     |     |     | U   | R   |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
f,P
|     |     |     | Figure | 3.6. Generator | in  | islanded operation. |     |     |     |
| --- | --- | --- | ------ | -------------- | --- | ------------------- | --- | --- | --- |
f
f
|     |     | 0   |     |     |     |     | S   |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
f
 und Pset are set in the generator
f 0 m0
f (cid:32)h(P)
Pset,tot
m
|     |           |       |          |                       | Pset      | Pset,tot(cid:32)P |        |               |     |
| --- | --------- | ----- | -------- | --------------------- | --------- | ----------------- | ------ | ------------- | --- |
|     |           |       |          |                       |           | m0 m              | e      |               |     |
|     | Figure    | 3.7.  | Speed    | droop characteristics |           | for the case      | when   | the gener-    |     |
|     | ator      | is in | islanded | operation.            |           |                   |        |               |     |
| Two | Generator |       | System   |                       |           |                   |        |               |     |
|     |           |       |          | The two               | generator | system,           | Figure | 3.8, provides | a   |
simple model that is often used to study the interaction between two areas
in a large system. In this model the two generators could represent two
subsystems, and the speed droop is then the sum of all the individual speed
droopsof thegenerators inthetwo subsystems,Figure3.9. With thehelpof
the speed droop characteristics of the two systems, we will determine how a
change in load will be compensated by the two systems. Thus, if we have a
change ∆P of the overall load, what will the changes in P m,1, P m,2, and
load
f be?

26 3. Primary Frequency Control
This will be solved in the following way:
•
Thequantities(P
m
se
0
t
,1
,f0,1,S1)and(P
m
se
0
t
,2
,f0,2,S2)describethespeed
droop characteristics of the two systems g1 and g2.
From these the sum g3 = g1+g2 is formed.
•
•
From the given P
load
we can determine P
m
se
,
t
1
, P
m
se
,
t
2
and f
N
from g3.
Inasimilarway: FromP +∆P canPset +∆Pset,Pset +∆Pset
load load m0,1 m,1 m0,2 m,2
•
and f +∆f be determined, and thus ∆Pset, ∆Pset und ∆f.
N m,1 m,2
All these steps are shown in Figure 3.9.
P m se 0 t ,1 , f 0,1 , S 1 P m se 0 t ,2 , f 0,2 , S 2
P P
m,1 m,2
G G
1 2
(cid:39)P (cid:39)P
m,1 m,2
P (cid:32)P (cid:14)P at f
load m,1 m,2 N
Figure 3.8. Two generator system.
S 1 ,g 1 S 3 ,g 3
f
0,2 S,g
f 2 2
0,1
f
N
f (cid:14)(cid:39)f
N
Pset Pset
m0,1 m0,2
Pset Pset P
m,1 m,2 load
P m se ,1 t(cid:14)(cid:39)P m se ,1 t P m se ,2 t(cid:14)(cid:39)P m se ,2 t P load (cid:14)(cid:39)P load
Figure 3.9. Speed droop characteristics for a two machine system.

| 3.3. Dynamic |     | Characteristics |     | of Primary |     | Control |     |     |     |     |
| ------------ | --- | --------------- | --- | ---------- | --- | ------- | --- | --- | --- | --- |
27
| 3.3 Dynamic |         |       | Characteristics |               |     | of Primary |     | Control |     |     |
| ----------- | ------- | ----- | --------------- | ------------- | --- | ---------- | --- | ------- | --- | --- |
| 3.3.1       | Dynamic | Model |                 | of a One-Area |     | System     |     |         |     |     |
In this section, we are going to extend the dynamic frequency model intro-
duced in Chapter 2 by the primary control loop in the power plants. For an
individualgenerator, the block diagram has been introduced in the previous
section.
| Following |     | the nomenclature |     | introduced |     | in Figure |     | 3.2, | we start | with |
| --------- | --- | ---------------- | --- | ---------- | --- | --------- | --- | ---- | -------- | ---- |
1
|     |     | Pset,tot | =   | Pset+∆Pset |     | = Pset |     | ∆f , |     | (3.4) |
| --- | --- | -------- | --- | ---------- | --- | ------ | --- | ---- | --- | ----- |
|     |     | m        |     | m0         | m   | m0     |     |      |     |       |
− S
whereP set,tot describesthepowersetpointoftheturbineincludingthesched-
m
uled value Pset and the component imposed by primary control. For the
m0
| linearized | consideration |     | of  | the power | system | in  | ∆ quantities, |     | we set |       |
| ---------- | ------------- | --- | --- | --------- | ------ | --- | ------------- | --- | ------ | ----- |
|            |               |     |     | Pset      | ∆Pset  |     |               |     |        |       |
|            |               |     |     | m0        | =      | m0  |               |     |        | (3.5) |
as the steady-state component cancels out against the other steady-state
set,tot
quantities. The remaining question is how a change in ∆P m translates
into an actual mechanical power output change ∆P . Thus, we regard now
m
| the internal | turbine |     | control | loop as | depicted | in  | Figure | 3.10. |     |     |
| ------------ | ------- | --- | ------- | ------- | -------- | --- | ------ | ----- | --- | --- |
Turbine
(cid:39)Pset
|     |     |     | m   | Controller |     |     |     |     |     |     |
| --- | --- | --- | --- | ---------- | --- | --- | --- | --- | --- | --- |
Turbine
(cid:14)
|     |     | (cid:39)Pset (cid:14) |     |     | K   |     |      | (cid:39)P |     |     |
| --- | --- | --------------------- | --- | --- | --- | --- | ---- | --------- | --- | --- |
|     |     | m0                    |     |     | t   |     | G(s) |           | m   |     |
|     |     |                       |     |     | s   |     | t    |           |     |     |
(cid:16)
| Figure    | 3.10.  | Block      | diagram | of the | turbine | and | turbine | control | dynamics. |     |
| --------- | ------ | ---------- | ------- | ------ | ------- | --- | ------- | ------- | --------- | --- |
| From this | figure | it follows |         | that   |         |     |         |         |           |     |
G (s)
|     |     |     |     | t    | ∆Pset(s)+∆Pset(s) |     |     |     |         |       |
| --- | --- | --- | --- | ---- | ----------------- | --- | --- | --- | ------- | ----- |
|     | ∆P  | (s) | =   |      |                   |     |     |     | .       | (3.6) |
|     |     | m   |     |      | 1                 | m0  |     | m   |         |       |
|     |     |     | G t | (s)+ | s                 |     |     |     |         |       |
|     |     |     |     | K    | (cid:2)           |     |     |     | (cid:3) |       |
t
| If the dynamics |     | of the | turbine | is neglected |     | (G t | (s)= | 1), one | obtains |     |
| --------------- | --- | ------ | ------- | ------------ | --- | ---- | ---- | ------- | ------- | --- |
1
|     |     | ∆P  | (s)= |       | ∆Pset(s)+∆Pset(s) |     |     |     | .   | (3.7) |
| --- | --- | --- | ---- | ----- | ----------------- | --- | --- | --- | --- | ----- |
|     |     | m   |      |       | m0                |     | m   |     |     |       |
|     |     |     |      | 1+T s |                   |     |     |     |     |       |
t
Note that the time constant T = (cid:2) 1/K is fairly small compared (cid:3) with the
|     |     |     |     | t   |     | t   |     |     |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
frequencydynamicsofthesystem. Regardingnowonlythefrequencycontrol
(∆Pset
| component |     | =   | 0), we | obtain | in steady | state | as  | before |     |     |
| --------- | --- | --- | ------ | ------ | --------- | ----- | --- | ------ | --- | --- |
m0
1
|     |     |     |     | ∆P  | =   | ∆f . |     |     |     | (3.8) |
| --- | --- | --- | --- | --- | --- | ---- | --- | --- | --- | ----- |
|     |     |     |     | m   | −S  |      |     |     |     |       |

|     |     |     |     |     |     | 3. Primary | Frequency | Control |
| --- | --- | --- | --- | --- | --- | ---------- | --------- | ------- |
28
For the case of n controllers for n generators we obtain analogously for
| controller |     | i   |     |     |     |     |     |     |
| ---------- | --- | --- | --- | --- | --- | --- | --- | --- |
1
|     |     |     | ∆P  | = ∆f |     | i = 1,...,n |     | (3.9) |
| --- | --- | --- | --- | ---- | --- | ----------- | --- | ----- |
mi
−S
i
1
|     |     |     |     | ∆P mi | =   | ∆f  |     | (3.10) |
| --- | --- | --- | --- | ----- | --- | --- | --- | ------ |
− S
i
|     |     |     |     | i   | i   |     |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
|     |     |     |     | X   | X   |     |     |     |
where
|     |     |     |     | ∆P = | ∆P  |     |     | (3.11) |
| --- | --- | --- | --- | ---- | --- | --- | --- | ------ |
|     |     |     |     | m    |     | mi  |     |        |
i
X
| is  | the total | change | in turbine | power. | By defining |     |     |        |
| --- | --------- | ------ | ---------- | ------ | ----------- | --- | --- | ------ |
|     |           |        |            | 1      | 1           |     |     |        |
|     |           |        |            | =      |             |     |     | (3.12) |
|     |           |        |            | S      | S           |     |     |        |
i
i
X
| we  | thus | have |     |     |     |     |     |     |
| --- | ---- | ---- | --- | --- | --- | --- | --- | --- |
1
|     |     |     |     | ∆P m = | ∆f  | .   |     | (3.13) |
| --- | --- | --- | --- | ------ | --- | --- | --- | ------ |
−S
This can be inserted into the dynamic system frequency model derived in
| Chapter |     | 2 as depicted | in  | Figure 3.11. |     |     |     |     |
| ------- | --- | ------------- | --- | ------------ | --- | --- | --- | --- |
Frequency-dependent loads
(cid:39)P System load change
load
1
D
l
|     |     |     | (cid:14) |     | (cid:14) |     |     |     |
| --- | --- | --- | -------- | --- | -------- | --- | --- | --- |
(cid:39)Pf
load
(cid:14)
(cid:14)
2W
|     |     | 0 s |     |     |     |     |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
f
|     |     | 0   |     |     | (cid:39)P |     |     |     |
| --- | --- | --- | --- | --- | --------- | --- | --- | --- |
e
Rotating mass loads
(cid:16)
|     |     |     |     |     |     | f   |     | (cid:39)f |
| --- | --- | --- | --- | --- | --- | --- | --- | --------- |
0
|     |     |     |     |     |     | (2HS | )s  |     |
| --- | --- | --- | --- | --- | --- | ---- | --- | --- |
B
(cid:14)
(cid:39)P
m System inertia
|     |     | 1 (cid:39)Pset |     | 1   |     |     |     |     |
| --- | --- | -------------- | --- | --- | --- | --- | --- | --- |
m
(cid:16)
|     |     | S (cid:14) |     | 1(cid:14)Ts |     |     |     |     |
| --- | --- | ---------- | --- | ----------- | --- | --- | --- | --- |
(cid:14)
t
|     | Primary  |     | (cid:39)Pset | Turbine    |     |     |     |     |
| --- | -------- | --- | ------------ | ---------- | --- | --- | --- | --- |
|     | control  |     | m0           | dynamics/  |     |     |     |     |
control
|     | Figure                  | 3.11. | Dynamic | frequency | model | of the power | system | with |
| --- | ----------------------- | ----- | ------- | --------- | ----- | ------------ | ------ | ---- |
|     | primary-controlledpower |       |         | plants.   |       |              |        |      |

3.3. Dynamic Characteristics of Primary Control 29
3.3.2 Dynamic Response of the One-Area System
Now we are going to study the effect of a disturbance in the system derived
above. Bothlossofgeneration andlossofloadcanbesimulatedbyimposing
a positive or negative step inputon the variable ∆P . A change of the set
load
value of the system frequency f0 is not considered as this is not meaningful
in real power systems.
From the block diagram in Figure 3.11 it is straightforward to derive the
transfer function between ∆P and ∆f (∆Pset = 0):
load m0
1+sT
t
∆f(s)= ∆P (s) (3.14)
− 1 1 2W0 2HS B load
+ (1+sT )+( + )s(1+sT )
t t
S D
l
f0 f0
The step response for
∆P
load
∆P (s)= (3.15)
load
s
is given in Figure 3.12. The frequency deviation in steady state is
∆P ∆P
load load
∆f∞ =
s
li
→
m
0
(s
·
∆f(s))= −
1 1
= −
1
=
−
∆P
load ·
D
R
(3.16)
+
S D D
l R
with
1 1 1
= + (3.17)
D S D
R l
Inordertocalculate an equivalent timeconstant T , T is putto0. This
eq t
can be done since for realistic systems the turbine controller time constant
T is much smaller than the time constant of the frequency dynamics T :
t M
f0 2W0 2HS
B
T T = ( + ) . (3.18)
t M
≪ S
B
f0 f0
This means that the transfer function in eq. (3.14) can be approximated by
a first order function
∆P (s) 1 D ∆P
load R load
∆f(s)= − = − (3.19)
1 S B S B s
+T s 1+T D s
M M R
D
R
f0 f0
or
1 ∆f∞
∆f(s)= (3.20)
S B s
1+T D s
M R
f0
with
S
B
T = T D (3.21)
eq M R
f0
as the equivalent time constant.

|     |     |     |     |     |     | 3.  | Primary | Frequency | Control |
| --- | --- | --- | --- | --- | --- | --- | ------- | --------- | ------- |
30
50
]zH[ ycneuqerF metsyS
49.95
49.9
49.85
49.8
49.75
|     |     | 0 1 | 2   | 3   | 4 5 | 6   | 7   | 8   | 9 10 |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | ---- |

400
]WM[ rewoP 300
 ∆ P
load
|     | 200 |     |     |     |     |     |     |     |  ∆ P |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | ---- |
m
 ∆ P f
load
100
0

|     |     | 0 1 | 2   | 3   | 4 5 | 6   | 7   | 8   | 9 10 |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | ---- |
Time [s]
|     | Figure | 3.12. | Behaviouroftheone-areasystem(noturbinedynamics, |     |     |     |     |     |     |
| --- | ------ | ----- | ----------------------------------------------- | --- | --- | --- | --- | --- | --- |
parameterizedasdescribedintheexamplebelow)afterastepincrease
|     | inload.                  | The | upper plotshowsthe |     | systemfrequency                   |     |     | f. The lowerplot |     |
| --- | ------------------------ | --- | ------------------ | --- | --------------------------------- | --- | --- | ---------------- | --- |
|     | showsthestepfunctionin∆P |     |                    |     | load ,theincreaseinturbinepower∆P |     |     |                  | m , |
∆Pf
|     | and | the frequency-dependent |     |     | load variation |     |     | .   |     |
| --- | --- | ----------------------- | --- | --- | -------------- | --- | --- | --- | --- |
load
Example
|     | S = | 4000 MW |     |     |     |     |     |     |     |
| --- | --- | ------- | --- | --- | --- | --- | --- | --- | --- |
B
•
|     | f0 = | 50 Hz |     |     |     |     |     |     |     |
| --- | ---- | ----- | --- | --- | --- | --- | --- | --- | --- |
•
|     | S =     | 4% = 0.04 | f0 = | 0.04·50 | Hz/MW      | = 1  | Hz/MW |       |     |
| --- | ------- | --------- | ---- | ------- | ---------- | ---- | ----- | ----- | --- |
|     |         |           |      | 4000    |            | 2000 |       |       |     |
|     | •       |           | SB   |         |            |      |       |       |     |
|     | D =     | 1%/1%     | D    | = f0    | = 50 Hz/MW |      | = 1   | Hz/MW |     |
|     | l       |           | l    | SB      | 4000       |      | 80    |       |     |
|     | •       |           | ⇒    |         |            |      |       |       |     |
|     | ∆P load | = 400     | MW   |         |            |      |       |       |     |
•
|     | T M | = 10 s |     |     |     |     |     |     |     |
| --- | --- | ------ | --- | --- | --- | --- | --- | --- | --- |
•
Then follows
1
| ∆f∞ | =   | D ∆P | =    |       |     |     | 400MW | = 0.19 | Hz (3.22) |
| --- | --- | ---- | ---- | ----- | --- | --- | ----- | ------ | --------- |
|     |     | R    | load |       | MW  | MW  |       |        |           |
|     | −   | ·    |      | −2000 | +80 | ·   |       | −      |           |
|     |     |      |      |       | Hz  | Hz  |       |        |           |
and
|     |     |     |      |     | 1      | 4000 | MW  |            |        |
| --- | --- | --- | ---- | --- | ------ | ---- | --- | ---------- | ------ |
|     |     | T = | 10 s |     |        |      |     | = 0.39 s . | (3.23) |
|     |     | eq  | ·    | MW  | MW     | 50   | Hz  |            |        |
|     |     |     | 2000 | Hz  | +80 Hz |      |     |            |        |

3.3. Dynamic Characteristics of Primary Control 31
3.3.3 Extension to a Two-Area System
Up to now we have mostly studied the behaviour of a power system consist-
ing of a single area. If the power system is highly meshed in this case, it can
be represented by a single bus where all units are connected. In practice,
however, a large interconnected power system is always divided into various
”control zones” or ”areas”, corresponding e.g. to countries. Understanding
the interactions between these areas is therefore highly important for the
flawless operation of the entire system. For simplified simulation studies, a
system with two areas can be represented by two single bus systems with a
tie-line in between them. This is depicted in Figure 3.13.
P P P P
m,1 e,1 P e,2 m,2
T12
T 1 G 1 G 2 T 2
P m se 0 t ,1 R 1 po T w ie e - r l i f n lo e w R 2 P m se 0 t ,2
P P
f load,1 load,2 f
1 2
Load 1 Load 2
Area 1 Area 2
Figure 3.13. Simplified representation of a power system with two areas.
In order to adapt our dynamic frequency model accordingly, the power
exchangeP T12 overthetielinebetweentheareas1and2hastobemodelled.
This is given by
U1U2
P T12 = sin(ϕ1 ϕ2) (3.24)
X −
where X is the (equivalent) reactance of the tie line. For small deviations
(U1 and U2 are constant) one gets
∂P T12 ∂P T12 U1U2
∆P T12 = ∆ϕ1+ ∆ϕ2 = cos(ϕ0,1 ϕ0,2)(∆ϕ1 ∆ϕ2)
∂ϕ1 ∂ϕ2 X − −
(3.25)
or
∆P T12 = Pˆ T (∆ϕ1 ∆ϕ2) (3.26)
−
with
Pˆ
T
=
U1U2
cos(ϕ0,1 ϕ0,2) . (3.27)
X −
Byusingthismodel,theblockdiagramofthepowersystemcanbeextended
as shown in Figure 3.14.

|     |     |     | 3. Primary | Frequency | Control |     |
| --- | --- | --- | ---------- | --------- | ------- | --- |
32
Frequency-dependent loads
(cid:39)P
load,1
1
D
l,1
|     | (cid:14) |            | (cid:14)  |     |     |     |
| --- | -------- | ---------- | --------- | --- | --- | --- |
|     |          | (cid:39)Pf | (cid:39)P |     |     |     |
load,1
T12
|     |     | (cid:14) | (cid:14) |     |     |     |
| --- | --- | -------- | -------- | --- | --- | --- |
(cid:14)
2W
0,1s
f
| 0   |     | (cid:39)P |     |     |     |     |
| --- | --- | --------- | --- | --- | --- | --- |
e,1
Rotating mass loads
(cid:16)
f (cid:39)f
|     |     |     |          | 0     | 1   |     |
| --- | --- | --- | -------- | ----- | --- | --- |
|     |     |     | (2H      | S )s  |     |     |
|     |     |     | (cid:14) | 1 B,1 |     |     |
(cid:39)P
|                |     |     | m,1 System inertia  |     |     |     |
| -------------- | --- | --- | ------------------- | --- | --- | --- |
| 1 (cid:39)Pset |     | 1   |                     |     |     |     |
(cid:16) m,1
| S (cid:14) |              | 1(cid:14)T s |     |     |     |     |
| ---------- | ------------ | ------------ | --- | --- | --- | --- |
| 1          | (cid:14)     | t,1          |     |     |     |     |
| Primary    | (cid:39)Pset | Turbine      |     |     |     |     |
| control    | m0,1         | dynamics/    |     |     |     |     |
control
2(cid:83)Pˆ
Frequency-dependent loads
|     |     |     | (cid:39)P |     | T   |     |
| --- | --- | --- | --------- | --- | --- | --- |
|     |     |     | load,2    |     | s   |     |
1
D
l,2
(cid:14)
|     | (cid:14) | (cid:39)Pf | (cid:14) |           |     |           |
| --- | -------- | ---------- | -------- | --------- | --- | --------- |
|     |          |            |          | (cid:39)P |     | (cid:39)P |
|     |          | load,2     |          | T12       |     | T12       |
|     |          | (cid:14)   | (cid:16) |           |     |           |
(cid:16)
(cid:14)
2W
| 0,2 s |     |           |     |     | 2(cid:83)Pˆ |     |
| ----- | --- | --------- | --- | --- | ----------- | --- |
| f     |     |           |     |     | T           |     |
| 0     |     | (cid:39)P |     |     | s           |     |
e,2
Rotating mass loads
|     |     |     | (cid:16) | f (cid:39)f |     |     |
| --- | --- | --- | -------- | ----------- | --- | --- |
|     |     |     |          | 0           | 2   |     |
|     |     |     | (2H      | S )s        |     |     |
|     |     |     | (cid:14) | 2 B,2       |     |     |
(cid:39)P
|     |     |     | m,2 System inertia  |     |     |     |
| --- | --- | --- | ------------------- | --- | --- | --- |
(cid:39)Pset
| 1   |     | 1   |     |     |     |     |
| --- | --- | --- | --- | --- | --- | --- |
(cid:16) m,2
| S (cid:14) |              | 1(cid:14)Ts |     |     |     |     |
| ---------- | ------------ | ----------- | --- | --- | --- | --- |
| 2          | (cid:14)     | t           |     |     |     |     |
| Primary    | (cid:39)Pset | Turbine     |     |     |     |     |
m0,2
| control |     | dynamics/  |     |     |     |     |
| ------- | --- | ---------- | --- | --- | --- | --- |
control
| Figure 3.14. | Two-area | dynamic | model including | tie-line flows. |     |     |
| ------------ | -------- | ------- | --------------- | --------------- | --- | --- |

3.3. Dynamic Characteristics of Primary Control 33
3.3.4 Dynamic Response of the Two-Area System
Forthecaseregardedhere,itisassumedthatoneoftheareasismuchsmaller
than the other. The bigger one of the two areas can then be regarded as an
infinite bus in our analysis. We will now study the behaviour after a load
change in the smaller area, Area 1. The system to be studied is depicted in
Figure 3.15.
Area 1 P Area 2
T12
S ,D ,W S ,D ,W
1 l,1 0,1 2 l,2 0,2
T ,S , f U ,(cid:77) X U ,(cid:77) T ,S , f
M,1 B,1 0 1 1 2 2 M,2 B,2 0
f
1
f (cid:32) f
2 0
Figure 3.15. Model of a two area system. Area 1 is much smaller than Area 2.
As Area 2 is very big (infinite bus) it follows that
T M,2S B2 T M,1S B1
f2 = constant ∆ϕ2 = 0 (3.28)
f0 ≫ f0 ⇒ ⇒
and consequently
∆P T12 = ∆P T21 = Pˆ T ∆ϕ1 =2πPˆ T ∆f1dt (3.29)
−
Z
Without any scheduled generator setpoint changes, i.e. ∆Pset = 0, the
m0,i
following transfer functions apply for a change in the Area 1 system load
∆P load,1(s):
s
∆f1(s) =
2πPˆ +( 1 +
−
1 )s+ T M,1S B,1 s 2
∆P load,1(s)
T
D l,1 S B,1(1+sT t ) f0
(3.30)
2πPˆ
T
∆P T12(s) = ∆f1(s) (3.31)
s
2πPˆ
T
∆P T12(s) =
2πPˆ +( 1 +
−
1 )s+ T M,1S B,1
∆P load,1(s)
T D l,1 S B,1(1+sT t ) f0s2
(3.32)

34 3. Primary Frequency Control
The response for
∆P load,1
∆P load,1(s)= (3.33)
s
is shown if Figure 3.16. The steady state frequency deviation is
∆f1,∞ = lim(s ∆f1(s)) = 0 (3.34)
s→0 ·
and the steady state deviation of the tie line power is
∆P T12,∞ = lim(s ∆P T12(s)) = ∆P load,1 (3.35)
s→0 · −
The infinite bus brings the frequency deviation ∆f1 back to zero. This
is achieved by increasing the tie-line power so the load increase is fully
compensated. While this is beneficial for the system frequency in Area 1,
a new, unscheduled and persisting energy exchange has arisen between the
two areas.
50
49.95
49.9
49.85
0 1 2 3 4 5 6 7 8 9 10
Time [s]
]zH[
ycneuqerF
f
1
f
2
1000
800
600
400
200
0
0 1 2 3 4 5 6 7 8 9 10
Time [s]
rewoP
∆ P
load,1
∆ P
m,1
∆ P
T12
Figure 3.16. StepresponseforthesysteminFigure3.14resp. Figure
3.15. Only primary control is used and the system is parameterized
according to Table 3.1. The upper diagram shows the frequencies f1
in Area 1 and f2 in Area 2. The lower diagram shows the step in the
system load∆P load,1, the turbine power ∆P m,1 and the tie-line power
∆P T21 = ∆P T12.
−

| 3.3. Dynamic | Characteristics | of Primary | Control |     |
| ------------ | --------------- | ---------- | ------- | --- |
35
|     | Parameter | Value | Unit  |     |
| --- | --------- | ----- | ----- | --- |
|     |           | H1    | 5 s   |     |
|     |           | H2    | 5 s   |     |
|     |           | S B,1 | 10 GW |     |
|     |           | S     | 10 TW |     |
B,2
|     |     | f0  | 50 Hz |     |
| --- | --- | --- | ----- | --- |
1 Hz
D l,1
200 MW
1 Hz
D
|     |     | l,2  | 200 TW |     |
| --- | --- | ---- | ------ | --- |
|     |     | W0,1 | 0 MW   |     |
Hz
MW
|     |     | W0,2 | 0   |     |
| --- | --- | ---- | --- | --- |
Hz
1 Hz
S1
5000 MW
|     |     | S2  | 1 Hz |     |
| --- | --- | --- | ---- | --- |
5000 MW
Pˆ
|     |     | 533.33 | MW  |     |
| --- | --- | ------ | --- | --- |
T
|       |                      | ∆P load,1       | 1000 MW    |                 |
| ----- | -------------------- | --------------- | ---------- | --------------- |
| Table | 3.1. Parameters      | for time domain | simulation | of the two-area |
| power | system corresponding | to Figure       | 3.16.      |                 |

36 3. Primary Frequency Control
3.4 Turbine Modelling and Control
This section gives an overview of the modelling of both steam and hydro
turbines, control valves and governors. Their characteristics and behaviour
are also briefly discussed. The aim here is to give an understanding of the
basic physical mechanisms behind these models that are very commonly
used in simulation packages for the study of power systems dynamics. In
thedynamicfrequencymodelofthepowersystemderivedsofar(asdepicted
in Figure 3.11), the linearized dynamic models of the turbines will enter in
the block ”Turbine dynamics/control”.
3.4.1 Turbine Models
Steam Turbines
Figures 3.17, 3.18, and 3.19 show the most common steam turbines and
their models. It is outside the scope of these lecture notes to give a de-
tailed derivation and motivation of these models, only a brief qualitative
discussion will be provided. In a steam turbine the stored energy of high
temperature and high pressure steam is converted into mechanical (rotat-
ing) energy, which then is converted into electrical energy in the generator.
The original source of heat can be a furnace fired by fossil fuel (coal, gas, or
oil) or biomass, or it can be a nuclear reactor.
The turbine can be either tandem compound or cross compound. In
a tandem compound unit all sections are on the same shaft with a single
generator,whileacrosscompoundunitconsistsoftwoshaftseachconnected
to a generator. The cross compound unit is operated as one unit with one
set of controls. Most modern units are of tandem compound type, even if
the crossover compound units are more efficient and have higher capacity.
However, the costs are higher and could seldom be motivated.
The power output from the turbine is controlled through the position
of the control valves, which control the flow of steam to the turbines. The
valve position is influenced by the output signal of the turbine controller.
Following the nomenclature introduced in Figure 3.10, this signal is defined
as
1
∆Pctrl = (∆Pset+∆Pset ∆P ). (3.36)
m T s m0 m − m
t
The delay between the different parts of the steam path is usually modelled
byafirstorderfilterasseeninFigures3.17, 3.18, and3.19. Certainfractions
ofthetotalpowerareextractedinthedifferentturbines,andthisismodelled
by the factors F , F , F , F in the models. Typical values of the
VHP HP IP LP
time constant of the delay between the control valves and the high-pressure
turbine, T , is 0.1 0.4 s. If a re-heater is installed, the time delay is
CH
−
larger, typically T = 4 11 s. The time constant of the delay between
RH
−
theintermediateandlowpressureturbines,T ,isintheorderof0.3 0.6s.
CO
−

3.4. Turbine Modelling and Control 37
Nonreheat Steam Turbines
Control
Valve Valves, Shaft
Position Steam HP
Chest
To Condenser
Linear Model
1
(cid:39)Pctrl (cid:39)P
m 1(cid:14)sT m
CH
Tandem Compound, Single Reheat Steam Turbines
Reheater Crossover
Control
Valves,
Valve
Steam HP IP LP LP Shaft
position
Chest
To Condenser
Linear Model
(cid:54) (cid:54) (cid:39)P
m
F F F
HP IP LP
1 1 1
(cid:39)Pctrl
m 1(cid:14)sT 1(cid:14)sT 1(cid:14)sT
CH RH CO
Figure 3.17. Steam turbine configurations and approximate linear
models. Nonreheat and tandem compound, single reheat configura-
tions.

|     |     |     |     |     |     | 3.  | Primary | Frequency | Control |     |
| --- | --- | --- | --- | --- | --- | --- | ------- | --------- | ------- | --- |
38
Tandem Compound, Double Reheat Steam Turbine
Crossover
|     |     |     |     | Reheater |     | Reheater |     |     |     |     |
| --- | --- | --- | --- | -------- | --- | -------- | --- | --- | --- | --- |
Control
Valves,
| Valve |     |     | VHP |     | HP  |     | IP  | LP  | LP  | Shaft |
| ----- | --- | --- | --- | --- | --- | --- | --- | --- | --- | ----- |
Steam
position
Chest
To Condenser
|     |     |     |     |     | (cid:54) |     | (cid:54) |     | (cid:54) | (cid:39)P |
| --- | --- | --- | --- | --- | -------- | --- | -------- | --- | -------- | --------- |
m
Linear Model
|     |     | F   |     | F   |     |     | F   |     | F   |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
|     |     | VHP |     |     | HP  |     | IP  |     | HP  |     |
|     | 1   |     | 1   |     |     | 1   |     | 1   |     |     |
(cid:39)Pctrl
| m       | 1(cid:14)sT |       | 1(cid:14)sT |        |                | 1(cid:14)sT    |     | 1(cid:14)sT |        |     |
| ------- | ----------- | ----- | ----------- | ------ | -------------- | -------------- | --- | ----------- | ------ | --- |
|         | CH          |       |             | RH1    |                | RH2            |     | CO          |        |     |
| Figure  | 3.18.       |       |             |        |                |                |     |             |        |     |
|         |             | Steam | turbine     |        | configurations |                | and | approximate | linear |     |
| models. | Tandem      |       | compound,   | double | reheat         | configuration. |     |             |        |     |

| 3.4. | Turbine | Modelling | and | Control |     |     |
| ---- | ------- | --------- | --- | ------- | --- | --- |
39
Cross Compound, Single Reheat Steam Turbine
Control
HP, LP Shaft
Valves,
|     | Valve |     |        |     | LP  LP  |     |
| --- | ----- | --- | ------ | --- | ------- | --- |
|     |       |     | Steam  | HP  |         |     |
position
Chest
|     |     |     |     | Reheater | Crossover |     |
| --- | --- | --- | --- | -------- | --------- | --- |
IP, LP Shaft
|     |     |     |     |     | IP LP  LP  |     |
| --- | --- | --- | --- | --- | ---------- | --- |
Linear Model
(cid:54)
(cid:39)P
m1
F F
HP LP 2
|     |     |     | 1   | 1   | 1   |     |
| --- | --- | --- | --- | --- | --- | --- |
(cid:39)Pctrl
1(cid:14)sT
|     | m   | 1(cid:14)sT |     | RH  | 1(cid:14)sT |     |
| --- | --- | ----------- | --- | --- | ----------- | --- |
|     |     |             | CH  |     | CO          |     |
F
F LP
IP 2
(cid:54) (cid:39)P
m2
|     | Figure  | 3.19. | Steam     | turbine configurations | and approximate | linear |
| --- | ------- | ----- | --------- | ---------------------- | --------------- | ------ |
|     | models. | Cross | compound, | single reheat          | configuration.  |        |

|     |     |     |     |     |     | 3.  | Primary | Frequency | Control |
| --- | --- | --- | --- | --- | --- | --- | ------- | --------- | ------- |
40
Step Response To illustrate the dynamics of a steam turbine,the configu-
rationwithtandemcompound,singlereheat, Figure3.17, withthefollowing
| data | will | be studied: |        |             |       |            |     |       |            |
| ---- | ---- | ----------- | ------ | ----------- | ----- | ---------- | --- | ----- | ---------- |
|      | T    | = 0.1       | s, T = | 10 s, T     | = 0.3 | s          |     |       |            |
|      | CH   |             | RH     | CO          |       |            |     |       |            |
|      | F HP | = 0.3,      | F IP = | 0.4, F LP = | 0.3   |            |     |       |            |
| As   | T    | T           | und T  | T           | , we  | can assume | T   | = T   | = 0 for an |
|      | CH   | RH          |        | CO RH       |       |            |     | CH CO |            |
|      |      | ≪           |        | ≪           |       |            |     |       |            |
approximate analysis. Then a simplified block diagram according to Fig-
ure 3.20 can be used. For this system the step response is easy to calculate.
| It  | is depicted | in  | Figure | 3.21. |     |          |     |           |     |
| --- | ----------- | --- | ------ | ----- | --- | -------- | --- | --------- | --- |
|     |             |     |        |       |     | (cid:54) |     | (cid:39)P |     |
m
|     |     |     |     | 0.3 |     | 0.7 |     |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
1
(cid:39)Pctrl
|     |        |       | m            | 1(cid:14)s10 |     |                  |     |        |        |
| --- | ------ | ----- | ------------ | ------------ | --- | ---------------- | --- | ------ | ------ |
|     | Figure | 3.20. | Simplified   | model        | of  | tandem compound, |     | single | reheat |
|     | system | in    | Figure 3.17. |              |     |                  |     |        |        |
1
0.9
0.8
0.7
FIP + FLP = 0.7
enibrut morf rewoP 0.6
0.5
TRH = 10 s
0.4
0.3
0.2
FHP = 0.3
0.1
0
|     |     |     | 0 5 | 10 15 | 20 25 | 30  | 35 40 | 45 50 |     |
| --- | --- | --- | --- | ----- | ----- | --- | ----- | ----- | --- |
Time (s)
|     |     | Figure | 3.21. | Step response |     | of system | in Figure | 3.20. |     |
| --- | --- | ------ | ----- | ------------- | --- | --------- | --------- | ----- | --- |

| 3.4. | Turbine | Modelling |     | and Control |     |     |     |     |     |
| ---- | ------- | --------- | --- | ----------- | --- | --- | --- | --- | --- |
41
P
1
Length of
|     |     |     |     |     | Penstock |     | = L |     |     |
| --- | --- | --- | --- | --- | -------- | --- | --- | --- | --- |
h = Head
|     |     | Area     | = A |     |     |     |     |     |     |
| --- | --- | -------- | --- | --- | --- | --- | --- | --- | --- |
|     |     | Velocity | = v |     |     |     |     |     |     |
P
2
|     |     |     |     | Effective Area= |     |     | a   |     |     |
| --- | --- | --- | --- | --------------- | --- | --- | --- | --- | --- |
|     |     |     |     | Output Velocity |     |     | = v |     |     |
out
|     | Figure | 3.22. | Schematic | drawing | of  | hydro | turbine with water | paths. |     |
| --- | ------ | ----- | --------- | ------- | --- | ----- | ------------------ | ------ | --- |
Hydro Turbines
Compared with steam turbines, hydro turbines are easier and cheaper to
control. Thus,frequencycontrol is primarilydoneinthehydropower plants
if available. If the amount of hydro–generated power in a system is not
sufficient, the steam turbines have to be included in the frequency control.
The power produced by a generator is determined by the turbine gover-
norandthedynamicpropertiesoftheturbine. Thus,tobeabletodetermine
the frequency’s dynamic behaviour, models for the turbine as well as for the
| turbine | control |     | are necessary. |     |     |     |     |     |     |
| ------- | ------- | --- | -------------- | --- | --- | --- | --- | --- | --- |
Figure 3.22 depicts a hydro turbine with penstock and hydro reservoir
anddefinesthenotation thatwillbeusedfromnow on. Bernoulli’s equation
| for | a trajectory  |       | between     | the points    | P1 and  | P2    | can be written | as  |        |
| --- | ------------- | ----- | ----------- | ------------- | ------- | ----- | -------------- | --- | ------ |
|     |               | P2 ∂v | 1           |               |         |       | P2 1           |     |        |
|     |               |       |             | 2 2           |         |       |                |     |        |
|     |               |       | dr+         | (v 2 v 1 )+Ω2 |         | Ω1+   | dp = 0         | .   | (3.37) |
|     |               | ∂t    | · 2         | −             | −       |       | ρ              |     |        |
|     | ZP1           |       |             |               |         |       | ZP1            |     |        |
|     | The following |       | assumptions | are           | usually | made: |                |     |        |
v1 = 0, since the reservoir is large and the water level does not change
•
|     | during | the | time scale | that is | of interest |     | here. |     |     |
| --- | ------ | --- | ---------- | ------- | ----------- | --- | ----- | --- | --- |

42 3. Primary Frequency Control
The water velocity is non–zero only in the penstock.
•
Thewaterisincompressible,i.e.ρdoesnotchangewithwaterpressure.
•
The water pressure is the same at P1 and P2, i.e. p1 = p2.
•
Further,
Ω2 Ω1 = gh . (3.38)
− −
The above assumptions together with eq. (3.38) make it possible to write
(3.37), with v
out
= v2 and the length of the penstock L, as
dv 1
2
L + v gh = 0 . (3.39)
dt 2 out −
The velocity of the water in the penstock is v. The effective opening of the
penstock, determined by the opening of the turbine’s control valve (guide
vanes), is denoted a. If the penstock’s area is A,
A
v = v (3.40)
out
a
is valid and eq. (3.39) can be written as
2
dv 1 1 A
= gh v . (3.41)
dt L − 2L a
(cid:18) (cid:19)
The maximum available power at the turbine is
3 3
1 1 A v
3
P = ρav = ρ . (3.42)
2 out 2 a2
To get the system into standard form,
x = v ,
 a
 u = , (3.43)

 A



y = P ,





areintroduced. (Here, wehaveusedthestandardnotation, i.e.xforstate, u
for control signal, and y for output signal.) The system now can be written
as
gh 1
2
x˙ = x ,
L − 2Lu2
 (3.44)
   x 3
 y = ρA .
2u2





| 3.4. | Turbine | Modelling | and | Control |     |     |     |     |     |
| ---- | ------- | --------- | --- | ------- | --- | --- | --- | --- | --- |
43
| u   |     | x   |     |     |     |     |     |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
*/*
x⁄u
3
x
|     |     |     |     |     |     |     |     | y = P | = ρA-------- |
| --- | --- | --- | --- | --- | --- | --- | --- | ----- | ------------ |
2
2u
dx
| 2   | 2   |     |         |     | - dt |     |     | x   |     |
| --- | --- | --- | ------- | --- | ---- | --- | --- | --- | --- |
| x   | ⁄u  |     | 1       |     |      |     | 1   |     | y   |
|     |     |     | -- ---- |     | Σ    |     | --- |     |     |
|     |     |     | 2L      |     |      |     | s   |     |     |
+
gh
------
L
ρA
-------
2
|     | Figure | 3.23. | Block | diagram | showing | model | of  | hydro turbine. |     |
| --- | ------ | ----- | ----- | ------- | ------- | ----- | --- | -------------- | --- |
The system corresponding to eq. (3.44) can be described with the block
| diagram | in Figure |     | 3.23. |     |     |     |     |     |     |
| ------- | --------- | --- | ----- | --- | --- | --- | --- | --- | --- |
Eq. (3.44) is nonlinear and a detailed analysis is beyond the scope of
these lecture notes. To get an idea of the system’s properties, the equations
are linearised, and small variations around an operating point are studied.
In steady state, x˙ = 0, and the state is determined by x0, u0, and y0, which
fulfils
|     |     |     |     | x0  | = u0 | 2gh | ,   |     |        |
| --- | --- | --- | --- | --- | ---- | --- | --- | --- | ------ |
|     |     |     |    |     | p    |     |     |     | (3.45) |
3
|     |     |     |    |     | ρAx | 0   |     |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
|     |     |     |    | y0  | =   | .   |     |     |     |
|     |     |     |    |     |     | 2   |     |     |     |
|     |     |     |     |     | 2u  | 0   |     |     |     |
Small deviations ∆x, ∆u, and ∆y around the operating point satisfy

|     |     |     |     |     | 1   |     | 2x 2 |     |     |
| --- | --- | --- | --- | --- | --- | --- | ---- | --- | --- |
0
|     |     |     | ∆x˙ = | 2x0 | ∆x+   |     | ∆u    | ,   |     |
| --- | --- | --- | ----- | --- | ----- | --- | ----- | --- | --- |
|     |     |     |       | −   | 2Lu 2 |     | 2Lu 3 |     |     |
|     |     |    |       |     | 0     |     | 0     |     |     |

|     |     |    |     |     |     |     |     |     | (3.46) |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | ------ |
 

|     |     |   |      |     | 2   |     | 3   |     |     |
| --- | --- | --- | ---- | --- | --- | --- | --- | --- | --- |
|     |     |     |      | Ax  | 0   | Ax  | 0   |     |     |
|     |     |     | ∆y = | 3ρ  | ∆x  | 2ρ  | ∆u  | ,   |     |
|     |     |     |      |     | 2   |     | 3   |     |     |
|     |     |    |      | 2u  | 0 − | 2u  | 0   |     |     |

 

| which, | using | eqs. (3.45), | can | be written | as   |     |     |     |     |
| ------ | ----- | -------------- | --- | ---------- | ---- | --- | --- | --- | --- |
|        |       |                |     |            | √2gh | 2gh |     |     |     |
|        |       |                | ∆x˙ | =          | ∆x+  |     | ∆u  | ,   |     |
|        |       |                |     | −          | u0L  | u0L |     |     |     |

(3.47)
 

 
|     |     |     |    |        | 3y0 | 2y0 |     |     |     |
| --- | --- | --- | --- | ------ | --- | --- | --- | --- | --- |
|     |     |     | ∆y  | =      | ∆x  |     | ∆u  | .   |     |
|     |     |     |     | u0√2gh |     | −   | u0  |     |     |
 

 


|     |     |     |     |     |     |     | 3. Primary | Frequency | Control |
| --- | --- | --- | --- | --- | --- | --- | ---------- | --------- | ------- |
44
∆u
∆u
1
t(s)
|     |     |     | 0   | 5   | 10  |     | 15  | 20  |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
∆y
y
0
-----∆u
1
|     | u   |     |     |     |     |     |     |     | t(s) |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | ---- |
0
y
|           | 0   |     |     |     |     |     |     | T = 5 s |     |
| --------- | --- | --- | --- | --- | --- | --- | --- | ------- | --- |
| -2-----∆u |     |     |     |     |     |     |     | w       |     |
u 1
0
|     | Figure | 3.24.  | The     | variation | of the | produced | power, | ∆y, after | a step |
| --- | ------ | ------ | ------- | --------- | ------ | -------- | ------ | --------- | ------ |
|     | change | in the | control | valve.    |        |          |        |           |        |
The quantity L/√2gh has dimension of time, and from the above equa-
tions it is apparent that this is the time it takes the water to flow through
| the | penstock | if  | a= A. | That | time is denoted |     | T:  |     |        |
| --- | -------- | --- | ----- | ---- | --------------- | --- | --- | --- | ------ |
|     |          |     |       |      | T = L/          | 2gh | .   |     | (3.48) |
p
If eqs. (3.47) are Laplace–transformed, ∆x can be solved from the first
| of  | the equations, |     | leading | to  |     |     |     |     |     |
| --- | -------------- | --- | ------- | --- | --- | --- | --- | --- | --- |
L/T
|     |     |     |     | ∆x  | =   | ∆u  | ,   |     | (3.49) |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | ------ |
1+su0T
| which, | when | inserted |     | in the lower | of eqs.     | (3.47) | gives |     |        |
| ------ | ---- | -------- | --- | ------------ | ----------- | ------ | ----- | --- | ------ |
|        |      |          |     |              | y0 1        | 2u0Ts  |       |     |        |
|        |      |          |     | ∆y =         | −           |        | ∆u .  |     | (3.50) |
|        |      |          |     |              | u0 · 1+u0Ts |        |       |     |        |
The quantity u0T = a0T/A also has dimension of time and is denoted T .
w
The time constant T is the time it takes for the water to flow through the
w
penstock when a = a0 or u = u0, i.e. for the operation point where the
| linearization |     | is  | done. | Eq. (3.50) | can thus | be   | written | as  |        |
| ------------- | --- | --- | ----- | ---------- | -------- | ---- | ------- | --- | ------ |
|               |     |     |       |            | y0 1     | 2T s |         |     |        |
|               |     |     |       | ∆y         | =        | w    | ∆u .    |     | (3.51) |
−
|     |     |     |     |     | u0 · 1+T | s   |     |     |     |
| --- | --- | --- | --- | --- | -------- | --- | --- | --- | --- |
w

| 3.4. Turbine |     | Modelling | and | Control |     |     |     |     |
| ------------ | --- | --------- | --- | ------- | --- | --- | --- | --- |
45
It is evident that the transfer function in eq. (3.51) is of non–minimum
phase, i.e. not all poles and zeros are in the left half plane. In this case, one
zero is in the right half plane. That is evident from the step response to
| eq. (3.51), | depicted |     | in Figure | 3.24. |     |     |     |     |
| ----------- | -------- | --- | --------- | ----- | --- | --- | --- | --- |
The system has the peculiar property to give a lower power just after
the opening of the control valve is increased before the desired increased
power generation is reached. The physical explanation is the lower pressure
appearingafterthecontrolvalveisopened,sothatthewaterinthepenstock
can be accelerated. When the water has been accelerated, the generated
power is increased as a consequence of the increased flow. That property of
water turbines places certain demands on the design of the control system
for the turbines.
| 3.4.2 | Steam | Turbine | Control | Valves |     |     |     |     |
| ----- | ----- | ------- | ------- | ------ | --- | --- | --- | --- |
Asstatedearlier,thecontrolinputofthesteamturbineactsonavalvewhich
influences the inflow of live steam into the turbine. As the valve cannot be
moved at infinite speed, a further dynamics is introduced into the system.
This is usually modelled by a first-order element. Furthermore, constraints
exist on the ramp rate (speed of the valve motion) and the absolute valve
position. Note that, if the block diagram is expressed in ∆ quantities, the
latter has to be formulated in ∆ quantities as well, taking into account the
steady-state valve position. Figure 3.25 depicts the corresponding block
diagram.
Note that this block must be inserted between the turbine controller
∆Pctrl
output m and the turbine input when the valve dynamics shall be con-
sidered. The output of the valve can be named then ∆Pctrl and its input
m
∆Pctrl∗
| could | be renamed |     | to e.g. | .   |     |     |     |     |
| ----- | ---------- | --- | ------- | --- | --- | --- | --- | --- |
m
|                |          |          |              |                  | (cid:39)P(cid:5) |                     | (cid:39)P (cid:32)P | (cid:16)P     |
| -------------- | -------- | -------- | ------------ | ---------------- | ---------------- | ------------------- | ------------------- | ------------- |
|                |          |          |              |                  | up               |                     | max                 | max max,0     |
| (cid:39)Pctrl* |          |          |              |                  |                  |                     |                     | (cid:39)Pctrl |
|                | (cid:14) |          | 1            |                  |                  | 1                   |                     |               |
|                | m        |          |              |                  |                  |                     |                     | m             |
|                |          |          | T            |                  |                  | s                   |                     |               |
|                |          | (cid:16) | V            |                  |                  |                     |                     |               |
|                |          |          |              | (cid:39)P(cid:5) |                  | (cid:39)P (cid:32)P | (cid:16)(cid:39)P   |               |
|                |          |          |              | down             |                  |                     | min,0               |               |
|                |          |          |              |                  |                  | min                 | min                 |               |
|                |          |          | Figure 3.25. | Model            | of               | a control           | valve.              |               |

|     |     |     |     | 3.  | Primary Frequency | Control |
| --- | --- | --- | --- | --- | ----------------- | ------- |
46
| 3.4.3 | Hydro | Turbine Governors |     |     |     |     |
| ----- | ----- | ----------------- | --- | --- | --- | --- |
The task of a turbine governor is to control the turbine power output such
that it is equal to a set value which consists of a constant and a frequency-
dependent part, the latter of which is of interest here. For steam turbines,
thishasbeendiscussedinSection3.1. Becauseoftheparticularitiesofhydro
turbines, which have been shown in Section 3.4.1, another type of governor
is needed.
Amodel of ahydroturbinegovernor is given in Figure 3.26. Thecontrol
servo is here represented simply by a time constant T . The main servo,
p
i.e. the guide vane, is represented by an integrator with the time constant
T . Typical values for these parameters are given in Table 3.2. Limits for
G
opening and closing speed as well as for the largest and smallest opening of
| the control        | valve | are given. |           |          |                      |     |
| ------------------ | ----- | ---------- | --------- | -------- | -------------------- | --- |
|                    |       |            |           | u(cid:5) |                      | u   |
|                    |       |            |           | open     |                      | max |
| (cid:39)f (cid:14) |       | 1          | (cid:16)1 |          | 1 (cid:39)u (cid:14) |     |
u
|     |          | 1(cid:14)T s | T   |     | s   |     |
| --- | -------- | ------------ | --- | --- | --- | --- |
|     | (cid:16) | p            | G   |     |     |     |
(cid:14)
u
|     |     |     | u(cid:5) |     |     | min |
| --- | --- | --- | -------- | --- | --- | --- |
|     |     |     | close    |     | u   |     |
0
|     | (cid:14) |     | (cid:71)T s |     |     |     |
| --- | -------- | --- | ----------- | --- | --- | --- |
R
|     | (cid:14) |     | 1(cid:14)T s |     |     |     |
| --- | -------- | --- | ------------ | --- | --- | --- |
R
(cid:86)
|     | Figure | 3.26. Model | of turbine | governor | for hydro turbine. |     |
| --- | ------ | ----------- | ---------- | -------- | ------------------ | --- |
|     |        | Parameter   | Typical    | Values   |                    |     |
|     |        | T           | 2.5        | – 7.5    | s                  |     |
R
|     |     | T   | 0.2 | – 0.4 | s   |     |
| --- | --- | --- | --- | ----- | --- | --- |
G
|     |     | T   | 0.03 | – 0.06 | s   |     |
| --- | --- | --- | ---- | ------ | --- | --- |
p
|           |              | δ                                                  |      | 0.2 – 1 |     |     |
| --------- | ------------ | -------------------------------------------------- | ---- | ------- | --- | --- |
|           |              | σ                                                  | 0.03 | – 0.06  |     |     |
| Table3.2. |              | Typicalvaluesforsomeparametersoftheturbinegovernor |      |         |     |     |
| for       | hydro power. |                                                    |      |         |     |     |

| 3.5. Dynamic |     | Responses |     | including | Turbine | Dynamics |     |     |     |
| ------------ | --- | --------- | --- | --------- | ------- | -------- | --- | --- | --- |
47
The controller has two feedback loops, a transient feedback loop and
a static feedback loop. The transient feedback loop has the amplification
δ for high frequencies. Thus, the total feedback after a frequency change
is (δ +σ). In steady state, the transient feedback is zero, and the ratio
−
between the frequency deviation and the change in the control valve is given
by
1
|     |     |     |     | ∆u= |     | ∆f . |     |     | (3.52) |
| --- | --- | --- | --- | --- | --- | ---- | --- | --- | ------ |
−σ
| Using eq. | (3.51), | the | stationary |     | change | of power | is obtained | as  |     |
| --------- | ------- | --- | ---------- | --- | ------ | -------- | ----------- | --- | --- |
1P0
|           |       |       |     | ∆P            | =   | ∆f     | .   |     | (3.53) |
| --------- | ----- | ----- | --- | ------------- | --- | ------ | --- | --- | ------ |
|           |       |       |     |               | −σ  | u0     |     |     |        |
| Thus, the | speed | droop |     | for generator | i,  | S , is |     |     |        |
i
u0i
|     |     |     |     | S   | = σ | ,   |     |     | (3.54) |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | ------ |
|     |     |     |     |     | i   | i   |     |     |        |
P0i
| and the | total | speed | droop, | S, in | the system | is   | given by |     |        |
| ------- | ----- | ----- | ------ | ----- | ---------- | ---- | -------- | --- | ------ |
|         |       |       |        | S −1  | =          | S −1 | .        |     | (3.55) |
i
i
X
The transient feedback is needed since the water turbine is a non–minimum
phase system as discussed above. With static feedback only, the control
performance will be unsatisfactory when closed-loop stability shall be guar-
anteed. Increasing the static feedback to a range where a reasonable control
| performance |     | could | be attained | will | make | the | system unstable. |     |     |
| ----------- | --- | ----- | ----------- | ---- | ---- | --- | ---------------- | --- | --- |
The transient feedback loop provides an additional feedback component
during non-stationary operating conditions. This feedback decays as steady
state is attained. The initial total feedback can be about ten times larger
than the static feedback, i.e. the speed droop is initially lower than its sta-
tionary value.
| 3.5 | Dynamic |     | Responses |     | including |     | Turbine | Dynamics |     |
| --- | ------- | --- | --------- | --- | --------- | --- | ------- | -------- | --- |
In this section, we will simulate the dynamic responses of a power system
consistingofdifferentgenerationunittypeswithprimarycontrolequipment.
The goal is to improve the understanding of the impact of the turbine dy-
| namics | on the | overall | control | behaviour |     | of the | system. |     |     |
| ------ | ------ | ------- | ------- | --------- | --- | ------ | ------- | --- | --- |
Weconsider again theone-area power systemas presentedinFigure3.11
withthemainparametersgivenaccordingtoTable3.3. Asstatedbefore,the
turbine dynamics is inserted in the block ”Turbine dynamics/control”. The
effect of three different turbine dynamics will be studied: a steam turbine
without reheater, a steam turbine with reheater and a hydro turbine.
In Figure 3.27, the power system responseto a load increase disturbance
of ∆P = +1000 MW is compared. Note that this is equivalent to the
load
| loss of | a major | generation |     | unit, | e.g. a | nuclear | power plant. |     |     |
| ------- | ------- | ---------- | --- | ----- | ------ | ------- | ------------ | --- | --- |

|     |     |     |     | 3. Primary | Frequency | Control |
| --- | --- | --- | --- | ---------- | --------- | ------- |
48
|     |     | Parameter | Value | Unit |     |     |
| --- | --- | --------- | ----- | ---- | --- | --- |
|     |     | H         | 5     | s    |     |     |
|     |     | S         | 10    | GW   |     |     |
B
|     |     | f0  | 50  | Hz   |     |     |
| --- | --- | --- | --- | ---- | --- | --- |
|     |     | D   |     | 1 Hz |     |     |
|     |     | L   | 200 | MW   |     |     |
MW
|     |     | W0  | 0   |     |     |     |
| --- | --- | --- | --- | --- | --- | --- |
Hz
|     |     | T   | 0.3 | s   |     |     |
| --- | --- | --- | --- | --- | --- | --- |
CH
|     |     | T   | 8   | s   |     |     |
| --- | --- | --- | --- | --- | --- | --- |
RH
|     |     | T   | 0.5 | s   |     |     |
| --- | --- | --- | --- | --- | --- | --- |
CO
|     |     | S   | 0.04 | p.u. |     |     |
| --- | --- | --- | ---- | ---- | --- | --- |
|     |     | T   | 1.4  | s    |     |     |
W
|     |     | T   | 0.2 | s   |     |     |
| --- | --- | --- | --- | --- | --- | --- |
G
|     |     | T   | 6.5 | s   |     |     |
| --- | --- | --- | --- | --- | --- | --- |
R
|       |                 | σ        | 0.04   | p.u.       |              |         |
| ----- | --------------- | -------- | ------ | ---------- | ------------ | ------- |
|       |                 | δ        | 0.3    | p.u.       |              |         |
| Table | 3.3. Parameters | for time | domain | simulation | of the power | system. |
The upper plot shows the frequency response of the uncontrolled power
system just as a comparison. It can be seen in the following plots that
the frequency control performance is highly dependent on the turbine type.
While steam turbines without reheating equipment do not allow the fre-
quency to decay substantially more than their steady-state deviation, the
time delays caused by the reheater make the response a lot slower. The
hydro turbine allows the most significant frequency decay before the system
| is brought | back to | the steady-state | frequency. |     |     |     |
| ---------- | ------- | ---------------- | ---------- | --- | --- | --- |

| 3.5. | Dynamic | Responses | including | Turbine | Dynamics |     |     |     |
| ---- | ------- | --------- | --------- | ------- | -------- | --- | --- | --- |
49
Uncontrolled power system
50
]zH[ f 48
46
|     | 0   | 5   |     | 10  | 15  | 20  | 25  | 30  |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
Primary control on unit without reheating
50
]zH[ f
49.5
49
|     | 0   | 5   |     | 10  | 15  | 20  | 25  | 30  |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
Primary control on unit with reheating
50
]zH[ f
49.5
49
|     | 0   | 5   |     | 10  | 15  | 20  | 25  | 30  |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
Primary control on hydro unit
50
]zH[ f
49
48
|     | 0   | 5   |     | 10  | 15  | 20  | 25  | 30  |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
System load step ∆ P
load
1000
]WM[
daol
500
P ∆
0
|     | 0   | 5   |     | 10  | 15  | 20  | 25  | 30  |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
Time [s]
|     | Figure | 3.27. Dynamic |     | response | of the power | system without | pri- |     |
| --- | ------ | ------------- | --- | -------- | ------------ | -------------- | ---- | --- |
marycontrol,withprimarycontrolonsteamturbineswithoutreheater,
|     | steam | turbines with | reheater, | and | hydro turbines. |     |     |     |
| --- | ----- | ------------- | --------- | --- | --------------- | --- | --- | --- |

|     |     |     |     |     |     |     | 3. Primary | Frequency | Control |
| --- | --- | --- | --- | --- | --- | --- | ---------- | --------- | ------- |
50
Finally, one more illustration of the effect of the turbine dynamics shall
be given. For a direct comparison of a primary-controlled one-area system
without and with turbine dynamics, the exemplary system simulated in
Figure 3.12 is now simulated again with a steam turbine model without
| reheater |     | (T CH = | 0.3 s). | The result | is  | shown | in Figure | 3.28. |     |
| -------- | --- | ------- | ------- | ---------- | --- | ----- | --------- | ----- | --- |
50
|     | ]zH[ ycneuqerF metsyS | 49.95 |     |     |     |     |     |     |     |
| --- | --------------------- | ----- | --- | --- | --- | --- | --- | --- | --- |
49.9
49.85
49.8
49.75
|     |     | 0   | 1   | 2 3 | 4   | 5   | 6 7 | 8 9 | 10  |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |

400
300
|     |     | ]WM[ rewoP |     |     |     |     |     |  ∆ P |     |
| --- | --- | ---------- | --- | --- | --- | --- | --- | ---- | --- |
load
 ∆ P
|     |     | 200 |     |     |     |     |     |     | m   |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
 ∆ P f
|     |     | 100 |     |     |     |     |     |     | load |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | ---- |
0

|     |     | 0   | 1   | 2 3 | 4   | 5   | 6 7 | 8 9 | 10  |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
Time [s]
|     | Figure | 3.28. | Behaviour | of  | the one-area |     | system (including | dynamics |     |
| --- | ------ | ----- | --------- | --- | ------------ | --- | ----------------- | -------- | --- |
ofsteamturbinewithoutreheater,otherwisesameparameterizationas
|     | inFigure          | 3.12)after |     | a stepincreasein                     |     | load. | The upper | plotshowsthe |     |
| --- | ----------------- | ---------- | --- | ------------------------------------ | --- | ----- | --------- | ------------ | --- |
|     | systemfrequencyf. |            |     | Thelowerplotshowsthestepfunctionin∆P |     |       |           |              | ,   |
load
|     | the | increaseinturbine |     | power∆P |     | ,andthe | frequency-dependentload |     |     |
| --- | --- | ----------------- | --- | ------- | --- | ------- | ----------------------- | --- | --- |
m
∆Pf
|     | variation |     | .   |     |     |     |     |     |     |
| --- | --------- | --- | --- | --- | --- | --- | --- | --- | --- |
load

4
| Load |     | Frequency | Control |
| ---- | --- | --------- | ------- |
In this chapter the secondary, or load-frequency, control of power systems
will be discussed. Simple models that enable the simulation of the dynamic
behaviour during the action of frequency controllers will also be derived and
studied.
In the previous chapter, the role of the primary frequency control was
dealt with. It was shown that after a disturbance a static frequency error
will persist unless additional control actions are taken. Furthermore, the
primary frequency control might also change the scheduled interchanges be-
tween different areas in an interconnected system. To restore the frequency
and the scheduled power interchanges, additional control actions must be
taken. This is done through the Load-Frequency Control (LFC). The LFC
can be done either manually through operator interaction or automatically.
In the latter case it is often called Automatic Generation Control (AGC).
The characteristics of AGC will be studied in the subsequent sections, both
| during | steady | state and dynamic | conditions. |
| ------ | ------ | ----------------- | ----------- |
| 4.1    | Static | Characteristics   | of AGC      |
The overall purpose of the Automatic Generation Control comprises two
main aspects:
Keep the frequency in the interconnected power system close to the
•
1
|     | nominal | value. |     |
| --- | ------- | ------ | --- |
Restore the scheduled interchanges between different areas, e.g. coun-
•
|     | tries, | in an interconnected | system. |
| --- | ------ | -------------------- | ------- |
The mechanisms of AGC that enable it to fulfill these requirements will be
| outlined | in  | the sequel. |      |
| -------- | --- | ----------- | ---- |
|          | 1In |             | ±0.1 |
many systems, deviations of up to Hz from the nominal value (50 or 60 Hz)
is deemed as acceptable in steady state. In some systems, North America, even tighter
tolerance bands are applied, while recently in UK the tolerance band has been relaxed
somewhat.
51

52 4. Load Frequency Control
Area 1 Area 2
G
G G
P P
T1 T2
G
Pset Pset
AGC1 AGC2
G
G G
f f
1 2
AGC AGC
1 2
P (cid:32) Tie line power for Area 1 = (cid:166)Pj (cid:32)Sum over all tie lines
T1 T1
j(cid:143)(cid:58)
1
Figure 4.1. Two area system with AGC.
ConsideratwoareasystemasdepictedinFigure4.1. Thetwosecondary
frequency controllers, AGC1 and AGC2, will adjust the power reference
values of the generators participating in the AGC. In an N-area system,
there are N controllers AGC , one for each area i. A block diagram of such
i
a controller is given in Figure 4.2. A common way is to implement this as a
proportional-integral (PI) controller:
1
∆P = (C + )∆e (4.1)
AGCi pi i
− sT
Ni
where C = 0.1 ... 1.0 and T = 30 ... 200 s. The error ∆e is called
pi Ni i
Area Control Error, ACE for area i.
i
We willnow considerasystem withN areas. TheACEs arein thiscase:
j j
ACE
i
= (P
Ti −
P
T0i
)+B
i
(f
−
f0) i = 1,2,...,N . (4.2)
j X ∈Ω i
Defining now
j j
∆P = (P P ) , (4.3)
Ti Ti − T0i
j X ∈Ω i
the ACE can be written as
ACE = ∆P +B ∆f i= 1,2,...,N . (4.4)
i Ti i
The set Ω consist of all areas connected to area i for which the tie line
i
j
powers should be controlled to the set value P . The constants B are
T0i i

| 4.1. Static | Characteristics |     |     | of AGC |     |     |     |     |
| ----------- | --------------- | --- | --- | ------ | --- | --- | --- | --- |
53
P
T0i
(cid:16)
P
(cid:39)e
|     |     | Ti  |     | i    AGC |     | (cid:39)P |     |     |
| --- | --- | --- | --- | -------- | --- | --------- | --- | --- |
i
|     |     |     | (cid:14) |     |     |     | AGCi |     |
| --- | --- | --- | -------- | --- | --- | --- | ---- | --- |
(cid:14)
B
i
(cid:39)f
f
(cid:14)
(cid:16)
f
0
| Figure | 4.2.    | Control | structure | for AGC | (∆e = | Error | = ACE | =   |
| ------ | ------- | ------- | --------- | ------- | ----- | ----- | ----- | --- |
|        |         |         |           |         | i     |       | i     |     |
| Area   | Control | Error   | for area  | i)      |       |       |       |     |
called frequency bias factors [MW/Hz]. It is assumed that the frequency
references are the same in all areas, i.e. f0i = f0 for all i, and f is also the
same in steady state for all areas. The goal is to bring all ACE 0.
i
→
Thevariablesarethus∆P (N variables)andf,i.e.intotalN + 1vari-
Ti
ables. Since we have N equations (ACE i = 0), we need one more equation.
| As a fifth | equation | we  | have | the power balance: |     |     |     |       |
| ---------- | -------- | --- | ---- | ------------------ | --- | --- | --- | ----- |
|            |          |     |      | ∆P Ti =            | 0 , |     |     | (4.5) |
X i
| and consequently |     | a solution |     | can be achieved. |     |     |     |     |
| ---------------- | --- | ---------- | --- | ---------------- | --- | --- | --- | --- |
In steady state, f is identical for all areas, and we assume that the
frequency is controlled back to the reference value, i.e. f0 = f. If the sum
j
of the reference values of the tie line powers P T0i is 0, then the system will
j j
settle down to an operating point where P T0i = P for all tie line powers.
Ti
The time constants of the AGC is chosen such that it reacts much slower
| than the  | primary      | frequency |      | control. |     |     |     |     |
| --------- | ------------ | --------- | ---- | -------- | --- | --- | --- | --- |
| Selection | of Frequency |           | Bias | Factors  |     |     |     |     |
Consider the two area system in Figure 4.1. The load is now increased with
∆P inarea2. Ifthetielinepowershouldbekeptthesame,thegeneration
load
must be increased in area 2 with ∆P after the AGC has reacted. Before
load
the AGC has reacted we have a frequency deviation of ∆f in both areas,

|     |     |     |     |     |     |     | 4.  | Load Frequency | Control |
| --- | --- | --- | --- | --- | --- | --- | --- | -------------- | ------- |
54
| which | means | that | for area | 1   |     |      |     |     |       |
| ----- | ----- | ---- | -------- | --- | --- | ---- | --- | --- | ----- |
|       |       |      |          | ∆f  | =   | S1∆P | T1  |     | (4.6) |
−
| and for | area | 2   |     |      |       |     |        |     |       |
| ------- | ---- | --- | --- | ---- | ----- | --- | ------ | --- | ----- |
|         |      |     |     | ∆f = | S2(∆P |     | ∆P T1) |     | (4.7) |
load
|        |      |     |         | −   |      | −       |     |            |     |
| ------ | ---- | --- | ------- | --- | ---- | ------- | --- | ---------- | --- |
| and ∆P | T1 = | ∆P  | T2. The | two | ACEs | can now | be  | written as |     |
−
| ACE1 | = ∆P | T1+B1∆f |     | = ∆P T1+B1( |     | S1∆P | T1) | = ∆P T1(1 B1S1) | (4.8) |
| ---- | ---- | ------- | --- | ----------- | --- | ---- | --- | --------------- | ----- |
|      |      |         |     |             |     | −    |     | −               |       |
and
| ACE2 | =   | ∆P T2+B2∆f |     | = ∆P | T2+B2( |     | S2(∆P | ∆P T1)) = |     |
| ---- | --- | ---------- | --- | ---- | ------ | --- | ----- | --------- | --- |
load
|     |     |     |     |     |     | −    |       | −      |       |
| --- | --- | --- | --- | --- | --- | ---- | ----- | ------ | ----- |
|     |     |     |     |     | ∆P  | T2(1 | B2S2) | B2S2∆P | (4.9) |
load
|     |     |     |     |     |     |     | −   | −   |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
In this case it is desirable that the AGC controller in area 1 does not react.
If we set B1 = 1/S1 we see from eq. (4.8) that ACE1 = 0. This is called
Non Interactive Control. If B2 = 1/S2 is chosen the ACE in area 2 becomes
|     |     |     |     | ACE2 | =   | ∆P  | load |     | (4.10) |
| --- | --- | --- | --- | ---- | --- | --- | ---- | --- | ------ |
−
This means that only controller 2 reacts and the load increase ∆P is
load
compensated for in area 2 by the PI control law as stated in eq. (4.1).
However, as long as the controller in eq. (4.1) has an integrating part,
all positive values of B i will guarantee that all ACE i 0. The choice ac-
→
cording to Non Interactive Control has been foundto give the best dynamic
performance through a number of investigations. In a multi-area case this
| corresponds |         | to selecting |                 | B i = 1/S | i for | all areas. |     |     |     |
| ----------- | ------- | ------------ | --------------- | --------- | ----- | ---------- | --- | --- | --- |
| 4.2         | Dynamic |              | Characteristics |           |       | of         | AGC |     |     |
Asinthepreviouschapteronprimaryfrequencycontrol,wewillnowdevelop
a dynamic model of the power system where the newly introduced AGC is
included. As the way of extracting input-output transfer functions from
block diagrams has already been presented in the last chapter, we omit the
analytical derivation here for shortness. The interested reader is welcome
to calculate the transfer function between the load disturbance and the
| frequency | as       | an exercise. |        |     |     |     |     |     |     |
| --------- | -------- | ------------ | ------ | --- | --- | --- | --- | --- | --- |
| 4.2.1     | One-area |              | system |     |     |     |     |     |     |
In a single-area power system, there is obviously no tie-line power to be
controlled. In this case, the AGC only fulfills the purpose of restoring the
nominalsystemfrequency. Figure4.3showstheknownblockdiagramwhich
has been extended by the proportional-integral control law of the AGC.
Figure 4.4 shows a plot of the system frequency which is brought back to
the nominal value. The parameters of the system are as presented in Table
3.3 (turbine dynamics neglected), and B = 1/S, C p = 0.17, T N = 120 s.

4.2. Dynamic Characteristics of AGC 55
Frequency-dependent loads
(cid:39)P System load change
load
1
D
l
(cid:14) (cid:14)
(cid:39)Pf
load
(cid:14)
(cid:14)
2W
0 s
f
0 (cid:39)P
e
Rotating mass loads
(cid:16)
f (cid:39)f
0
(2HS )s
(cid:14) B
(cid:39)P
m System inertia
1 (cid:39)Pset 1
(cid:16) m
S (cid:14) 1(cid:14)Ts
(cid:14) t
Primary Turbine
control (cid:39)Pset dynamics/
m0 control
(one area
ACE
(cid:39)P (cid:39)P 1 system)
sched AGC (cid:16)(C (cid:14) ) B
(cid:14) (cid:14) p sT
N
frequency
AGC
bias
Figure 4.3. Dynamic model of one-area system with AGC.
50.1
50.05
50
49.95
49.9
49.85
49.8
49.75
49.7
0 100 200 300 400 500 600 700 800 900
Time [s]
]zH[
f
with ACG
without AGC
Figure 4.4. Dynamic response of the one-area system equipped with
primary control and AGC compared with the same system without
AGC.

|     |     |     |     |     | 4.  | Load | Frequency Control |
| --- | --- | --- | --- | --- | --- | ---- | ----------------- |
56
| 4.2.2 Two-area | system |     | – unequal | sizes | –   | disturbance | response |
| -------------- | ------ | --- | --------- | ----- | --- | ----------- | -------- |
Here we consider the same two-area power system as in section 3.3.4 where
Area1isassumedtobemuchsmaller thanArea2. Thecorrespondingblock
diagramincludingtheAGCisshowninFigure4.6. Becauseofthesecondary
control(AGC)oneobtainsthestepresponseinFigure4.5. Theloadincrease
of ∆P load,1 = 1000 MW in Area 1 is in this case fully compensated by the
| generators in | Area 1. |     |     |     |     |     |     |
| ------------- | ------- | --- | --- | --- | --- | --- | --- |
|               | 50.05   |     |     |     |     |     |     |
]zH[ ycneuqerf metsyS
50
|     | 49.95 |     |     |     |     |     |  f  |
| --- | ----- | --- | --- | --- | --- | --- | --- |
1
 f
|     | 49.9 |     |     |     |     |     | 2   |
| --- | ---- | --- | --- | --- | --- | --- | --- |
49.85
49.8
|     | 0    | 100 | 200 | 300 | 400 | 500 | 600 |
| --- | ---- | --- | --- | --- | --- | --- | --- |
|     | 1000 |     |     |     |     |     |     |
800
600
]WM[ P
 ∆ P
|     | 400 |     |     |     |     |     | AGC,1 |
| --- | --- | --- | --- | --- | --- | --- | ----- |
 ∆ P
AGC,2
|     | 200 |     |     |     |     |     |  ∆ P |
| --- | --- | --- | --- | --- | --- | --- | ---- |
T21
0
−200
|     | 0   | 100 | 200 | 300 | 400 | 500 | 600 |
| --- | --- | --- | --- | --- | --- | --- | --- |
Time [s]
| Figure4.5.                                            | StepresponseforthesysteminFigure4.6withAGC.The |        |                     |             |              |      |              |
| ----------------------------------------------------- | ---------------------------------------------- | ------ | ------------------- | ----------- | ------------ | ---- | ------------ |
| upperdiagramshowsthesystemfrequenciesofArea1andArea2. |                                                |        |                     |             |              |      | The          |
| lowerdiagramshowsthecontrolactionoftheAGCsinArea1∆P   |                                                |        |                     |             |              |      | AGC,1        |
| which                                                 | compensates                                    | the    | power deficit       | and         | in Area      | 2 ∆P | AGC,2 which  |
| is largely                                            | uninfluenced                                   |        | by the disturbance. |             | Furthermore, |      | the tie line |
| power                                                 | ∆P T21 is                                      | shown, | which initially     | compensates |              | the  | disturbance  |
| and then                                              | slowly                                         | decays | to 0.               |             |              |      |              |

| 4.2. Dynamic | Characteristics |     | of AGC |     |     |
| ------------ | --------------- | --- | ------ | --- | --- |
57
(cid:39)P
load,1
1
D
l,1
(cid:14)
1
1(cid:14)Ts
t
|     |     | (cid:14) (cid:14) |                     | 1   |          |
| --- | --- | ----------------- | ------------------- | --- | -------- |
|     |     |                   | (cid:16)(C (cid:14) | )   |          |
|     |     |                   | p1                  |     | (cid:14) |
sT
N1 (cid:14)
(cid:39)P (cid:39)P
T12 T12
(cid:16)
(cid:16)
2(cid:83)Pˆ
T
s
1
1(cid:14)Ts
t
B
2
(cid:14)
(cid:14) (cid:14)(cid:39)P
|     | (cid:39)P |     |                           | 1   |          |
| --- | --------- | --- | ------------------------- | --- | -------- |
|     | sched,2   |     | AGC,2 (cid:16)(C (cid:14) | )   |          |
|     |           |     | p2                        | sT  | (cid:16) |
N2
|     | Figure 4.6. | Dynamic | model of two-area | system with | AGC. |
| --- | ----------- | ------- | ----------------- | ----------- | ---- |

58 4. Load Frequency Control
4.2.3 Two-area system, unequal sizes – normal control operation
So far, we only simulated the dynamic response of the power system to
step-wise disturbances in the load. During the everyday normal operation
of a power system, however, the automatic control loops of primary and
secondary control are always active to compensate for the continuously aris-
ing small imbalances between generation and load. These normal-operation
imbalances are due to load fluctuations, load prediction errors, and, in the
presence of intermittent infeeds (from wind power etc.) in the control area,
infeed fluctuations and infeed prediction errors. In this context, the differ-
ence between fluctuation and prediction errors is constituted by the time
scales on which they occur: while the term ”fluctuation” is usually defined
as largely uncorrelated stochastic noise on a second or minute time scale,
”prediction error” usually refers to a mismatch of predicted and actual con-
sumption/infeed on a 15-minute time scale. The latter usually shows a
certain autocorrelation, which means that the probability of the signal to
assumeacertainvalueisdependentonthepreviouslyassumedsignalvalues.
Another important impact on the AGC arises from schedule changes
that occur at the full hour. The reason for this timing is the trading on
electricity markets which is usually done in an hourly framework. Because
of ramping actions of power plants which often deviate from the ramping
profiles they are supposed to follow, imbalances just before the full hour
(either positive or negative), as well as just after the full hour (then in the
opposite direction) arise. This effect, however, is disregarded in the present
setup.
Figure4.7demonstratestheresponseofthetwo-areasystemtoastochas-
tically varying load. The system is parameterized again according to Table
3.1. To increase the degree of realism, the dynamic model of a steam tur-
bine without reheater is included. As often found in practice, the primary
controls are equipped with a dead band of 10 mHz. Saturation of the
±
control variables (due to limited amounts of contracted control reserves) is
not modelled. A detailed discussion of the synthesis of the load fluctuation
and prediction error signals is beyond the scope of this lecture. Thus, only
the input time series ∆P load,1 and ∆P load,2 are shown in the plot.

| 4.2. | Dynamic | Characteristics |     | of  | AGC |     |     |     |     |
| ---- | ------- | --------------- | --- | --- | --- | --- | --- | --- | --- |
59
System frequencies
|     | 50.15 |     |     |     |     |     |     |     |     |
| --- | ----- | --- | --- | --- | --- | --- | --- | --- | --- |
]zH[ ycneuqerf metsyS
50.1
50.05
50
 f
1
|     | 49.95 |     |     |     |     |     |     |     |  f  |
| --- | ----- | --- | --- | --- | --- | --- | --- | --- | --- |
2

|     | 0   | 10  |     | 20  | 30  |     | 40  | 50  | 60  |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
Activity of secondary control
|     | 600 |     |     |     |     |     |     |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
400
]WM[ P 200
 ∆ P
|     | 0   |     |     |     |     |     |     | AGC,1 |        |
| --- | --- | --- | --- | --- | --- | --- | --- | ----- | ------ |
|     |     |     |     |     |     |     |     |  ∆ P  |  /1000 |
AGC,2
|     | −200 |     |     |     |     |     |     |  ∆ P |     |
| --- | ---- | --- | --- | --- | --- | --- | --- | ---- | --- |
T21
−400
|     | 0   | 10  |     | 20  | 30  |     | 40  | 50  | 60  |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
Activity of primary control
|     | 400 |     |     |     |     |     |     |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
200
]WM[ P
0
 ∆ Pset
m,1
|     | −200 |     |     |     |     |     |     |  ∆ Pset /1000 |     |
| --- | ---- | --- | --- | --- | --- | --- | --- | ------------- | --- |
m,2
−400
|     | 0   | 10  |     | 20  | 30  |     | 40  | 50  | 60  |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
Stochastic load fluctuation and prediction error
|     | 400 |     |     |     |     |     |     |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
200
]WM[ P
0
 ∆ P
|     | −200 |     |     |     |     |     |     | load,1       |     |
| --- | ---- | --- | --- | --- | --- | --- | --- | ------------ | --- |
|     |      |     |     |     |     |     |     |  ∆ P  / 1000 |     |
load,2
−400
|     | 0   | 10  |     | 20  | 30  |     | 40  | 50  | 60  |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
Time [min]
|     | Figure     | 4.7.        | Normal  | operation  | of the | two area | system. | The usual     |     |
| --- | ---------- | ----------- | ------- | ---------- | ------ | -------- | ------- | ------------- | --- |
|     | small      | mismatches  | between | generation | and    | demand   | are     | modelled by a |     |
|     | stochastic | disturbance |         | in the     | load.  |          |         |               |     |

|     |     |     | 4. Load | Frequency Control |
| --- | --- | --- | ------- | ----------------- |
60
4.2.4 Two-area system – equal sizes, including saturations – dis-
| turbance | response |     |     |     |
| -------- | -------- | --- | --- | --- |
Finally we briefly investigate the dynamic behaviour of a two-area system
wherebothareasareofthesamesize. Turbinedynamicsareagain neglected
in this scenario. Here, saturations of the control inputs which represent the
limited amount of contracted primary and secondary control reserves are
modelled (primary control: 75 MW, secondary control: 350 MW). A
|     |     | ±   |     | ±   |
| --- | --- | --- | --- | --- |
graphical representation of the saturations in a block diagram is omitted
here for shortness. Referring again to Figure 4.6, the saturation blocks
∆Pset
would have to be inserted in the signal path of m (primary control)
and ∆P (secondary control). Furthermore, countermeasures against
AGC
integrator wind-up have to be taken, which shall not be discussed here.
Figure 4.8 shows the step response (∆P load,1 = 400 MW) for the system
withtwoequallysizedareas. ItisclearlyvisiblethattheAGCofArea1can-
notcompensateforthedeviationandremainsatitssaturationof+350MW.
The system frequency is not brought back to 50 Hz. In real power system
operation, the ancillary service dispatcher in the control center would now
manually activate tertiary control reserves in order to relieve the saturated
secondary reserves.
|     | 50  |     |     |     |
| --- | --- | --- | --- | --- |
49.98
49.96
|     | ]zH[ f |     |     | ∆ f |
| --- | ------ | --- | --- | --- |
|     | 49.94  |     |     | 1   |
∆ f
2
49.92
49.9
49.88
|     | 0   | 100 200 | 300 400 500 | 600 |
| --- | --- | ------- | ----------- | --- |
|     | 400 |         |             |     |
300
|     | 200    |     | ∆ P |     |
| --- | ------ | --- | --- | --- |
|     | ]WM[ P |     |     | T12 |
∆ P
AGC,1
|     | 100 |     | ∆ P |     |
| --- | --- | --- | --- | --- |
AGC,2
0
−100
|     | 0   | 100 200 | 300 400 500 | 600 |
| --- | --- | ------- | ----------- | --- |
Time [s]
| Figure      | 4.8. Step response | for the  | system in Figure    | 4.6 with AGC, |
| ----------- | ------------------ | -------- | ------------------- | ------------- |
| equal areas | with a rated       | power of | 10 GW each. Because | of the satu-  |
ratedsecondarycontrol,thepowersystemfrequencycannotbebrought
| back to | the nominal value | of 50 Hz. |     |     |
| ------- | ----------------- | --------- | --- | --- |

5
Synchronous Machine Model
Almost all energy consumed by various loads in an electric power system is
produced by synchronous machines, or, more correctly, the conversion from
the primary energy sources, like water energy, nuclear energy, or chemical
energy, to electrical energy is done in synchronous machines with a mechan-
ical intermediate link, the turbine. This is true in larger power systems, but
not always in smaller systems like isolated islands, power supply of equip-
ment in deserts, or other smaller systems. In these systems, the energy
can come from asynchronous generators, for example in wind generation
units, batteries, or some other source of electrical energy. In systems with
synchronous generators, these have an extremely important part in many
dynamic phenomena. Thus, it is very important to develop usable and real-
istic models of the synchronous machines. In the previous chapters, mainly
the mechanical properties of the synchronous machines have been modelled
using the swing equation, while a very simplistic model of the electrical prop-
erties of the synchronous machine has been used. In this chapter, a more
general, detailed model of the electric parts of the synchronous machine will
be derived. The simple models used earlier will be justified. It should be
emphasized that the description here aims towards the development of mod-
els usable for studying dynamic phenomena in the power system. It is not
the purpose of these models to give a detailed and deep understanding of the
physical functions of the synchronous machine. Of course, it is desirable to
have a good insight into the physics of the synchronous machine to be able to
derive appropriate models. For a detailed discussion of these aspects, books
and courses dealing with the theory of electrical machines should be studied.
5.1 Park’s Transformation
Park’stransformationisaphasetransformation(coordinatetransformation)
between the three physical phases in a three phase system and three new
phases, or coordinates, that are convenient for the analysis of synchronous
machines. This transformation is also known as the dq–transformation or
Blondel’s transformation. A reason why the transformation is suitable can
be derived from Figure 5.1.
It is obvious that the phase quantities in the a–, b–, and c–phases will
vary periodically in steady state. Further, the self and mutual inductances
between stator circuits and rotor circuits will vary with the rotor position.
Instead of performingall computations in the fixedstator system, thestator
61

|     |     |     | 5. Synchronous | Machine Model |
| --- | --- | --- | -------------- | ------------- |
62
a-axis
|     | d-axis | θ     |     |     |
| --- | ------ | ----- | --- | --- |
|     |        | fb n′ | sc  |     |
i
b
i
Q
i
D
n′
| Direction |     |     | i   |     |
| --------- | --- | --- | --- | --- |
F
| of Rotation | sa  |     |     | fa  |
| ----------- | --- | --- | --- | --- |
i
a
i
i
F
|     |     | i   | Q   |     |
| --- | --- | --- | --- | --- |
D
c-axis
n′
| b-axis |     | i   | sb  |     |
| ------ | --- | --- | --- | --- |
c
fc
q-axis
| Figure | 5.1.       |               |                           |     |
| ------ | ---------- | ------------- | ------------------------- | --- |
|        | Definition | of quantities | in Park’s transformation. |     |
quantities voltages, currents,andfluxescan betransformedtoasystemthat
rotates with the rotor. Thus, two orthogonal axes are defined as shown in
Figure 5.1: One along the axis in which the current in the rotor windings
generates a flux, and one in an axis perpendicular to this. The first is the
directaxis(d–axis), andtheotheristhequadratureaxis(q–axis). Fromnow
on, the denominations d–axis and q–axis will be used. To make the system
complete, a third component corresponding to the zero sequence must be
defined.
Figure 5.1 is a simplified picture of a synchronous machine and should
only beviewed as an intuitive basis for the transformation given below. The
machine in Figure 5.1 has one pole pair, but Park’s transformation can, of
course, be applied to machines with an arbitrary number of pole pairs.
Park’s transformation is, as a consequence of the reasoning above, time
dependent, and the connection between the phase currents and the trans-

5.1. Park’s Transformation 63
formed currents is given by
1
i0 = (i
a
+i
b
+i
c
) ,
3
 r
  2 2π 2π
  i = i cosθ+i cos θ +i cos θ+ , (5.1)
 d a b c
    r 3 (cid:20) (cid:18) − 3 (cid:19) (cid:18) 3 (cid:19)(cid:21)
2 2π 2π
   i q = 3 − i a sinθ − i b sin θ − 3 − i c sin θ+ 3 .
  r (cid:20) (cid:18) (cid:19) (cid:18) (cid:19)(cid:21)


If the a–axis is chosen as reference,
θ = ωt+θ0 (5.2)
is obtained and the time dependence in the transformation is obvious. It
should be pointed out that i , i , and i are the real physical phase currents
a b c
as functions of time and not a phasor representation of those. Now,
x = (x ,x ,x )T
abc a b c
(5.3)
x0dq = (x0,x
d
,x
q
)T
can be defined. x can here be an arbitrary quantity, like voltage, current,
or flux. With this notation, Park’s transformation can be written as
x0dq = Px
abc
(5.4)
with
1/√2 1/√2 1/√2
2
P = cosθ cos(θ
2π)
cos(θ+
2π)
. (5.5)
3 3
r 3  sinθ sin(θ − 2π) sin(θ+ 2π) 
3 3
− − − −
 
The inverse transformation is then given by
−1
x
abc
=P x0dq , (5.6)
and it can easily be shown that
P −1 = PT . (5.7)
A mnemonic for Park’s transformation can be obtained from Figure 5.1 by
projecting the a–, b–, and c–axes onto the d– and q–axes in the figure.
Equation (5.7) implies that Park’s transformation is an orthonormal
transformation. This is reflected in the expression for the momentary power
that is produced in the stator windings
p = u i +u i +u i = uT i =
a a b b c c abc abc
(P −1 u0dq )TP −1 i0dq = (PTu0dq )TP −1 i0dq =
uT
0dq
PP −1 i0dq = uT
0dq
i0dq = (5.8)
u0i0+u
d
i
d
+u
q
i
q
.

|     |     |     |     |     |     | 5. Synchronous | Machine | Model |
| --- | --- | --- | --- | --- | --- | -------------- | ------- | ----- |
64
Here,Equations(5.6)and(5.7)havebeenused. Equation(5.8)cantherefore
| be written | as  |         |      |      |          |     |          |       |
| ---------- | --- | ------- | ---- | ---- | -------- | --- | -------- | ----- |
|            |     | p = u i | +u i | +u i | = u0i0+u |     | i +u i . | (5.9) |
|            |     | a a     | b b  | c    | c        |     | d d q q  |       |
Equation (5.9) shows that the introduced transformation is power invariant,
| which is | a consequence | of  | Equation |     | (5.7). |     |     |     |
| -------- | ------------- | --- | -------- | --- | ------ | --- | --- | --- |
ItshouldbepointedoutthatthereareseveraldifferentvariantsofPark’s
transformation appearing in literature. They can differ from the form pre-
sented here by the direction of the q–axis and by constants in the transfor-
mation matrix. When using equations from some book or paper, it is thus
important to make sure that the definition of Park’s transformation used is
| the same | as one’s | own. | Otherwise, | wrong |     | results | might be obtained. |     |
| -------- | -------- | ---- | ---------- | ----- | --- | ------- | ------------------ | --- |
Therotorwindingsproduceafluxlinkagethatmainlyliesinthedirection
of the d–axis. That flux induces an electro-magnetic field, E, which is
◦
lagging by 90 , hence in the direction of the negative q–axis. For generator
operation, the phasor for E leads by an angle δ before the phasor for the
terminal voltage U. At t = 0, the negative q–axis thus leads by an angle δ
before the phasor for the voltage along the a–axis, cf. Figure 5.1. For t > 0,
the d– and q–axes have moved by an angle ωt with the angular speed of the
| rotor ω. | The rotor’s | d–axis | will | hence | be  | in position |     |     |
| -------- | ----------- | ------ | ---- | ----- | --- | ----------- | --- | --- |
π
|     |     |     | θ   | = ωt+δ+ |     | .   |     | (5.10) |
| --- | --- | --- | --- | ------- | --- | --- | --- | ------ |
2
It is particularly of interest to study how zero sequence, negative sequence,
and positive sequence quantities are transformed by Park’s transformation.
It is comparatively easy to show that a pure zero sequence quantity only
leads to a contribution in x0 with x d = x q = 0. A pure positive sequence
quantity
sin(θ+α)
|     |     | x (+)= | √2x |     | sin(θ+α |     | 2π)   | (5.11) |
| --- | --- | ------ | --- | --- | ------- | --- | ----- | ------ |
|     |     | abc    |     |     |         |     | 3     |        |
|     |     |        |     |    |         | −   | 2π)  |        |
|     |     |        |     |     | sin(θ+α | +   |       |        |
3
|                |     |     |     |    |     |     |    |     |
| -------------- | --- | --- | --- | --- | --- | --- | --- | --- |
| is transformed | to  |     |     |     |     |     |     |     |
0
√3x
|     |     | x0dq | (+)= |     | sin(α) |     | ,   | (5.12) |
| --- | --- | ---- | ---- | --- | ------ | --- | --- | ------ |
|     |     |      |      |     |       |     |    |        |
cos(α)
−
|     |     |     |     |     |    |     |    |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
i.e. pure DC-quantities (time independent) in the dq–system with the zero
sequence component equal zero. A pure negative sequence quantity gives
risetoquantitiesind–andq–directionsthatvarywiththeangularfrequency
2ω. The zero sequence component vanishes also in this case. (Show this!)

5.2. The Inductance Matrices of the Synchronous Machine 65
5.2 The Inductance Matrices of the Synchronous Ma-
chine
Inthefollowing, a synchronousmachine withonedamperwindingind–and
oneinq–axisand,ofcourse, afieldwindingisconsidered. Quantitiesrelated
to these windings are denoted with the indices D, Q, and F, respectively.
The flux linkages in the stator windings (Ψ ) and in the windings F, D,
abc
and Q (Ψ ) depend on the currents in these windings according to
FDQ
Ψ L L i
abc abc,abc abc,FDQ abc
= . (5.13)
Ψ L L i
FDQ FDQ,abc FDQ,FDQ FDQ
(cid:18) (cid:19) (cid:18) (cid:19)(cid:18) (cid:19)
L , ..., L are 3 3 matrices with self and mutual inductances
abc,abc FDQ,FDQ
×
as matrix elements. These will depend on the rotor position, hence they are
time dependent. The following approximation for inductances L(θ) proves
to be useful: L(θ) = L +L cos2θ with L > L > 0, where L and L
s m s m s m
are machine constants that can be identified from measurements. The same
holds for the machine constant M that will be used in the case of mutual
s
inductances. Keeping that in mind, the matrix elements are calculated.
• L abc,abc : L aa = L s +L m cos2θ ,
L = L +L cos(2θ
4π)
,
bb s m 3

L = L +L cos(2θ
−
+
4π)
,
  cc s m 3 (5.14)
  L = L = M L cos(2θ+ π) ,
   ab ba − s − m 3
L = L = M L cos(2θ+π) ,
bc cb s m
   L ac = L ca = − − M s − − L m cos(2θ+ 5 3 π) .


• L abc,FDQ and  L aF = L Fa = M F cosθ ,
L FDQ,abc : L = L = M cos(θ 2π) ,
   L b c F F = L F F b c = M F F cos(θ − + 2 3 3 π) ,





   L aD = L Da = M D cosθ ,
    L bD = L Db = M D cos(θ 2 3 π) , (5.15)
 
 L = L = M cos(θ
−
+
2π)
,
 cD Dc D 3

            L L L a b c Q Q Q = = = L L L Q Q Q b c a = = = − − − M M M Q Q Q s s s i i i n n n ( ( θ θ θ − + , 2 2 3 3 π π ) ) , .


L FDQ,FDQ :    L FF = L F ,
•
L = L ,
DD D

L = L ,
 QQ Q

  (5.16)



 L = L = M ,
 FD DF R
L = L = 0 ,
FQ QF

   L DQ = L QD = 0 .






66 5. Synchronous Machine Model
Allinductances withonly oneindexinEquations (5.14) –(5.16) arecon-
stants and depend on the design of the synchronous machine. The resulting
inductancesareofcourse,asmentionedbefore,notquiteexact. Theycanbe
called exact in an ideal machine, where spatial harmonics and other unsym-
metries are neglected. For a real synchronous machine, the approximations
are usually very good and lead to fully acceptable results for the computa-
tions and analyses treated here. It should be emphasized that the model
developed here is for use in computations where the synchronous machines
are part of a larger system. The model is not primarily aimed at studies of
the internal quantities in the generator.
It is now natural to transform the abc–components in Equation (5.13)
to 0dq–components. For this, an extended transformation given by
P 0
P = , (5.17)
ex
0 I
(cid:18) (cid:19)
with P according to (5.5) and a 3 3 unit matrix I is used. The result is
×
Ψ0dq L0dq,0dq L0dq,FDQ i0dq
= , (5.18)
Ψ FDQ L FDQ,0dq L FDQ,FDQ i FDQ
(cid:18) (cid:19) (cid:18) (cid:19)(cid:18) (cid:19)
with the inductance matrix given by
L 0dq,0dq L 0dq,FDQ = P 0 L abc,abc L abc,FDQ P−1 0 .
(cid:18) L FDQ,0dq L FDQ,FDQ (cid:19) (cid:18) 0 I (cid:19)(cid:18) L FDQ,abc L FDQ,FDQ (cid:19)(cid:18) 0 I (cid:19)
(5.19)
The virtue of the Park’s transformation is apparent in the following equa-
tion, where the inductance matrix in (5.18) is computed
L0 0 0
L0dq,0dq = 0 L
d
0 , (5.20)
 
0 0 L
q
 
with
L0 = L
s
2M
s
,
−
3
L = L +M + L , (5.21)
 d s s 2 m
  L = L +M 3 L ,
q s s 2 m
−
and 

0 0 0
L0dq,FDQ = kM
F
kM
D
0 , (5.22)
 
0 0 kM
Q
 
where
3
k = (5.23)
2
r
and, of course,
L FDQ,0dq = LT 0dq,FDQ . (5.24)

| 5.3. | Voltage | Equations | for | the | Synchronous |     | Machine |     |     |     |
| ---- | ------- | --------- | --- | --- | ----------- | --- | ------- | --- | --- | --- |
67
d-axis
d
ω
D
F
q-axis
|     |        |         |           | q       |         | Q   |              |         |      |     |
| --- | ------ | ------- | --------- | ------- | ------- | --- | ------------ | ------- | ---- | --- |
|     | Figure | 5.2.    | Schematic | picture | of      | the | transformed  | system. | (One |     |
|     | damper | winding | in the    | d–axis  | and one | in  | the q–axis.) |         |      |     |
L has, of course, not changed, but for completeness it is re-
FDQ,FDQ
peated here.
|     |     |     |     |     | L   | M   | 0   |     |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
F R
|     |     |     | L FDQ,FDQ | =   | M   | R L | D 0 | .   |     | (5.25) |
| --- | --- | --- | --------- | --- | --- | --- | --- | --- | --- | ------ |
|     |     |     |           |     |    |     |     |    |     |        |
|     |     |     |           |     | 0   | 0   | L   |     |     |        |
Q
|     |     |     |     |     |    |     |     |    |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
Two important observations can be made from Equations (5.20)–(5.25):
The inductances in the inductance matrix in Equation (3.18) are not
•
|     | dependent |     | on time. |     |     |     |     |     |     |     |
| --- | --------- | --- | -------- | --- | --- | --- | --- | --- | --- | --- |
The quantities in d- and q-directions are decoupled. (The induction
•
|     | matrix | is  | block diagonal: | one | 2   | 2 matrix | and | one | 1 1 matrix.) |     |
| --- | ------ | --- | --------------- | --- | --- | -------- | --- | --- | ------------ | --- |
|     |        |     |                 |     | ×   |          |     |     | ×            |     |
The second observation above leads to a picture of the transformed sys-
| tem | according | to  | Figure 5.2. |     |     |     |             |     |         |     |
| --- | --------- | --- | ----------- | --- | --- | --- | ----------- | --- | ------- | --- |
| 5.3 | Voltage   |     | Equations   |     | for | the | Synchronous |     | Machine |     |
For the three stator circuits and the three rotor circuits the following rela-
| tions | can | be written: |     |     |     |     |     |     |     |     |
| ----- | --- | ----------- | --- | --- | --- | --- | --- | --- | --- | --- |
Ψ˙
|     |     |     |     | u   | = r | i   | ,   |     |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
|     |     |     |     | a   | − a | a − | a   |     |     |     |
Ψ˙
|     |     |     |     | u b | = r b | i b  | b , |     |     | (5.26) |
| --- | --- | --- | --- | --- | ----- | ---- | --- | --- | --- | ------ |
|     |     |     |     |    | −     | −    |     |     |     |        |
|     |     |     |     | u   | = r   | i Ψ˙ | ,   |     |     |        |
|     |     |     |     |  c | c     | c    | c   |     |     |        |
|     |     |     |     |     | −     | −    |     |     |     |        |


68 5. Synchronous Machine Model
(cid:3)
Figure 5.3. Sign convention for stator and rotor circuits.
and
u = r i +Ψ˙ ,
F F F F
0= r i +Ψ˙ , (5.27)
D D D

 0= r Q i Q +Ψ˙ Q .
Equations (5.26) and (5.27) can be written more compactly in vector
form,
u R 0 i Ψ˙
abc abc abc abc
= . (5.28)
u FDQ − 0 R FDQ i FDQ − Ψ˙ FDQ
(cid:18) (cid:19) (cid:18) (cid:19)(cid:18) (cid:19) (cid:18) (cid:19)
The vector u is defined as
FDQ
u = ( u ,0,0)T , (5.29)
FDQ F
−
while the other vectors are defined as before. R and R are diagonal
abc FDQ
3 3 matrices.
×
If Equation (5.28) is multiplied by P according to Equation (5.17), all
ex
quantities are transformed to the dq–system, i.e.
u0dq PR
abc
P −1 0 i0dq PΨ˙
abc
= . (5.30)
u FDQ − 0 R FDQ i FDQ − Ψ˙ FDQ
(cid:18) (cid:19) (cid:18) (cid:19)(cid:18) (cid:19) (cid:18) (cid:19)
−1
The matrix PR
abc
P is denoted R0dq , and if r
a
= r
b
= r
c
= r, which in
most cases is true,
R0dq = R
abc
= rI (5.31)
is valid.

| 5.3. Voltage | Equations |     | for | the | Synchronous | Machine |     |     |     |     |     |
| ------------ | --------- | --- | --- | --- | ----------- | ------- | --- | --- | --- | --- | --- |
69
To get Equation (5.30) expressed solely in dq–quantities, also the last
term on the right hand side must be expressed in these. Since P is time
| dependent, | it  | is important |     | to remember |        | that |     |     |     |        |     |
| ---------- | --- | ------------ | --- | ----------- | ------ | ---- | --- | --- | --- | ------ | --- |
|            |     |              |     |             | P˙ = 0 | ,    |     |     |     | (5.32) |     |
6
| which leads | to  |     |       |     |     |     |      |     |     |        |     |
| ----------- | --- | --- | ----- | --- | --- | --- | ---- | --- | --- | ------ | --- |
|             |     | Ψ˙  |       | d   | P˙Ψ |     | +PΨ˙ |     |     |        |     |
|             |     |     | 0dq = | (PΨ | )=  |     |      | ,   |     | (5.33) |     |
|             |     |     |       |     | abc | abc |      | abc |     |        |     |
dt
and thus
|          |        | PΨ˙ | Ψ˙    | P˙Ψ        |       | Ψ˙  | P˙P −1 |      |     |        |     |
| -------- | ------ | --- | ----- | ---------- | ----- | --- | ------ | ---- | --- | ------ | --- |
|          |        | abc | = 0dq |            | abc = | 0dq |        | Ψ0dq | .   | (5.34) |     |
|          |        |     |       | −          |       |     | −      |      |     |        |     |
| Equation | (5.30) | can | hence | be written | as    |     |        |      |     |        |     |
−1
| u0dq |     | R0dq |     | 0   | i0dq |     | Ψ˙  |     | P˙P | Ψ0dq |     |
| ---- | --- | ---- | --- | --- | ---- | --- | --- | --- | --- | ---- | --- |
0dq
|     | =   |     |     |     |     |     | Ψ˙  | +   |     |     | .   |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| u   |     | −   | 0 R |     | i   | −   |     |     |     | 0   |     |
(cid:18) FDQ (cid:19) (cid:18) FDQ (cid:19)(cid:18) FDQ (cid:19) (cid:18) FDQ (cid:19) (cid:18) (cid:19)
(5.35)
Some trivial computations show that the matrix P˙P −1 can be expressed as
|     |     |     |     |     | 0 0 | 0   |     |     |     |        |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | ------ | --- |
|     |     |     | P˙P | −1  |     |     |     |     |     |        |     |
|     |     |     |     | =   | 0 0 | ω   | .   |     |     | (5.36) |     |
|     |     |     |     |     |    |     |    |     |     |        |     |
|     |     |     |     |     | 0   | ω 0 |     |     |     |        |     |
−
|     |     |     |     |     |    |     |    |     |     |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
The voltage equations in the dq–system can thus be written in component
form as
Ψ˙
|     |     |     | u0  | =   | ri0 | 0 , |     |     |     |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
|     |     |     |     |     | − − |     |     |     |     |     |     |
Ψ˙
|     |     |     | u   | d = | ri d    | d +ωΨ | q , |     |     | (5.37) |     |
| --- | --- | --- | --- | --- | ------- | ----- | --- | --- | --- | ------ | --- |
|     |     |     |    |     | − −     |       |     |     |     |        |     |
|     |     |     | u   | =   | ri Ψ˙   | ωΨ    | ,   |     |     |        |     |
|     |     |     |    | q   | q       | q     | d   |     |     |        |     |
|     |     |     |     | −   | −       | −     |     |     |     |        |     |
| and |     |     |    |     |         |       |     |     |     |        |     |
|     |     |     |     | u   | = r i   | Ψ˙    | ,   |     |     |        |     |
|     |     |     |     | F   | F F     |       | F   |     |     |        |     |
|     |     |     |     | −   | −       | Ψ˙ −  |     |     |     |        |     |
|     |     |     |     | 0 = | r i     |       | ,   |     |     | (5.38) |     |
|     |     |     |    |     | − D D − | D     |     |     |     |        |     |
Ψ˙
|     |     |     |    | 0 = | r Q i Q | Q . |     |     |     |     |     |
| --- | --- | --- | --- | --- | ------- | --- | --- | --- | --- | --- | --- |
|     |     |     |     |     | − −     |     |     |     |     |     |     |
In the previous section, expressions for the dependencies of the flux linkages
on the currents in the different windings were derived. To further simplify
the expressions that were obtained, the per unit system for the different
windings is now introduced so that all mutual inductances in the d–axis
are equal, and all in the q–axis are equal. (In our case, only one damping
winding in the q–axis was considered, but in a more general case several
| damper | windings | can | be considered.) |     | We  | introduce |     |     |     |     |     |
| ------ | -------- | --- | --------------- | --- | --- | --------- | --- | --- | --- | --- | --- |
|        |          |     | 3               |     | 3   |           |     |     |     |     |     |
|        |          |     | M               | =   | M = | M         | = L | ,   |     |     |     |
|        |          |     | 2               | F   | 2 D | R         | AD  |     |     |     |     |
(5.39)
|     |     |     | q3  | q   |     |     |     |     |     |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
|     |     |     | M   | = L | .   |     |     |     |     |     |     |
|     |     |     | 2   | Q   | AQ  |     |     |     |     |     |     |
q

|     |     |     |     |     | 5.  | Synchronous Machine | Model |
| --- | --- | --- | --- | --- | --- | ------------------- | ----- |
70
| The different | fluxes | can | then be   | written | as    |     |        |
| ------------- | ------ | --- | --------- | ------- | ----- | --- | ------ |
|               |        |     | Ψ0 = L0i0 | ,       |       |     |        |
|               |        |     | Ψ = L     | i +L    | (i +i | ) , | (5.40) |
|               |        |     | d         | d d     | AD F  | D   |        |

|     |     |     | Ψ = L   | i +L     | i ,      |        |        |
| --- | --- | --- | ------- | -------- | -------- | ------ | ------ |
|     |     |    | q       | q q      | AQ Q     |        |        |
| and |     |    |         |          |          |        |        |
|     |     |     | Ψ = L   | i +L     | (i +i    | ) ,    |        |
|     |     |     | F       | F F      | AD d     | D      |        |
|     |     |     | Ψ = L   | i +L     | (i       | +i ) , | (5.41) |
|     |     |    | D       | D D      | AD d     | F      |        |
|     |     |    | Ψ Q = L | Q i Q +L | AQ i q . |        |        |
Equations (5.37) and(5.38) together with Equations (5.40) and (5.41) now
describetheelectricaldynamicsofasynchronousmachinecompletely. These
equations together with a description of the external system unequivocally
determine the behaviour of the synchronous machine during different dis-
turbances. In Figure 5.4, a graphical description of these equations is given.
InEquation(5.37),weobservethattheemfind–andq–directionconsists
of two terms: one that is a time derivative of the absolute value of the flux
linkage and one that arises because the field winding is rotating. The first
of these is usually called stator transient and the other rotational emf. In
steady state, the first of these vanishes, and the whole emf is created by the
Ψ˙ Ψ˙
rotation of the field winding. It can be shown that the terms d and q are
in most applications much smaller than ωΨ and ωΨ , which justifies that
|           |              |       |            |     | d   | q            |        |
| --------- | ------------ | ----- | ---------- | --- | --- | ------------ | ------ |
| the first | ones are     | often | neglected. |     |     |              |        |
| 5.4       | Synchronous, |       | Transient, |     | and | Subtransient | Induc- |
tances
The complete description of the synchronous machine given in the previous
section can be simplified and made more understandable from a physical
standpoint if a number of new parameters are introduced. These new pa-
rameters can be derived from the already defined ones. In steady state or a
sufficientlylongtimeafteradisturbance,theinducedcurrentsinthedamper
windings and in the field winding vanish. After a disturbance different time
intervals can be distinguished, during which different couplings between the
circuits in Figure 5.4 prevail. This makes it possible to define new induc-
tances describing the synchronous machine during these time periods, and
these inductances will be derived in this section. Further, the time con-
stants that specify how fast the currents in the damper windings decay are
derived in the next section. These time constants indicate also the duration
of the time intervals, during which the derived inductances determine the
| behaviour | of the | synchronous | machine. |     |     |     |     |
| --------- | ------ | ----------- | -------- | --- | --- | --- | --- |
Earlier, the synchronous inductances L and L were defined. They are
|     |     |     |     |     | d   | q   |     |
| --- | --- | --- | --- | --- | --- | --- | --- |

| 5.4. | Synchronous, |     | Transient, | and | Subtransient |     | Inductances |     |     |     |     |
| ---- | ------------ | --- | ---------- | --- | ------------ | --- | ----------- | --- | --- | --- | --- |
71
r
F
+
| u   |     |     | L   |     |     |     |     |     | r   |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
|     | F   |     | F   |     |     |     |     |     |     | d i |     |
d
-
i
|     |     | F   |     |     |     |     |     |     |     |     | +   |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
|     |     |     |     |     | L   |     |     | L   |     |     | u   |
|     |     |     |     |     | AD  |     |     | d   | ωψ  |     | d   |
r
q
|     |     | D   |     |     |     |     |     |     | +   | -   |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
|     |     |     | L   |     |     |     |     |     | r   |     |     |
|     |     |     | D   |     |     |     |     |     |     | q i |     |
q
i
|     |     | D   |     |     |     |     |     |     |     |     | +   |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
|     |     |     |     |     |     |     |     | L   |     |     | u   |
|     |     |     |     |     |     |     |     | q   |     |     | q   |
|     |     | r   |     |     | L   |     |     |     | ωψ  |     |     |
|     |     |     |     |     | AQ  |     |     |     |     | d   |     |
Q
|     |     |     |     |     |     |     |     |     | -   | +   |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
|     |     |     | L   |     |     |     |     |     | r   |     |     |
|     |     |     | Q   |     |     |     |     |     |     | 0 i |     |
0
i
|          |                | Q                 |                |             |           |        |         |                 |     |     | +   |
| -------- | -------------- | ----------------- | -------------- | ----------- | --------- | ------ | ------- | --------------- | --- | --- | --- |
|          |                |                   |                |             |           |        |         | L               |     |     | u   |
|          |                |                   |                |             |           |        |         | 0               |     |     | 0   |
|          | Rotor Circuits |                   |                |             |           |        |         | Stator Circuits |     |     |     |
|          | Figure         | 5.4.              | Graphical      | description |           | of the | voltage | equations       | and | the |     |
|          | coupling       | between           | the equivalent |             | circuits. |        |         |                 |     |     |     |
| repeated | here           | for completeness. |                |             |           |        |         |                 |     |     |     |
3
|     |     |     |          | L = | L +M | +   | L   |     |     |        |     |
| --- | --- | --- | -------- | --- | ---- | --- | --- | --- | --- | ------ | --- |
|     |     |     |          | d   | s    | s   | 2 m |     |     |        |     |
|     |     |     |          |     |      |     | 3   |     |     | (5.42) |     |
|     |     |     |          | L = | L +M |     | L   |     |     |        |     |
|     |     |     | (cid:26) | q   | s    | s   | 2 m |     |     |        |     |
−
For a synchronous machine with salient poles, like a hydropower generation
unit, L > 0 and thus L > L , while L 0 for machines with round
|     | m   |     |     | d   | q   | m   |     |     |     |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
≈
rotors leading to L L . These inductances describe the synchronous
|     |     |     | d ≈ | q   |     |     |     |     |     |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
machine in steady state as can be seen from Figure 5.4. In steady state the
currents i and i = 0, so there is no influence from the damper windings
|     | D   | Q   |     |     |     |     |     |     |     |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
on the stator circuits. Since in steady state the rotor current i is a pure
F
dc current the only influence from the field current on the stator circuits
is through the rotational voltages ωΨ and ωΨ . From Figure 5.4 it is
|     |     |     |     |     |     | d   | q   |     |     |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
thus obvious that the inductances seen from the generator terminals are in

|     |     |     |     |     |     |     | 5. Synchronous |     | Machine | Model |
| --- | --- | --- | --- | --- | --- | --- | -------------- | --- | ------- | ----- |
72
steady state L d and L q . However, when transients occur, e.g. due to short
circuits or other disturbances, there will be couplings between the circuits
in Figure 5.4 and this will result in that the equivalent inductances as seen
fromtheterminalswillchange. Theseequivalentinductanceswillbederived
in the following.
First, the subtransient and transient inductances in the d-axis will be
derived. It is assumed that the machine is in steady state before the distur-
| bance | and | a voltage | change | of  | the form |          |     |     |     |     |
| ----- | --- | --------- | ------ | --- | -------- | -------- | --- | --- | --- | --- |
|       |     |           | ∆u     |     |          | sin(θ+α) |     |     |     |     |
a
2π)
|     |     |     | ∆u  | = √2∆u |     | sin(θ+α |     | c(t)  |     | (5.43) |
| --- | --- | --- | --- | ------ | --- | ------- | --- | ----- | --- | ------ |
|     |     |     | b   |        |     |         |     | 3     |     |        |
|     |     |    |     |       |    |         | −   | 4π)  |     |        |
|     |     |     | ∆u  |        |     | sin(θ+α |     |       |     |        |
|     |     |     | c   |        |     |         | −   | 3     |     |        |
|     |     |    |     |       |    |         |     |      |     |        |
issuperimposedontheterminalvoltages. Thefunctionc(t)isastepfunction
at t = 0, i.e. c(t) = 0 for t < 0 and c(t) = 1 for t > 0. With α = π/2 the
| Park–transformed |     |     | voltage | vector | in  | Equation | (5.43) | becomes |     |        |
| ---------------- | --- | --- | ------- | ------ | --- | -------- | ------ | ------- | --- | ------ |
|                  |     |     |         | ∆u0    |     |          | 0      |         |     |        |
|                  |     |     |         | ∆u     | =   | √3∆u     | c(t)   |         |     | (5.44) |
|                  |     |     |         |       | d  |          |       |        |     |        |
|                  |     |     |         | ∆u     | q   |          | 0      |         |     |        |
|                  |     |     |         |       |    |          |       |        |     |        |
For t = 0+, that is, directly after the voltage is applied on the terminals,
the flux linkages Ψ and Ψ are still zero since they cannot change instan-
|            |     |      | F        | D             |           |      |        |       |     |     |
| ---------- | --- | ---- | -------- | ------------- | --------- | ---- | ------ | ----- | --- | --- |
| taneously. |     | This | gives    | the following | equations |      |        |       |     |     |
|            |     |      | Ψ F (0+) | = 0           | = L F ∆i  | F +L | AD (∆i | d +∆i | D ) |     |
(5.45)
|     |     |     | Ψ (0+) | = 0 | = L | ∆i +L | (∆i | +∆i | )   |     |
| --- | --- | --- | ------ | --- | --- | ----- | --- | --- | --- | --- |
|     |     |     | D      |     | D   | D     | AD  | d   | F   |     |
(cid:26)
where ∆i , ∆i , and ∆i , with obvious notation, are the currents induced
|     | f   | d   |     | D   |     |     |     |     |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
in the circuits due to the step in the voltage. From (5.45) ∆i and ∆i can
|              |     |     |        |     |     |     |     |     | D   | F   |
| ------------ | --- | --- | ------ | --- | --- | --- | --- | --- | --- | --- |
| be expressed |     | in  | ∆i d , |     |     |     |     |     |     |     |
2
|     |     |     |     |      | L F   | L AD | L   |      |     |     |
| --- | --- | --- | --- | ---- | ----- | ---- | --- | ---- | --- | --- |
|     |     |     |     | ∆i = |       | −    | AD  | ∆i , |     |     |
|     |     |     |     | D    |       |      | 2   | d    |     |     |
|     |     |     |     |      | − L F | L D  | L   |      |     |     |
|     |     |     |    |      |       | −    | AD  |      |     |     |
(5.46)
|     |     |     |   |      |     |     | 2   |      |     |     |
| --- | --- | --- | --- | ---- | --- | --- | --- | ---- | --- | --- |
|     |     |     |    |      | L   | L   | L   |      |     |     |
|     |     |     |   | ∆i = | D   | AD  | AD  | ∆i . |     |     |
|     |     |     |     | F    |     | −   | 2   | d    |     |     |
|     |     |     |     |      | − L | L   | L   |      |     |     |
|     |     |     |     |      | F   | D   | AD  |      |     |     |
|     |     |     |    |      |     | −   |     |      |     |     |
fo 
These expressions  r ∆i D and ∆i F can now be inserted into the expression

| for ∆Ψ | in  | (5.40) | giving |     |     |     |     |     |     |     |
| ------ | --- | ------ | ------ | --- | --- | --- | --- | --- | --- | --- |
d
|     | ∆Ψ       | =   | L ∆i | +L   | (∆i | +∆i | ) =      |           |     |        |
| --- | -------- | --- | ---- | ---- | --- | --- | -------- | --------- | --- | ------ |
|     |          | d   | d    | d AD | F   | D   |          |           |     |        |
|     |          |     | 2    |      | 2   | 3   |          |           | .   | (5.47) |
|     |          |     | L L  | +L   | L   | 2L  |          |           |     |        |
|     |          | L   | D AD | F    | AD  | AD  | ∆i       | = L ′′ ∆i | ,   |        |
|     |          | d   |      |      | 2 − |     |          | d d       | d   |        |
|     |          | −   |      | L L  | L   |     |          |           |     |        |
|     | (cid:18) |     |      | F D  | AD  |     | (cid:19) |           |     |        |
−
′′
where the subtransient inductance L in the d–axis has been defined and it
d
| can be | rewritten |     | as  |       |     |          |     |     |     |        |
| ------ | --------- | --- | --- | ----- | --- | -------- | --- | --- | --- | ------ |
|        |           |     |     | ′′    | L D | +L F     | 2L  | AD  |     |        |
|        |           |     |     | L = L |     |          | −   | .   |     | (5.48) |
|        |           |     |     | d     | d   |          | 2   |     |     |        |
|        |           |     |     |       | − L | F L D /L |     | 1   |     |        |
AD −

| 5.4. Synchronous, |     | Transient, |     | and Subtransient |     | Inductances |     |     |
| ----------------- | --- | ---------- | --- | ---------------- | --- | ----------- | --- | --- |
73
The time constant of the decay of the current in the damper winding is
much smaller that the time constant in the field winding, see next section,
which means that after a certain time it can be assumed that the current
in the damper winding has decayed to zero, i.e. ∆i = i = 0. The same
|     |     |     |     |     |     |     | D D |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
assumption regarding i D can be made if no damper winding is modelled in
| the d-axis. | This | assumption |     | gives   |       |     |     |        |
| ----------- | ---- | ---------- | --- | ------- | ----- | --- | --- | ------ |
|             |      |            | ∆Ψ  | = 0 = L | ∆i +L | ∆i  |     | (5.49) |
|             |      |            | F   |         | F F   | AD  | d   |        |
which gives
|     |     |     | ∆i  | = (L | /L  | )∆i |     | (5.50) |
| --- | --- | --- | --- | ---- | --- | --- | --- | ------ |
|     |     |     |     | F    | AD  | F d |     |        |
−
| and with | use of | (5.40) | and | i = 0 |     |     |     |     |
| -------- | ------ | ------ | --- | ----- | --- | --- | --- | --- |
D
2
L
|     |     |     |     |          | AD         |       | ′       |        |
| --- | --- | --- | --- | -------- | ---------- | ----- | ------- | ------ |
|     |     | ∆Ψ  | d = | L d      | ∆i         | d = L | d i d , | (5.51) |
|     |     |     |     | − L      |            |       |         |        |
|     |     |     |     | (cid:18) | F (cid:19) |       |         |        |
′
The transient inductance in the d–axis, L , is defined in Equation (5.51) as
d
2
L
|     |     |     |     | L ′ = L | AD    | .   |     | (5.52) |
| --- | --- | --- | --- | ------- | ----- | --- | --- | ------ |
|     |     |     |     | d d     |       |     |     |        |
|     |     |     |     |         | − L F |     |     |        |
The time constant for the decay of the current in the damper winding is
| derived | in the next | section. |     |     |     |     |     |     |
| ------- | ----------- | -------- | --- | --- | --- | --- | --- | --- |
An equivalent analysis to the one above can be performed for the q–
axis, but, since no field winding exists in the q–axis for the model we are
consideringhere, theterminology is somewhatdifferent. For amachine with
salientpolesanddamperwindingintheq–axis,theeffectiveinductanceafter
the current in the damper winding has decayed is practically equal to the
synchronous inductance. Hence it is sometimes said that, for machines with
salient poles, the transient and synchronous inductances in the q–axis are
equal.
With α = π the Park–transformed voltage vector in Equation (5.43)
becomes
|     |     |     | ∆u0 |        |     | 0    |     |        |
| --- | --- | --- | --- | ------ | --- | ---- | --- | ------ |
|     |     |     | ∆u  | = √3∆u |     | 0    |     | (5.53) |
|     |     |     |    | d     |    |      |    |        |
|     |     |     | ∆u  | q      |     | c(t) |     |        |
|     |     |     |    |       |    |      |    |        |
A similar analysis as above will the give the subtransient inductance in q–
axis
L 2
|     |     |     |     | ′′    | AQ  |     |     |        |
| --- | --- | --- | --- | ----- | --- | --- | --- | ------ |
|     |     |     |     | L = L |     |     |     | (5.54) |
|     |     |     |     | q     | q   |     |     |        |
|     |     |     |     |       | − L | Q   |     |        |
for a synchronous machine with one damper winding in the q–axis. Accord-
| ing to | the reasoning | above |     | we have |     |     |     |     |
| ------ | ------------- | ----- | --- | ------- | --- | --- | --- | --- |
′
|     |     |     |     | L = | L . |     |     | (5.55) |
| --- | --- | --- | --- | --- | --- | --- | --- | ------ |
|     |     |     |     | q   | q   |     |     |        |

|     |     |     |     | 5. Synchronous | Machine | Model |
| --- | --- | --- | --- | -------------- | ------- | ----- |
74
in this case.
If one additional damper winding is modelled into the q–axis, a value of
′
L can be derived that differs from L . This derivation is analogous to the
| q           |                     |             |                | q             |           |      |
| ----------- | ------------------- | ----------- | -------------- | ------------- | --------- | ---- |
| one done    | for the inductances |             | in the d–axis. |               |           |      |
| In general, | for the             | inductances | defined,       | the following | relations | hold |
|             |                     |             | L ′′ < L ′     | < L ,         |           |      |
|             |                     |             | d d            | d             |           |      |
(5.56)
|     |     |     | ′′ ′  |       |     |     |
| --- | --- | --- | ----- | ----- | --- | --- |
|     |     |     | L < L | < L . |     |     |
|     |     |     | q q   | q     |     |     |
The subtransient, transient, and synchronous reactances are defined in an
obvious way, e.g. X d = ω0L d etc., which most often are expressed in p.u.
| based on | the machine    | power | and voltage | ratings, | see Table 5.1. |     |
| -------- | -------------- | ----- | ----------- | -------- | -------------- | --- |
| 5.5      | Time constants |       |             |          |                |     |
The time constants that determine how fast transients in the rotor and
damper windings decay after a disturbance depend on the resistances of
thesewindings andassociated inductances. We willherederive the socalled
open circuit time constants whereby it assumed that the stator circuits are
open, i.e. i = i = i = 0, or equivalently i0 = i = i = 0. These
|     | a b | c   |     |     | d q |     |
| --- | --- | --- | --- | --- | --- | --- |
′′
time constants are normally denoted by an index o for open, e.g. T as
do
explained below. An alternative that also occurs in the literature are the
time constants when the stator terminals are short-circuited, which also
uniquleydeterminethewindingresistances. Theopencircuittimeconstants
are normally the ones given by the manufacturer of the generator and can
| be obtained | by measurements. |     |     |     |     |     |
| ----------- | ---------------- | --- | --- | --- | --- | --- |
Thus, suppose now that the stator windings are open and and a step
change in the field voltage at the time t = 0, i.e. u F = u F (0) + ∆u F c(t)
will be investigated, with c(t) being a step function at t = 0. We will here
derive the time constants associated with the field winding and the damper
windinginthed–axis. Thecircuitequations describingthecurrentsinduced
| by the step | in the field | voltage | for these | two windings | are for | t > 0 |
| ----------- | ------------ | ------- | --------- | ------------ | ------- | ----- |
+∆Ψ˙
|     |     | r   | F ∆i F | F = ∆u F c(t) |     |     |
| --- | --- | --- | ------ | ------------- | --- | --- |
(5.57)
|     |     | r   | ∆i +∆Ψ˙ | = 0 |     |     |
| --- | --- | --- | ------- | --- | --- | --- |
|     |     |     | D D     | D   |     |     |
(cid:26)
For a synchronous machine r r and the induced current will conse-
|     |     |     | D F |     |     |     |
| --- | --- | --- | --- | --- | --- | --- |
≫
quently decay much faster in the damper winding than in the field winding.
′′ ′
(This fact was also used above in the derivation of L and L .) Therefore
d d
we will analyze the decay of the current in the damper winding first. Since
i = 0, the fluxes in the field and damper windings can be written as
d
|     |     | ∆Ψ  | D = L D ∆i | D +L AD ∆i | F , |     |
| --- | --- | --- | ---------- | ---------- | --- | --- |
(5.58)
|     |     | ∆Ψ  | = L ∆i | +L ∆i  | .   |     |
| --- | --- | --- | ------ | ------ | --- | --- |
|     |     |     | F F    | F AD D |     |     |
(cid:26)

5.5. Time constants 75
Taking the time derivative of the lower equation in (5.58) gives
∆Ψ˙ = L ∆i˙ +L ∆i˙ . (5.59)
F F F AD D
Fromtheupperequationof(5.57) wecanreplace∆Ψ˙ in(5.59), whichafter
F
some re-arrangements gives
∆u r ∆i L ∆i˙
∆i˙ = F − F F − AD D (5.60)
F
L
F
Now the time derivative of the upper equation of (5.58) is inserted into the
lower equation of (5.57) yielding
r ∆i +L ∆i˙ +L ∆i˙ = 0 , (5.61)
D D D D AD F
in which the expression for ∆i˙ in (5.60) is inserted giving
F
∆u r ∆i L ∆i˙
r ∆i +L ∆i˙ +L F − F F − AD D = 0 . (5.62)
D D D D AD
L
F
This equation can be rewritten as
r L /L L
∆i˙ + D ∆i = ∆u AD F +r AD ∆i . (5.63)
D 2 D F 2 F F
L L /L − L L /L L
D − AD F D − AD F F
As pointed out above the current in the damper circuit will decay must
faster, which means that the current in the field winding, ∆i , can be re-
F
garded as a constant in Equation (5.63). The time constant of the decay of
the damper winding current, ∆i , is the subtransient time constant of the
D
′′
open circuit in the d–axis, T , and can now with the above assumptions be
do
identified from Equation (5.63) as
2
L L /L
T ′′ = D − AD F . (5.64)
do r
D
When i has vanished, i.e. when i = 0, the field current is determined
D D
solely by the upper equation in (5.57), and the transient time constant of
′
the open circuit, T , and together with the lower equation of (5.58) it is
do
easily seen that this time constant is given by
′
T = L /r . (5.65)
do F F
Accordingly, for a synchronous machine with a damper winding in the q–
axis,
′′
T =L /r (5.66)
qo Q Q
can be derived.

|     |     |     |     |     |     | 5.  | Synchronous | Machine Model |
| --- | --- | --- | --- | --- | --- | --- | ----------- | ------------- |
76
|     |     |     |        | Round | Rotor |     | Salient   | Pole |
| --- | --- | --- | ------ | ----- | ----- | --- | --------- | ---- |
|     |     | x   | (p.u.) | 1.0   | – 2.3 |     | 0.6 – 1.5 |      |
d
|     |     | x q | (p.u.) | 1.0  | – 2.3 |     | 0.4 – 1.0 |     |
| --- | --- | --- | ------ | ---- | ----- | --- | --------- | --- |
|     |     | x ′ | (p.u.) | 0.15 | – 0.4 |     | 0.2 – 0.5 |     |
d
|     |     | x ′′ | (p.u.) | 0.12 | – 0.25 |     | 0.15 – 0.35 |     |
| --- | --- | ---- | ------ | ---- | ------ | --- | ----------- | --- |
d
′
|     |     | x   | (p.u.) | 0.3 | – 1.0 |     | —   |     |
| --- | --- | --- | ------ | --- | ----- | --- | --- | --- |
q
′′
|     |     | x   | (p.u.) | 0.12 | – 0.25 |     | 0.2 – 0.45 |     |
| --- | --- | --- | ------ | ---- | ------ | --- | ---------- | --- |
q
′
|     |     | T   | (s) | 3.0 | – 10.0 |     | 1.5 – 9.0 |     |
| --- | --- | --- | --- | --- | ------ | --- | --------- | --- |
do
|     |     | T ′′ | (s) | 0.02 | – 0.05 |     | 0.01 – 0.05 |     |
| --- | --- | ---- | --- | ---- | ------ | --- | ----------- | --- |
do
|     |     | T ′ | (s) | 0.5 | – 2.0 |     | –   |     |
| --- | --- | --- | --- | --- | ----- | --- | --- | --- |
qo
′′
|     |     | T   | (s) | 0.02 | – 0.05 |     | 0.01 – 0.09 |     |
| --- | --- | --- | --- | ---- | ------ | --- | ----------- | --- |
qo
|     |       | H (s)        |        | 3 – | 5 (n = 3000        | rpm) | 1.5 – 5        |           |
| --- | ----- | ------------ | ------ | --- | ------------------ | ---- | -------------- | --------- |
|     |       |              |        | 5 – | 8 (n = 1500        | rpm) |                |           |
|     | Table | 5.1. Typical | values |     | of some parameters |      | of synchronous | machines. |
Thequantitiesintroducedinthisandtheprevioussectionsareimportant
parameters of asynchronousmachine and areusually given by the manufac-
turer of the machine. The reasons for this are that they are easily measured
by simple tests and that they are introduced in a natural way into the sim-
plified models we will derive in the next section. In Table 5.1, typical values
of the discussed parameters for different types and sizes of synchronous ma-
chines are given. Reactances instead of inductances are given in Table 5.1,
i.e. x = ω0L etc., with ω0 = 2πf0. The p.u. base is the power and voltage
|         | d          | d            |        |     |              |             |       |         |
| ------- | ---------- | ------------ | ------ | --- | ------------ | ----------- | ----- | ------- |
| ratings | of         | the machine. |        |     |              |             |       |         |
| 5.6     | Simplified |              | Models |     | of the       | Synchronous |       | Machine |
| 5.6.1   | Derivation |              | of     | the | fourth-order |             | model |         |
Acompleteandexactmodelofthesynchronousmachine,consideringtheas-
sumptions and approximations made, was presented in sections 5.2 and 5.3.
When a synchronous machine is modelled in for example a software package
for stability simulations, these are often the equations used to represent the
synchronous machine. Nevertheless, it is, for several reasons, often mean-
ingful to use models that comprise more simplifications and approximations
than those derived earlier. If a better insight into a problem is wanted or if
a problem is analyzed without using computer simulations, simplified repre-
sentations of the synchronous machine are often the only possibility. Here,
| such | a model | will   | be derived |     | under the  | following | assumptions: |         |
| ---- | ------- | ------ | ---------- | --- | ---------- | --------- | ------------ | ------- |
|      | The     | stator | transients | are | neglected, | i.e.      | we set Ψ˙ =  | Ψ˙ = 0. |
|      |         |        |            |     |            |           | d            | q       |
•

| 5.6. | Simplified |     | Models | of  | the Synchronous |     |     | Machine |     |     |
| ---- | ---------- | --- | ------ | --- | --------------- | --- | --- | ------- | --- | --- |
77
|     | The | d–axis | contains |     | no damper |     | windings. |     |     |     |
| --- | --- | ------ | -------- | --- | --------- | --- | --------- | --- | --- | --- |
•
|     | In  | the q–axis, |     | one damper |     | winding | is  | modelled. |     |     |
| --- | --- | ----------- | --- | ---------- | --- | ------- | --- | --------- | --- | --- |
•
With these assumptions, the synchronous machine is described by the
equations
|     |     |     |     |     | Ψ d = | L d i d | +L AD | i F , |     |        |
| --- | --- | --- | --- | --- | ----- | ------- | ----- | ----- | --- | ------ |
|     |     |     |     |     | Ψ =   | L i     | +L    | i ,   |     |        |
|     |     |     |     |     | q     | q q     | AQ    | Q     |     |        |
|     |     |     |     |    |       |         |       |       |     | (5.67) |
|     |     |     |     |     | Ψ     | = L i   | +L    | i ,   |     |        |
|     |     |     |     |   | F     | F       | F     | AD d  |     |        |

|     |     |     |     |     | Ψ Q | = L Q i | Q +L | AQ i q , |     |        |
| --- | --- | --- | --- | --- | --- | ------- | ---- | -------- | --- | ------ |
|     |     |     |     |    |     |         | +Ψ˙  |          |     |        |
|     |     |     |     |   | u   | = r     | i    | ,        |     |        |
|     |     |     |     |     | F   | F       | F    | F        |     | (5.68) |
+Ψ˙
|     |     |     |     |     | 0   | = r Q i Q |     | Q , |     |     |
| --- | --- | --- | --- | --- | --- | --------- | --- | --- | --- | --- |
(cid:26)
|     |               |     |      |           | u d      | = ri    | d +ωΨ   | q ,          |       |        |
| --- | ------------- | --- | ---- | --------- | -------- | ------- | ------- | ------------ | ----- | ------ |
|     |               |     |      |           |          | −       |         |              |       | (5.69) |
|     |               |     |      |           | u        | = ri    | ωΨ      | .            |       |        |
|     |               |     |      |           | q        |         | q       | d            |       |        |
|     |               |     |      |           | (cid:26) | −       | −       |              |       |        |
| For | completeness, |     | some | relations |          | defined | above   | are repeated | here. |        |
|     |               |     |      |           | L ′      | = L     | L 2     | /L           |       |        |
|     |               |     |      |           |          | d       |         | F            |       |        |
|     |               |     |      |           | d        |         | − A 2 D |              |       | (5.70) |
|     |               |     |      |           | L ′′     | = L     | L       | /L           |       |        |
|     |               |     |      |           | q        | q       | AQ      | Q            |       |        |
|     |               |     |      |           | (cid:26) |         | −       |              |       |        |
The goal is now to eliminate all quantities with indices F and Q, except for
u , from the equations above to get a model that can be used to represent
F
the synchronous machine as a component in a system. That means that the
only quantities that should be present in the model are stator voltages, the
stator current, and u F , which is a control variable that can be changed by
| the | excitation |               | system | as described |     | in   | Chapter     | 6.          |     |     |
| --- | ---------- | ------------- | ------ | ------------ | --- | ---- | ----------- | ----------- | --- | --- |
|     | From       | the Equations |        | (5.67),      |     | i is | eliminated, | which leads | to  |     |
Q
L
|     |     |     |     |     |     | AQ  |     | ′′      |     |        |
| --- | --- | --- | --- | --- | --- | --- | --- | ------- | --- | ------ |
|     |     |     |     |     | Ψ q | Ψ   | Q = | L i q . |     | (5.71) |
|     |     |     |     |     | −   | L   |     | q       |     |        |
Q
| Now,     | by  | defining |     |            |     |      |     |     |     |        |
| -------- | --- | -------- | --- | ---------- | --- | ---- | --- | --- | --- | ------ |
|          |     |          |     |            | ′   | L    | AQ  |     |     |        |
|          |     |          |     |            | e   | = ω  | Ψ   | ,   |     | (5.72) |
|          |     |          |     |            | d   |      |     | Q   |     |        |
|          |     |          |     |            |     |      | L Q |     |     |        |
| Equation |     | (5.71)   | can | be written |     | as   |     |     |     |        |
|          |     |          |     |            |     | ′    |     | ′′  |     |        |
|          |     |          |     |            | Ψ   | e /ω | = L | i . |     | (5.73) |
|          |     |          |     |            | q   | − d  |     | q q |     |        |
Equivalent derivations can be done for the rotor circuit in the d–axis,
| i.e. | for the | field | winding. |     |     |     |     |     |     |     |
| ---- | ------- | ----- | -------- | --- | --- | --- | --- | --- | --- | --- |
L
|     |     |     |     |     |     | AD  |       | ′       |     |        |
| --- | --- | --- | --- | --- | --- | --- | ----- | ------- | --- | ------ |
|     |     |     |     |     | Ψ d |     | Ψ F = | L d i d |     | (5.74) |
|     |     |     |     |     | −   | L   |       |         |     |        |
F
| is  | obtained, | which, | using |     | the definition |     |     |     |     |     |
| --- | --------- | ------ | ----- | --- | -------------- | --- | --- | --- | --- | --- |
L
|     |     |     |     |     | e ′ | = ω | AD Ψ | ,   |     | (5.75) |
| --- | --- | --- | --- | --- | --- | --- | ---- | --- | --- | ------ |
|     |     |     |     |     | q   |     |      | F   |     |        |
− L
F

|     |     |     |     |     |     |     | 5.  | Synchronous | Machine | Model |
| --- | --- | --- | --- | --- | --- | --- | --- | ----------- | ------- | ----- |
78
| can be          | written        | as  |      |               |          |        |       |               |     |        |
| --------------- | -------------- | --- | ---- | ------------- | -------- | ------ | ----- | ------------- | --- | ------ |
|                 |                |     |      |               | Ψ +e     | ′ /ω = | L ′ i | .             |     | (5.76) |
|                 |                |     |      |               | d        | q      | d d   |               |     |        |
| Now,            | the quantities |     |      |               |          |        |       |               |     |        |
|                 |                |     |      |               | e =      | ωL     | i ,   |               |     |        |
|                 |                |     |      |               | d        | AQ     | Q     |               |     | (5.77) |
|                 |                |     |      |               | e q =    | ωL AD  | i F   |               |     |        |
|                 |                |     |      |               | (cid:26) | −      |       |               |     |        |
| are introduced. |                |     | From | the equations |          | above, | the   | relationships |     |        |
|                 |                |     |      |               | ′        |        | ′′    |               |     |        |
|                 |                |     |      | e             | = e      | (x     | x )i  | ,             |     |        |
|                 |                |     |      |               | d d−     | q −    | q     | q             |     |        |
(5.78)
|     |     |     |     | e   | = e ′ | +(x | x ′ )i | ,   |     |     |
| --- | --- | --- | --- | --- | ----- | --- | ------ | --- | --- | --- |
|     |     |     |     | (   | q q   | d   |        | d   |     |     |
− d
| with      | x = | ωL etc. | can       | be  | obtained. |             |         |     |     |        |
| --------- | --- | ------- | --------- | --- | --------- | ----------- | ------- | --- | --- | ------ |
|           | d   | d       |           |     |           |             |         |     |     |        |
| According |     | to      | Equations |     | (5.77)    | and (5.78), |         |     |     |        |
|           |     |         |           |     | e ′       | (x          | x ′′ )i |     |     |        |
|           |     |         |           |     | d−        | q           | q q     |     |     |        |
|           |     |         |           | i   | =         | −           |         | .   |     | (5.79) |
|           |     |         |           | Q   |           | ωL          |         |     |     |        |
AQ
Substituting this into the second equation of (5.68), which together with
(5.72) give
|     |     |     |     | ′   |      | ′′  |     |      |     |        |
| --- | --- | --- | --- | --- | ---- | --- | --- | ---- | --- | ------ |
|     |     |     |     | e   | (x x | )i  | L   |      |     |        |
|     |     |     |     | d−  | q    | q q | Q   | ′    |     |        |
|     |     |     | r Q |     | −    | +   |     | e˙ = | 0 , | (5.80) |
|     |     |     |     |     | ωL   |     | ωL  | d    |     |        |
|     |     |     |     |     | AQ   |     | AQ  |      |     |        |
where it has been assumed that ω˙ = 0 or ω = ω0. Equation (5.80) can also
| be written |     | as  |     |           |      |     |         |       |     |        |
| ---------- | --- | --- | --- | --------- | ---- | --- | ------- | ----- | --- | ------ |
|            |     |     |     | T ′′ e˙ ′ | +e ′ | (x  | x ′′ )i | = 0 . |     | (5.81) |
|            |     |     |     | qo d      | d    | q   | q q     |       |     |        |
|            |     |     |     |           | −    | −   |         |       |     |        |
For the rotor circuit in the d–axis, i.e. for the exciter winding, accordingly
ωL
|     |     |     | ′   | ′     | ′   | ′    |     | AD  |     |        |
| --- | --- | --- | --- | ----- | --- | ---- | --- | --- | --- | ------ |
|     |     |     | T   | e˙ +e | +(x | x )i | =   |     | u   | (5.82) |
|     |     |     | do  | q     | q d | − d  | d − | r   | F   |        |
F
| is obtained, |     | which, | using |     |     |     |     |     |     |     |
| ------------ | --- | ------ | ----- | --- | --- | --- | --- | --- | --- | --- |
ωL AD
|     |     |     |     |     | e = |     | u , |     |     | (5.83) |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | ------ |
|     |     |     |     |     | F   | r   | F   |     |     |        |
F
| can be | written | as  |     |       |     |     |      |     |     |        |
| ------ | ------- | --- | --- | ----- | --- | --- | ---- | --- | --- | ------ |
|        |         |     |     | ′ ′   | ′   |     | ′    |     |     |        |
|        |         |     | T   | e˙ +e | +(x | x   | )i = | e   | .   | (5.84) |
|        |         |     |     | do q  | q   | d   | d d  | F   |     |        |
|        |         |     |     |       |     | −   |      | −   |     |        |
If Equations (5.81) and (5.84) are Laplace–transformed and the voltage
equation (5.69) is rewritten with the introduced quantities, we obtain
|     |          | ∆u  |                   | ∆e ′ |                   | r   | x ′′ | ∆i               |            |        |
| --- | -------- | --- | ----------------- | ---- | ----------------- | --- | ---- | ---------------- | ---------- | ------ |
|     |          | d   |                   | d    |                   | d   | q    |                  | d          |        |
|     |          |     | =                 | ′    | +                 | − ′ |      |                  | ,          | (5.85) |
|     |          | ∆u  |                   | ∆e   |                   | x   | r    | ∆i               |            |        |
|     | (cid:18) | q   | (cid:19) (cid:18) | q    | (cid:19) (cid:18) | d   | q    | (cid:19)(cid:18) | q (cid:19) |        |
|     |          |     |                   |      |                   | −   | −    |                  |            |        |
′
| with | e given | by  |     |     |     |     |     |     |     |     |
| ---- | ------- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
d
|     |     |     |     |     |      | (x x   | ′′ )∆i |     |     |        |
| --- | --- | --- | --- | --- | ---- | ------ | ------ | --- | --- | ------ |
|     |     |     |     |     | ′    | q      | q      | q   |     |        |
|     |     |     |     |     | ∆e = | −      |        |     |     | (5.86) |
|     |     |     |     |     | d    | 1+sT′′ |        |     |     |        |
qo

| 5.6. | Simplified |     | Models | of the | Synchronous |     | Machine |     |     |     |
| ---- | ---------- | --- | ------ | ------ | ----------- | --- | ------- | --- | --- | --- |
79
′
and e from
q
′
|     |     |     |     | ′    | ∆e  | F +(x | d x )∆i | d   |     |        |
| --- | --- | --- | --- | ---- | --- | ----- | ------- | --- | --- | ------ |
|     |     |     |     | ∆e = |     |       | − d     |     | .   | (5.87) |
|     |     |     |     | q    |     | 1+sT′ |         |     |     |        |
−
do
This model, i.e. Equations (5.85)–(5.87), together with the swing equation,
are often called the fourth order model. This model of the synchronous
machine demands, with the assumptions made here, four state variables:
| ′   |        | ′   |     |              |     |            |     |     |     |     |
| --- | ------ | --- | --- | ------------ | --- | ---------- | --- | --- | --- | --- |
| ∆e  | and ∆e | and | the | “mechanical” |     | quantities | ∆ω  | and | ∆δ. |     |
| d   |        | q   |     |              |     |            |     |     |     |     |
Often, also the damper winding in the q–axis can be neglected. That
| leads | to a     | third | order    | model,     | which             | can | be written           | as  |            |        |
| ----- | -------- | ----- | -------- | ---------- | ----------------- | --- | -------------------- | --- | ---------- | ------ |
|       |          | ∆u    |          | 0          |                   | r   | x                    | ∆i  |            |        |
|       |          | d     | =        |            | +                 | d   | q                    |     | d ,        | (5.88) |
|       |          |       |          | ′          |                   | − ′ |                      |     |            |        |
|       |          | ∆u    |          | ∆e         |                   | x   | r                    | ∆i  |            |        |
|       | (cid:18) | q     | (cid:19) | (cid:18) q | (cid:19) (cid:18) | − d | − q (cid:19)(cid:18) |     | q (cid:19) |        |
′
| with | ∆e  | according | to  | Equation | (5.87). |     |     |     |     |     |
| ---- | --- | --------- | --- | -------- | ------- | --- | --- | --- | --- | --- |
q
| 5.6.2 | The | Heffron-Phillips |     |     | formulation |     | for | stability | studies |     |
| ----- | --- | ---------------- | --- | --- | ----------- | --- | --- | --------- | ------- | --- |
The third-order model of the synchronous machine derived in the previous
section can be formulated as a block diagram. The basis for the model
presented here, which was originally proposed by Heffron and Phillips, is
the ”single machine, infinite bus” (SMIB) setup. By introducing a number
of new constants, a very compact notation is achieved. The model shall
enable the reader to directly implement a usable representation of an SMIB
system, including the mechanical dynamics, field winding, and excitation
system. This implementation can be used directly for stability studies. In
the present case, a generic simplified representation of the excitation system
is used. Detailed descriptions and common variants of these systems can be
| found       | in chapter |               | 6.  |     |              |     |          |         |     |     |
| ----------- | ---------- | ------------- | --- | --- | ------------ | --- | -------- | ------- | --- | --- |
| Background: |            | Low-frequency |     |     | oscillations |     | in power | systems |     |     |
In large interconnected power systems, low-frequency oscillations can arise
spontaneously. Unlike the electro-mechanical oscillations described by the
swingequation, theseoscillations haveafrequencyofwellbelow1Hz(about
3 – 10 cycles per minute depending on the power system). They are known
to either decay slowly or continue to grow, which leads eventually to system
separation. The main cause of the oscillations is a lack of damping in the
system due to the effect of excitation systems in synchronous machines.
An effective countermeasure to low-frequency oscillations is the usage of
Power Systems Stabilizers (PSS). These are automatic controllers acting on
the excitation systems, providing an additional damping component which
leadstoanattenuation oftheoscillations. Furtherdetailsaboutthissystem,
which can be directly attached to the Heffron-Phillips model derived in this
| section, | will | be presented |     | in  | the chapters |     | 6 and | 7.  |     |     |
| -------- | ---- | ------------ | --- | --- | ------------ | --- | ----- | --- | --- | --- |

80 5. Synchronous Machine Model
Block diagram
Figure 5.5 presents the transfer function block diagram of the Heffron-
Phillips model. Note that all quantities are presented in per unit. The
mechanical system is represented by the system inertia and the damping
constant, where the torque balance ∆T ∆T is considered as an input
m e
−
and the incremental torque angle ∆δ as an output. The electrical part of
the system consists of three main parts: 1) the composition of the electri-
cal torque (influenced by ∆δ over constant K1 and the internal incremental
′
voltage ∆e
q
over constant K2), 2)theeffect of thefieldwinding(determined
by the field winding constant K3 and influenced by ∆δ over constant K4),
and 3) the effect of the excitation system (influenced by ∆δ over constant
′
K5 and ∆e
q
over constant K6). The excitation system itself is modeled by
a first-order transfer function including the amplification factor K and the
A
time constant T .
A

| 5.6. Simplified | Models | of the | Synchronous |     | Machine |     |     |     |     |
| --------------- | ------ | ------ | ----------- | --- | ------- | --- | --- | --- | --- |
81
(cid:71)(cid:39)
suonorhcnyS
 deeps
f(cid:83)2 0
s
|     |     |     | (cid:90)(cid:39) |     |     |     |  elgna euqrot fo ecneulfnI |  elgna euqrot fo ecneulfnI |     |
| --- | --- | --- | ---------------- | --- | --- | --- | -------------------------- | -------------------------- | --- |
 tnatsnoc gnipmaD
 egatlov lanimret no
|     |     |  egnahc euqrot |     |  aitreni metsyS |     |     |  euqrot cirtcele no |     |     |
| --- | --- | -------------- | --- | --------------- | --- | --- | ------------------- | --- | --- |
lacinahceM
sH2
|     |     |     | 1   |     | D   | K 1 |     | 5   |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
|     |     |     |     |     | K   |     |     | K   |     |
.metsys
m
|     |     | T(cid:39) | (cid:14) | (cid:16) |     |     |     |     | BIMS |
| --- | --- | --------- | -------- | -------- | --- | --- | --- | --- | ---- |
(cid:16)
e
|     |     |     | T(cid:39) |     |     |     |     |     | a   |
| --- | --- | --- | --------- | --- | --- | --- | --- | --- | --- |
ni
enihcam
(cid:14)
(cid:14)
|     |     |     |     |  no egatlov lanretni |  egatlov lanretni |     |     |     |     |
| --- | --- | --- | --- | -------------------- | ----------------- | --- | --- | --- | --- |
 euqrot cirtcele
|     |     |     |     |  fo ecneulfnI |  fo ecneulfnI  lanimret no |     |     |     | suonohcnys |
| --- | --- | --- | --- | ------------- | -------------------------- | --- | --- | --- | ---------- |
 egatlov dleif no elgna
|     |     |  euqrot fo ecneulfnI |     | 2   |  egatlov |     |     |     |     |
| --- | --- | -------------------- | --- | --- | -------- | --- | --- | --- | --- |
K
(cid:14)
4
K
|     |     |     | 'e(cid:39) q |     |     |     | (cid:14) |     | gnitneserper |
| --- | --- | --- | ------------ | --- | --- | --- | -------- | --- | ------------ |
6
K
1(cid:14)s gnidniw dleiF
3
K(cid:16) 3
K
|     |     |     |     | 'T od |     |     |     |     | margaid |
| --- | --- | --- | --- | ----- | --- | --- | --- | --- | ------- |
F
|     |     |     | e(cid:39) |     |     |     |     |     | kcolB |
| --- | --- | --- | --------- | --- | --- | --- | --- | --- | ----- |
(cid:14)
.5.5
(cid:16)  metsys noitaticxE
erugiF
1(cid:14)s
A
K
A
T
u(cid:39) t
(cid:16)
(cid:14)0(cid:32) (cid:14)
|     |     | egatloV tnioptes | egnahc |     |     |     |     |     |     |
| --- | --- | ---------------- | ------ | --- | --- | --- | --- | --- | --- |
tesu(cid:39)
t

82 5. Synchronous Machine Model
Derivation of constants K1...K6
The constants K1...K6 shown in Figure 5.5 describe internal influence fac-
torswithinthesystem andcan befoundbyacomparisonof coefficients with
the equations governing the synchronous machine dynamics. While K1 and
K2 arederived from thecomputation of theelectric torque, K3 andK4 have
their origin in the field voltage equation (5.87). K5 and K6 come from the
equation governing the terminal voltage magnitude. Below we will calculate
these constants from the previously presented third-order model.
SMIB system setup: The power system under consideration is a so-called
”single machine, infinite bus” (SMIB) system. This means that one syn-
chronousgeneratorisconnectedviaatransmissionline(representedbyseries
impedance Z = R+jX and shunt admittance Y = G+jB) to an ”infinite”
bus with constant voltage u0. The generator has a terminal voltage u
t
and
injects the armature current i via its terminals. For the calculations below,
the armature currents i and i are assumed to be known.
d q
Thecurrentandvoltage phasors aredefinedas shownin Figure 5.6. The
torque angle δ is defined as the angle between u0 and the internal voltage
′
e . The following definitions will be used later in the computations:
q
i = i +ji , v = v +jv ,
d q t d q
1+ZY = C1+jC2 ,
′
R1 = R
−
C2x
d ′
, X1 = X +C1x
q
,
(5.89)
X2 = X +
2
C1x
d
, R2 = R
−
C2x
q
,
Z
e
= R1R2+X1X2 ,
2 2
Y
d
= (C1X1 C2R2)/Z
e
, Y
q
= (C1R1+C2X2)/Z
e
,
−
Thevoltages andcurrentintheSMIBsystem arerelated totheadmittances
and impedances by
−1
i = Yu
t
+Z (u
t
u0) or Zi= (1+ZY)u
t
u0 . (5.90)
− −
This can be separated into real and imaginary parts, which yields
R X i
d
C1 C2 u
d
sinδ
− = − u0 , (5.91)
X R i q C2 C1 u q − cosδ
(cid:20) (cid:21)(cid:20) (cid:21) (cid:20) (cid:21)(cid:20) (cid:21) (cid:20) (cid:21)
where
C1 = 1+RG XB , C2 = XG+RB . (5.92)
−
Now, Equation (5.88) is taken into account with one further simplification:
the armature resistance is neglected, i.e. r = r = 0. This can be inserted
d q
into Equation (5.91), which yields
i
d
Y
d ′
u0 R2 X1 sinδ
= e . (5.93)
(cid:20) i q (cid:21) (cid:20) Y q (cid:21) q − Z e 2 (cid:20) − X2 R1 (cid:21)(cid:20) cosδ (cid:21)

5.6. Simplified Models of the Synchronous Machine 83
q-axis
e‘ u
q t
i
u
0
d-axis
Figure 5.6. Phasor diagram of SMIB system.
This can be linearized again, resulting in
∆i Y F
d d ′ d
= ∆e + ∆δ , (5.94)
∆i Y q F
q q q
(cid:20) (cid:21) (cid:20) (cid:21) (cid:20) (cid:21)
with the constants F and F introduced for abbreviation, which are equal
d q
to
F
d
u0 R2 X1 cosδ0
= − , (5.95)
(cid:20) F q (cid:21) Z e 2 (cid:20) X2 R1 (cid:21)(cid:20) sinδ0 (cid:21)
where δ0 is the initial torque angle.
Now, the constants K1...K6 can be defined in terms of the introduced
notation.
K1 and K2 from electric torque: The electric torque of a synchronous
machine can be approximated by the electric power for small deviations
from the synchronous speed. The overall power is the sum of powers in the
d- and q-axis:
T P = i u +i u . (5.96)
e e d d q q
≈
Taking into account Equation (5.88) with r = r = 0, Equation (5.96) can
d q
be written as
′ ′
T =i e +(x x )i i . (5.97)
e q q q d d q
−
MergingthiswithEquation(5.94), thisyields withonefurtherlinearization:
′
∆T
e
= K1∆δ+K2∆e
q
, (5.98)
where the wanted constants K1 and K2 are equal to:
′
K1 = 0 + F d F q ′ (x q − x d )i q ′ 0 . (5.99)
(cid:20) K2 (cid:21) (cid:20) i q0 (cid:21) (cid:20) Y d Y q (cid:21)(cid:20) e q0 +(x q − x d )i d0 (cid:21)

84 5. Synchronous Machine Model
K3 and K4 from field voltage equation: The field winding circuit voltage
equation from (5.84) can be linearized, which yields
′ ′ ′
(1+sT )∆e = ∆e (x x )∆i . (5.100)
do q F d d d
− − −
Substituting ∆i of Equation (5.94) into this yields
d
′ ′
(1+sT
do
K3)∆e
q
= K3(∆e
F
+K4∆δ) (5.101)
−
where
′
K3 = 1/(1+(x
d
x
d
)Y
d
) (5.102)
−
′
K4 = (x
d
x
d
)F
d
. (5.103)
−
K5 and K6 from terminal voltage magnitude: The magnitude of the ter-
minal voltage of the generator can beexpressed by the d and q components:
2 2 2
u = u +u . (5.104)
t d q
The deviation from a steady state is thus equal to
∆u
t
= (u d0/u t0)∆u
d
+(u q0/u t0)∆u
q
. (5.105)
Substituting Equation (5.94) into Equation (5.105) yields
′
∆u
t
= K5∆δ+K6∆e
q
, (5.106)
where
′
K5 = 0 + F d F q − x d u q0/u t0 . (5.107)
K6 u q0/u t0 Y d Y q x q u d0/u t0
(cid:20) (cid:21) (cid:20) (cid:21) (cid:20) (cid:21)(cid:20) (cid:21)
Note that all subscripts 0 denote steady-state quantities in this section.
Excitation system parameters: The only missing parameters for the com-
pletion of the Heffron-Phillips model are the excitation system parameters
K andT . Thecorrespondingtransferfunctionrepresentsagenericexciter
A A
and voltage regulator of the fast-response type. Reasonable values for the
parameters are K 50 and T 0.05 s.
A A
≈ ≈

6
Voltage Control in Power Systems
Having introduced the principal governing equations for the synchronous ma-
chine in the previous chapter, this chapter deals with the basics of voltage
control in electric power systems. First, the relation between voltage and
the reactive power balance is discussed and various influences to this balance
are presented. The primary voltage control equipment in the synchronous
machine is also discussed and finally a short description of the hierarchical
voltage control structure is provided. The following structure is based on
[6]
6.1 Relation between voltage and reactive power
As explained in detail in chapters 2 – 4, the active power balance of a power
system must be maintained in order to keep the system in steady state.
Furthermore, the reactive power balance must be kept in such a way that
the voltages are within the acceptable limits. If the active power balance is
not kept, the frequency in the system will be influenced, while an improper
reactive power balance will result in deviations of the voltages in the system
1
from the desired ones.
Normallythepowersystemisoperatedsuchthatthevoltage dropsalong
thelinesaresmall. Thenodevoltagesofthesystemwillthenalmostbeequal
(flatvoltage profile). Inthis case thetransmissionsystem is effectively used,
i.e. primarily for transmission of active power, and not for transmission of
reactive power.
Thus, the voltage magnitudes can be controlled to desired values by
control of thereactive power. Increased productionof reactive power results
inhighervoltageneartheproductionsource,whileanincreasedconsumption
of reactive power results in lower voltage. While the active power is entirely
producedbythegeneratorsinthesystem,thereareseveralsourcesandsinks
of reactive power. On the other hand, the reactive power, in contrast with
the active power, cannot be transported over long distances in the system,
1Thefrequencydeviationisaconsequenceofanimbalancebetweenpowerfedintothe
system by the prime movers and the electric power consumed by the loads and losses.
However, the generated reactive power is always equal to the consumed reactive power,
which is a consequence of Kirchhoff’s laws. The voltage magnitudes are always adjusted
such that this balance is maintained. If the voltages settle at too low values, the reason
is that the reactive generation is too small. Vice versa, overvoltages arise when reactive
generation is too high. However, this does not mean that the generated and consumed
reactive power is not equalas in the case of activepower.
85

|     |     |     |     |     |     | 6. Voltage | Control | in Power | Systems |
| --- | --- | --- | --- | --- | --- | ---------- | ------- | -------- | ------- |
86
since normally X >> R in a power system. Consequently, the reactive
| power | can         | be regarded |             | as a | fairly   | local quantity. |     |     |     |
| ----- | ----------- | ----------- | ----------- | ---- | -------- | --------------- | --- | --- | --- |
|       | Important   |             | generators  | of   | reactive | power are:      |     |     |     |
|       | Overexcited |             | synchronous |      | machines |                 |     |     |     |
•
|     | Capacitor |     | banks |     |     |     |     |     |     |
| --- | --------- | --- | ----- | --- | --- | --- | --- | --- | --- |
•
|     | The | capacitance |     | of overhead |     | lines and cables |     |     |     |
| --- | --- | ----------- | --- | ----------- | --- | ---------------- | --- | --- | --- |
•
2
|     | FACTS | devices |     |     |     |     |     |     |     |
| --- | ----- | ------- | --- | --- | --- | --- | --- | --- | --- |
•
| Important |           | consumers |        | of reactive |     | power are: |     |     |     |
| --------- | --------- | --------- | ------ | ----------- | --- | ---------- | --- | --- | --- |
|           | Inductive |           | static | loads       |     |            |     |     |     |
•
|     | Underexcited |     | synchronous |     |     | machines |     |     |     |
| --- | ------------ | --- | ----------- | --- | --- | -------- | --- | --- | --- |
•
|     | Induction |     | motors |     |     |     |     |     |     |
| --- | --------- | --- | ------ | --- | --- | --- | --- | --- | --- |
•
|     | Shunt | reactors |     |     |     |     |     |     |     |
| --- | ----- | -------- | --- | --- | --- | --- | --- | --- | --- |
•
|     | The | inductance |     | of overhead |     | lines and cables |     |     |     |
| --- | --- | ---------- | --- | ----------- | --- | ---------------- | --- | --- | --- |
•
|     | Transformer |     | inductances |     |     |     |     |     |     |
| --- | ----------- | --- | ----------- | --- | --- | --- | --- | --- | --- |
•
|     | FACTS | devices |     |     |     |     |     |     |     |
| --- | ----- | ------- | --- | --- | --- | --- | --- | --- | --- |
•
For some of these, the reactive power is easy to control, while for others
itis practically impossible. Thereactive power of the synchronousmachines
iseasily controlled bymeansoftheexcitation. Switchingofshuntcapacitors
and reactors can also control the reactive power. FACTS devices offer also
| a   | possibility | to  | control | the | reactive | power. |     |     |     |
| --- | ----------- | --- | ------- | --- | -------- | ------ | --- | --- | --- |
It is most effective to compensate the reactive power as close as possible
tothereactive load. Therearecertain highvoltage tariffstoencouragelarge
consumers,e.g.industries,andelectricaldistributionscompaniestocompen-
sate their loads in an effective way. These tariffs are generally designed so
that the reactive power is only allowed to reach a certain percentage of the
active power. If this percentage is exceeded, the consumer has to pay for
the reactive power. The high voltage network is in this way primarily used
| for | transmission |     | of active | power. |     |     |     |     |     |
| --- | ------------ | --- | --------- | ------ | --- | --- | --- | --- | --- |
Thereactive losses of power lines and transformers depend on the size of
the reactance. For overhead-transmission lines the reactance can be slightly
reduced by the use of multiple conductors. The only possibility to radi-
cally reduce the total reactance of a transmission line s to connect a series
| capacitor |     | or a | series FACTS |     | device. |     |     |     |     |
| --------- | --- | ---- | ------------ | --- | ------- | --- | --- | --- | --- |
2FACTS
|     |     | = Flexible | AC  | Transmission |     | Systems. FACTS | devices | are power | electronics |
| --- | --- | ---------- | --- | ------------ | --- | -------------- | ------- | --------- | ----------- |
devices equipped with fast control that can often can be used for reactive power control.
They can normally be used both as reactive power sources and sinks. Furtherdiscussion
| of  | FACTS | devices | is given | in theSection |     | 6.3.4. |     |     |     |
| --- | ----- | ------- | -------- | ------------- | --- | ------ | --- | --- | --- |

| 6.2. Voltage | Control | Mechanisms |     |     |
| ------------ | ------- | ---------- | --- | --- |
87
| 6.2 Voltage | Control | Mechanisms |     |     |
| ----------- | ------- | ---------- | --- | --- |
The following factors influence primarily the voltages in a power system:
| Terminal | voltages | of synchronous | machines |     |
| -------- | -------- | -------------- | -------- | --- |
•
| Impedances | of  | lines |     |     |
| ---------- | --- | ----- | --- | --- |
•
| Transmitted | reactive | and active | power |     |
| ----------- | -------- | ---------- | ----- | --- |
•
| Turns | ratio of | transformers |     |     |
| ----- | -------- | ------------ | --- | --- |
•
| A suitable | use of | these leads to | the desired voltage | profile. |
| ---------- | ------ | -------------- | ------------------- | -------- |
Thegenerators are often operated at constant voltage, by usingan auto-
matic voltage regulator (AVR). Theoutputfromthis controls theexcitation
of the machine via the electric field exciter. In that way, the voltage can
be kept equal to the set value. The voltage drop caused by the generator
transformer is sometimes compensated totally or partly by this means, and
the voltage can consequently be kept constant on the high voltage side of
the transformer. Synchronous compensators can also be installed for volt-
age control. Thesearesynchronous machines withoutturbineor mechanical
load, which can produce and consume reactive power by controlling the ex-
citation. Nowadays new installations of synchronous compensators are very
rare, and power electronics based solutions are preferred if fast voltage con-
trol is needed.
The reactive power transmitted over a line has a great impact on the
voltage profile. Large reactive transmissions cause large voltage drops, thus
these should be avoided. Instead, the production of reactive power should
be as close as possible to the reactive loads. This can be made by the exci-
tation of the synchronous machines, as described above. However, there are
often no synchronous machines close to the load, so the most cost-effective
way is touseshuntcapacitors which areswitched accordingto theload vari-
ations. A power electronics based device can be economically motivated if
fast response or accuracy in the regulation is required. Shunt reactors must
sometimes be installed to limit the voltages to reasonable levels. In net-
works which contain a lot of cables this is also necessary, since the reactive
generation from these is much larger than from overhead lines. (C is much
| larger and | X is smaller.) |     |     |     |
| ---------- | -------------- | --- | --- | --- |

88 6. Voltage Control in Power Systems
6.3 Primary Voltage Control
The task of the primary voltage control is to control the reactive output
from a device so that the voltage magnitude is kept at or close to the set
value of the controller. Usually the node of the controlled voltage is at the
same or very close to the node of the reactive device, since reactive power is
a fairly local quantity. The set values for the voltage controllers are selected
so that the desired voltage profile of the system is obtained. The selection
of set values is the task of the secondary voltage control, which is briefly
summarized in section 6.4.
In the following the most important devices for reactive power and volt-
age control are described.
6.3.1 Synchronous Machine Excitation System and AVR
The reactive power output of synchronous machine can for a given active
power level be adjusted within the limits of the capability curve by the
excitation system. This offers a very efficient and fast way to control the
terminal voltage of the machine, which in most power system is the most
important voltage control.
The main purpose of the excitation system is to feed the field winding
of the synchronous machine with direct current so that the main flux in the
rotor is generated. Further, the terminal voltage of the synchronous ma-
chine is controlled by the excitation system, which also performs a number
of protection and control tasks. A schematic picture of a generator with
excitation system is depicted in Figure 6.1. Below, a short description of
the functions of the different blocks in Figure 6.1 is given:
The exciter supplies the field winding with direct current and thus
•
comprises the “power part” of the excitation system.
The controller treats and amplifies the input signals to a level and
•
formthatissuitedforthecontrol of theexciter. Inputsignals arepure
control signals as well as functions for stabilizing the exciter system.
The voltage measurement and load compensation unit mea-
•
sures the terminal voltage of the generator and rectifies and filters it.
Further, load compensation can be implemented if the voltage in a
point apart from the generator terminals, such as in a fictional point
inside the generator’s transformer, should be kept constant.
The power system stabilizer, PSS, gives a signal that increases
•
the damping to the controller, cf. Chapter 7. Usual input signals for
the PSS are deviations in rotor speed, accelerating power, or voltage
frequency.

| 6.3. Primary | Voltage | Control |     |     |     |     |     |     |     |
| ------------ | ------- | ------- | --- | --- | --- | --- | --- | --- | --- |
89
Limiter and
Protection
Voltage
Measurements
Load Compensation
A
Synchronous
| Regulator |     |     | Exciter |     |     |     |     |     |     |
| --------- | --- | --- | ------- | --- | --- | --- | --- | --- | --- |
Machine
PSS
= To the Power System
A
| Figure 6.1. | Schematic |     | picture | ofa | synchronousmachinewith |     |     | excita- |     |
| ----------- | --------- | --- | ------- | --- | ---------------------- | --- | --- | ------- | --- |
tionsystemwithseveralcontrol,protection,andsupervisoryfunctions.
| The limiter | and | protectioncancontain |     |     |     | alargenumberoffunctions |     |     |     |
| ----------- | --- | -------------------- | --- | --- | --- | ----------------------- | --- | --- | --- |
•
that ensure that different physical and thermal limits, which genera-
tor and exciter have, are not exceeded. Usual functions are current
limiters, over–excitation protection, and under–excitation protection.
Many of these ensure that the synchronous machine does not produce
| or absorb | reactive | power |     | outside | of the | limits | it is designed | for. |     |
| --------- | -------- | ----- | --- | ------- | ------ | ------ | -------------- | ---- | --- |
Today,alargenumberofdifferenttypesofexciter systemsisused. Three
| main types can | be distinguished: |     |     |     |     |     |     |     |     |
| -------------- | ----------------- | --- | --- | --- | --- | --- | --- | --- | --- |
DC excitation system, where the exciter is a DC generator, often
•
| on the same   | axis | as      | the rotor | of    | the synchronous |     | machine. |         |      |
| ------------- | ---- | ------- | --------- | ----- | --------------- | --- | -------- | ------- | ---- |
| AC excitation |      | system, |           |       |                 |     |          |         |      |
|               |      |         |           | where | the exciter     |     | is an AC | machine | with |
•
rectifier.
Static excitation system, where the exciting current is fed from a
•
controlled rectifier that gets its power either directly from the gen-
erator terminals or from the power plant’s auxiliary power system,
normally containing batteries. In the latter case, the synchronous ma-
chine can be started against an unenergised net, “black start”. The
| batteries | are usually |     | charged | from | the | net. |     |     |     |
| --------- | ----------- | --- | ------- | ---- | --- | ---- | --- | --- | --- |
Below, a more comprehensive treatment of some of the functions de-
| scribed above | is given. |     |     |     |     |     |     |     |     |
| ------------- | --------- | --- | --- | --- | --- | --- | --- | --- | --- |

|     |     |     | 6. Voltage | Control | in Power | Systems |
| --- | --- | --- | ---------- | ------- | -------- | ------- |
90
| U T |       |            |      |                    |     | - U |
| --- | ----- | ---------- | ---- | ------------------ | --- | --- |
|     |       |            | U    |                    | 1   | err |
|     |       |            | c    | ------------------ |     |     |
| I   | U = U | T +(R + jX | )I T | 1+sT               |     | Σ   |
| T   | c     | c          | c    |                    | R   |     |
+
U
ref
|                   | Figure 6.2. | Block diagram | of compensating |     | circuit. |     |
| ----------------- | ----------- | ------------- | --------------- | --- | -------- | --- |
| Load Compensation |             | Equipment     |                 |     |          |     |
Figure 6.2 shows the block diagram of a compensation circuit, consisting of
| a converter | for measured | values, a | filter, and | a comparator. |     |     |
| ----------- | ------------ | --------- | ----------- | ------------- | --- | --- |
There are several reasons for the use of compensation in voltage control
of synchronous machines. If two or more generators are connected to the
same bus, the compensation equipment can be used to create an artificial
impedancebetweenthose. Thatisnecessarytodistributethereactivepower
in an appropriate way between the machines. The voltage is measured
“somewhat inside” the generator, corresponding to positive values of R c
and X in Figure 6.2. If a machine is connected with a comparatively large
c
impedance to the system, which usually is the case since the generator’s
transformer normally has an impedance in the order of magnitude of 10%
on basis of the machine, it can be desirable to compensate a part of this
impedance by controlling the voltage “somewhat inside” of that impedance.
This then corresponds to negative values of R and X . As a rule, X is
|               |            |     |     | c   | c   | c   |
| ------------- | ---------- | --- | --- | --- | --- | --- |
| much larger   | than R c . |     |     |     |     |     |
| DC Excitation | Systems    |     |     |     |     |     |
Today, hardly any DC excitation systems are being installed, but many of
these systems are still in operation. Generally, it can be said that there is
a large number of variants of the different excitation systems listed above.
Every manufacturer uses its own design, and demands that depend on the
application often lead to considerable differences in the detailed models of
thedevicesineachgroup. Here,typicalexamplesformodelswillbegiven. In
reality, the models given by the manufacturers and power suppliers must be
used. One example of a DC excitation system, the IEEE type DC1 system,
is given in Figure 6.3. The input signal for the controller is the voltage
error U from the compensation equipment. The stabilizing feedback U
| err |     |     |     |     |     | F   |
| --- | --- | --- | --- | --- | --- | --- |
is subtracted, and sometimes a signal from the PSS is added. Both these
signals vanish in steady state. The controller is mainly described by the
dominating time constant T and the amplification K . The limits can
|     |     | A   |     |     | A   |     |
| --- | --- | --- | --- | --- | --- | --- |
represent saturation effects or limitations of the power supply. The time

| 6.3. | Primary | Voltage | Control |     |     |     |     |     |     |     |
| ---- | ------- | ------- | ------- | --- | --- | --- | --- | --- | --- | --- |
91
U
PSS
U
RMAX
+
|       |     |      |                |     |     |                | U   |     |            | E   |
| ----- | --- | ---- | -------------- | --- | --- | -------------- | --- | --- | ---------- | --- |
| U err |     |      |                |     |     | K              | + R |     |            | F   |
|       | +   | 1    | + s T ----C--  |     |     | -----A-------- |     | Σ   | 1          |     |
|       | Σ   | -    | ---- ----- --- |     |     | ------         |     |     | ---- ----- |     |
|       |     | 1+sT |                |     |     | 1+sT           | -   |     | sT         |     |
|       | -   |      | D              |     |     | A              |     |     | E          |     |
U
|     | U F |     |     |     | RMIN |     |     |     |     |     |
| --- | --- | --- | --- | --- | ---- | --- | --- | --- | --- | --- |
U
FE
|     |     |     |     |     |     |     |     | S   | E (E F )+K E |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | ------------ | --- |
sK
------------F-------
|     |     |             | 1+sT F |     |            |        |       |      |       |     |
| --- | --- | ----------- | ------ | --- | ---------- | ------ | ----- | ---- | ----- | --- |
|     |     | Figure 6.3. | Model  | of  | DC exciter | system | (IEEE | Type | DC1). |     |
constants T and T can be used to model internal time constants in the
|             |     | C     | D         |       |     |          |         |     |            |     |
| ----------- | --- | ----- | --------- | ----- | --- | -------- | ------- | --- | ---------- | --- |
| controller. |     | These | are often | small | and | can then | usually | be  | neglected. |     |
The output signal from the voltage controller, U , controls the exciter.
R
The exciter consists of a DC machine that can be excited independently or
shunt excited. For shunt excited machines, the parameter K models the
E
setting of the field regulator. The term S represents the saturation of the
E
exciter and is a function of the exciter’s output voltage, E . If saturation is
F
neglected, that is S E = 0, the effective time constant of the exciter becomes
| T   | /K , and   | its effective |     | amplification |     | is 1/K | .   |     |     |     |
| --- | ---------- | ------------- | --- | ------------- | --- | ------ | --- | --- | --- | --- |
| E   | E          |               |     |               |     |        | E   |     |     |     |
| AC  | Excitation | Systems       |     |               |     |        |     |     |     |     |
ForAC excitation systems, theexciter consists ofasmaller synchronousma-
chine that feeds the exciter winding through a rectifier. The output voltage
of the exciter is in this case influenced by the loading. To represent these
effects, the exciter current is used as an input signal in the model. In Fig-
ure 6.4, an example of a model of AC exciter systems is shown (IEEE type
AC1). The structure of the model is basically the same as for the DC exci-
tation system. Some functions have been added. The rectifier of the exciter
prevents (for most exciters) the exciter current from being negative. The
feedback with the constant K represents the reduction of the flux caused
D
by a rising field current I F . That constant depends on the synchronous and
transient reactances of the exciter. The voltage drop inside the rectifier is
described by the constant K , and its characteristic is described by F ,
|       |      |          |        | C    |          |     |     |     |     | EX  |
| ----- | ---- | -------- | ------ | ---- | -------- | --- | --- | --- | --- | --- |
| which | is a | function | of the | load | current. |     |     |     |     |     |
DC and AC excitation systems are sometimes called rotating exciters,
since they contain rotating machines. That distinguishes them from static
| excitation |     | systems, | which | are described |     | in the | sequel. |     |     |     |
| ---------- | --- | -------- | ----- | ------------- | --- | ------ | ------- | --- | --- | --- |

|     |     |     |     |     |     | 6. Voltage | Control | in  | Power | Systems |
| --- | --- | --- | --- | --- | --- | ---------- | ------- | --- | ----- | ------- |
92
U
PSS
|     |     |              |             |                       | U RMAX |      |              |     |     |     |
| --- | --- | ------------ | ----------- | --------------------- | ------ | ---- | ------------ | --- | --- | --- |
| U   | +   |              |             |                       |        | U R+ |              |     |     | E   |
|     | err | 1 + s        | T           | K                     |        |      |              | U E |     | F   |
|     | Σ   | - ---- ----- | --- ----C-- | ------ -----A-------- |        | Σ    | ---- 1 ----- |     | Π   |     |
|     |     | 1+sT         |             | 1+sT                  |        |      | sT           |     |     |     |
|     | + - |              | D           |                       | A      | -    | E            |     |     |     |
F
EX
0
|     |     |     |     | U RMIN |     |     |     |     | F = | f(I ) |
| --- | --- | --- | --- | ------ | --- | --- | --- | --- | --- | ----- |
|     | U F |     |     |        |     |     |     |     | EX  | H     |
K I
|     |     |     |       |                  |     | +    | K E +S | E   | I = --- | --C------F-- |
| --- | --- | --- | ----- | ---------------- | --- | ---- | ------ | --- | ------- | ------------ |
|     |     |     |       |                  |     |      |        |     | H       | U            |
|     |     |     |       | s K              |     | U FE |        |     |         | E            |
|     |     |     | ----- | --- ----F------- |     | Σ    |        |     |         |              |
1+sT
F
|     |     |     |     |     |     | +   |     |     |     | I F |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
K
D
|        | Figure     | 6.4. | Model   | of  | an AC | exciter system | (IEEE | Type | AC1). |     |
| ------ | ---------- | ---- | ------- | --- | ----- | -------------- | ----- | ---- | ----- | --- |
| Static | Excitation |      | Systems |     |       |                |       |      |       |     |
Instaticexcitation systems,theexciter windingisfedthroughatransformer
and a controlled rectifier. By far most exciter systems installed today are of
thattype, andalargenumberofvariantsexists. Theprimaryvoltage source
can be a voltage transformer that is connected to the generator terminals,
but even a combination of voltage and current transformers can be found.
With the latter arrangement, an exciter current can be obtained even if the
voltage at the generator terminals is low, for example during a ground fault
in or near the power plant. Sometimes, it is possible to supplement these
voltage sources by using the auxiliary power of the power plant as voltage
source. That makes it possible to start the generator in an unenergised net.
An example of a model of a static exciter system is shown in Figure 6.5.
Static excitation systems can often deliver negative field voltage and
even negative field current. However, the maximum negative field current is
| usually | considerably |     | lower | than | the | maximum | positive | field | current. |     |
| ------- | ------------ | --- | ----- | ---- | --- | ------- | -------- | ----- | -------- | --- |
The time constants are often so small that a stabilizing feedback is not
needed. The constant K can then be set to zero. Since the exciter system
F
is normally supplied directly from the generator bus, the maximum exciter
voltage dependsonthegenerator’s outputvoltage (andpossiblyitscurrent).
This is modelled by the dependency of the limitations of the exciter output
on the generator’s output voltage. The constant K represents the relative
C
| voltage | drop | in the | rectifier. |     |     |     |     |     |     |     |
| ------- | ---- | ------ | ---------- | --- | --- | --- | --- | --- | --- | --- |

| 6.3. Primary |     | Voltage | Control |     |     |     |     |     |     |
| ------------ | --- | ------- | ------- | --- | --- | --- | --- | --- | --- |
93
U
PSS
|     |     |     |        |     |     |     |     | U U    | -K I |
| --- | --- | --- | ------ | --- | --- | --- | --- | ------ | ---- |
|     |     |     | U IMAX |     |     |     |     | T RMAX | C FE |
+
| U   |     |     |     |                  |         |        |                  |     | E   |
| --- | --- | --- | --- | ---------------- | ------- | ------ | ---------------- | --- | --- |
| err | +   |     |     | 1 + s            | T       |        | K -----A-------- |     | F   |
|     |     | Σ   |     | - ---- ----- --- | ----C-- | ------ |                  |     |     |
|     |     |     |     | 1+sT             |         | 1+sT   |                  |     |     |
|     | -   |     |     |                  | D       |        | A                |     |     |
U
|     | F   |        |     |     |     |     |     | U U -K | I    |
| --- | --- | ------ | --- | --- | --- | --- | --- | ------ | ---- |
|     |     | U IMIN |     |     |     |     |     | T RMIN | C FE |
sK
------------F-------
1+sT
F
|       |          | Figure | 6.5. | Model   | of a static | exciter | system. |     |     |
| ----- | -------- | ------ | ---- | ------- | ----------- | ------- | ------- | --- | --- |
| 6.3.2 | Reactive | Shunt  |      | Devices |             |         |         |     |     |
In many systems, the reactive control capabilities of the synchronous ma-
chines are not sufficient to keep the voltage magnitudes within prescribed
limits at all loading conditions. The varied loading condition of the system
during low and peak load situations implies that the reactive power needed
to keep the desired voltage magnitudes vary significantly. It is impossible
and also unwise to use the reactive power capabilities of synchronous ma-
chines to compensate for this, since many synchronous machines will be
driven to their capability limits, and the fast and continuous reactive power
control offered by the synchronous machine will not be available. Therefore,
in most systems, breaker-switched shunt capacitor banks and shunt reac-
tors are used for a coarse control of reactive power, so that the synchronous
| generators | can | be used | for | the fast | and continuous |     | control. |     |     |
| ---------- | --- | ------- | --- | -------- | -------------- | --- | -------- | --- | --- |
Generally shunt capacitors are switched on during high-load conditions,
whenthereactive consumptionfromloadsandlinereactances isthehighest.
Since these load variations are rather slow and predictable, no fast control
is needed and the capacitor banks can be breaker switched. In systems with
long high-voltage lines, the reactive power generation of these lines can be
very high during light load conditions. To keep the voltages at acceptable
levels, shunt reactors might be needed. The sizes of the reactive shunt el-
ements determine how accurate the control can be. Capacitor banks, in
particular, can often be switched in smaller units, while shunt reactors are
most often installed in one single unit, because of high costs. A factor limit-
ingtheelement size is thetransient voltage change resultingfromswitching.
Thefundamentalfrequencyvoltagechangeinpucausedbyswitchingashunt
element can be estimated as ∆V = Qshunt/Ssc, where Qshunt is the size of
| the shunt | element | and | Ssc | is the | short-circuit | power | at  | the node. |     |
| --------- | ------- | --- | --- | ------ | ------------- | ----- | --- | --------- | --- |
Reactiveshuntelementsarealsousedforreactivepowerandvoltage con-
trol at HVDC terminal stations. Since typically a line commutated HVDC
converter station consumes about 50% as much reactive power as active

|     |     |     |     | 6. Voltage | Control | in Power | Systems |
| --- | --- | --- | --- | ---------- | ------- | -------- | ------- |
94
power transmitted, reactive compensation is needed. Part of the reactive
compensation is usually provided by harmonic filters needed to limit the
harmonic current injection into the ac networks. These filters are almost
| purely | capacitive  | at fundamental | frequency. |         |     |     |     |
| ------ | ----------- | -------------- | ---------- | ------- | --- | --- | --- |
| 6.3.3  | Transformer | Tap            | Changer    | Control |     |     |     |
An important method for controlling the voltage in power systems is by
changing the turnsratio of transformers. Certain transformersare equipped
with a number of taps on one of the windings. Voltage control can be ob-
tained by switching between these taps, as illustrated in Figure 6.6. Switch-
ingduringoperationbymeansoftapchangersisveryeffective andusefulfor
voltage control. Normally, the taps are placed on the high-voltage winding
| (the upper | side), | since then | lower currents | needs | to be switched. |     |     |
| ---------- | ------ | ---------- | -------------- | ----- | --------------- | --- | --- |
|            |        |            | U 1 Z k        | τU 2  | U 2             |     |     |
|            |        |            |                | N 1 N | 2               |     |     |
Transformerwithvariableturnsratio(tapchanger).
| Figure | 6.6. |             |      |            |                  |           |     |
| ------ | ---- | ----------- | ---- | ---------- | ---------------- | --------- | --- |
|        |      | Transformer | with | a variable | turns ratio (tap | changer). |     |
If N1 is the number of turns on the high-voltage side and N2 is the
number of turns on the low-voltage side, the turns ratio of transformer is
defined as
N1
|     |     |     | τ = | .   |     |     | (6.1) |
| --- | --- | --- | --- | --- | --- | --- | ----- |
N2
Then, the relation between the voltage phasors on the high-voltage side U1
| and on | the low-voltage | side | U2, at | no load, is |     |     |     |
| ------ | --------------- | ---- | ------ | ----------- | --- | --- | --- |
U1
|     |     |     | U2  | = . |     |     | (6.2) |
| --- | --- | --- | --- | --- | --- | --- | ----- |
τ
Ifthevoltagedecreasesonthehigh-voltageside,thevoltageonthelowerside
can be kept constant by decreasing, that is, by switching out a number of
windingsonthehigh-voltage side. Whenthetransformerisloaded, equation
(6.2) is of course incorrect, since the load current yields a voltage drop over
theleakage reactance of thetransformerZ k , butthesameprinciplecan still
| be applied | for voltage | control. |     |     |     |     |     |
| ---------- | ----------- | -------- | --- | --- | --- | --- | --- |
Transformerswithautomatic tap changer control are often usedfor volt-
age control in distribution networks. The voltage at the consumer side can
thereforebekeptfairly constanteven thoughvoltage variations occuronthe
high-voltage network. Timeconstantsintheseregulatorsaretypically inthe

| 6.3. Primary | Voltage Control |     |     |     |
| ------------ | --------------- | --- | --- | --- |
95
order of tenths of seconds. In some transformers, the turns ratio cannot be
changed during operation, but just manually when the transformer is un-
loaded. In this case, voltage variations in the network cannot be controlled,
| with voltage | levels changing | in large steps. |     |     |
| ------------ | --------------- | --------------- | --- | --- |
| 6.3.4 FACTS  | Controllers     |                 |     |     |
As previously mentioned, power electronics-based equipment, usually re-
ferred to as FACTS controllers or devices, can be used for fast voltage and
reactivepowercontrol. Thefirstdevicesintroducedwerebasedonthyristors
asactiveelements,butmorerecently, devicesusingvoltagesourceconverters
have been introduced; with the latter, a faster and more powerful control
can be achieved. FACTS devices used for voltage control are connected
in shunt. Two such devices are discussed here: the Static var compensator
| (SVC), andthe | STATicsynchronous | COMpensator(STATCOM). |     | TheSVC |
| ------------- | ----------------- | --------------------- | --- | ------ |
isbasedonthyristors,whiletheSTATCOMisbasedonavoltagesourcecon-
verter. There are also series-connected FACTS devices that in principle can
be used for voltage control, but the main reason for installing these devices
istocontrolactive power,whichindirectly influencesvoltages. Amongthese
devices, the unified power flow controller (UPFC) is equipped with a shunt
| part for voltage | control, | which basically operates | as a STATCOM. |     |
| ---------------- | -------- | ------------------------ | ------------- | --- |
V
i
s
Thyristorcontrolledreactor.
|     | Figure | 6.7.                 |          |     |
| --- | ------ | -------------------- | -------- | --- |
|     |        | Thyristor controlled | reactor. |     |

96 6. Voltage Control in Power Systems
Static Var Compensator
TheSVCmay becomposedoftwo differentshuntelements, thatis, athyris-
tor controlled reactor (TCR) and thyristor switched capacitor (TSC)banks.
If fast switching of the capacitor banks is not needed, one can also use
breaker-switched capacitors. The TCR is depicted in Figure 6.7 by delaying
the firing of the thyristors, a continuous control of the current through the
reactor can be obtained, with the reactive power consumption varying be-
2
tween 0 and V /X, where X is the reactance of the reactor. By combining
the TCR with a suitable number of capacitor banks, a continuous control
of the reactive power can be achieved by a combination of capacitor bank
switching and control of the reactor current. Usually, the TCR and TSC
are connected to the high-voltage grid through a transformer, as shown in
Figure 6.8. The control system of the SVC controls the reactive output so
that the voltage magnitude of the controlled node is kept constant. Usually,
a certain slope is introduced in the control, as shown in Figure 6.9, which
shows the reactive current as a function of the voltage. In the (almost)
horizontal part of the curve, around the voltage set point, the SVC control
is active. When the SVC has reached its maximum or minimum reactive
output, the voltage cannot be controlled, and the device will behave as a
pure reactor or pure capacitor; thus, in extreme voltage situations, the SVC
behaves as a reactor or capacitor bank. The control of the reactor current
is based on thyristors, which limits the bandwidth of the voltage control. If
a fast control is needed to compensate for flicker and voltage dips, one has
to use technologies based on voltage source converters.
V
i
s
Figure 6.8. Static var compensator.

6.3. Primary Voltage Control 97
(cid:3)
Figure 6.9. Static var compensator control.
STATCOM
The STATCOM is a device which is based on a voltage source converter.
The device is connected in shunt and consists of a capacitor charged with a
dc voltage, which provides the input voltage for a voltage source converter,
as illustrated in Figure 6.10. The converter feeds a reactive current into the
network, andbycontrollingthisreactive current,voltage controlisachieved.
Since a voltage source converter needs semiconductor elements with current
interrupting capabilities, thyristors cannot be used; instead, elements such
as GTOs or IGBTs have to be used.
In comparison with the SVC, the STATCOM offers two advantages.
First, the STATCOM’s output reactive current is not limited at low- or
high-voltage conditions; rather, the output current is only limited by the
converter ratings and is not dependent on the system voltage. This means
that the reactive support during extreme voltage situations is much bet-
ter with respect to the SVC, as shown in Figure 6.11. Second, the control
response is much faster, since it is limited by the switching frequency of
the voltage source converter (usually around 1 kHz). The STATCOM can
hence be used to reduce flicker and other fast voltage variations effectively.
Thedc capacitor of the voltage source converter constitutes an active power
storage; hence, an active current can also be injected into the network. The
STATCOMcanthusalsobeusedforactivepowercontrol(example,todamp
power oscillations). However, the energy stored in the dc capacitor is fairly
small; therefore, to truly control the active power output, a battery must be
installed on the dc side.

|     |     | 6.  | Voltage Control | in Power Systems |
| --- | --- | --- | --------------- | ---------------- |
98
V
i
s
Voltage
source
converter
|     | Figure | 6.10. STATCOM. |     |     |
| --- | ------ | -------------- | --- | --- |
V
|     |     | Capacitive Inductive | i   |     |
| --- | --- | -------------------- | --- | --- |
s
| Figure 6.11. | Voltage control | and reactive | capability | of a STATCOM. |
| ------------ | --------------- | ------------ | ---------- | ------------- |

| 6.4. Secondary | Voltage | Control |     |     |     |
| -------------- | ------- | ------- | --- | --- | --- |
99
| 6.4 Secondary |     | Voltage | Control |     |     |
| ------------- | --- | ------- | ------- | --- | --- |
As previously discussed, balancing the reactive power via AVRs and other
devices can be considered a local control action. Hence in case of a distur-
bance, the devices electrically nearby will try to compensate the reactive
power needs. This may result in unacceptable voltage values and an uneven
reactive power distribution over the generators. This creates the need of a
coordinated adjustment of the setpoints of the reactive power suppliers.
Secondary Voltage Regulation (SVR) has been developed to address the
abovementionedsituation. SVRisahierarchical,centralizedvoltagecontrol
schemethatsupervisesthegeneratorAVRsandotherreactivepowersources
ina given network zone soas to enhancevoltage stability of thegrid. Figure
6.12 illustrates the basic setup. In each zone, a ’pilot’ node is selected and
controlled typically by the participating generators so as to maintain the
voltage of the pilot node at a specific value, by delivering the reactive power
| proportionally | to their | own | capabilities. |     |     |
| -------------- | -------- | --- | ------------- | --- | --- |
TVR
SVR SVR
|     |     | PI      |     |     | PI      |
| --- | --- | ------- | --- | --- | ------- |
|     |     | QR QR   | QR  |     | QR QR   |
|     |     | AVR AVR | AVR |     | AVR AVR |
Power network
|     | Figure | 6.12. | Structure | of the | voltage regulation. |
| --- | ------ | ----- | --------- | ------ | ------------------- |
Therefore the AVR is enhanced with two additional control levels. The
higher level is responsible for the voltage control of the ’pilot’ node. The
voltage error serves as input to a proportional-integral controller (PI) and
the generated signal is then used by each generator at a lower control level.
Thelatter correspondsto alocal reactive power regulator (QR)that adjusts
the input of the AVR with respect to the generator capability. A similar
hierarchy applies also in the time constants of each control level in order to

|     |     | 6.  | Voltage Control | in Power Systems |
| --- | --- | --- | --------------- | ---------------- |
100
avoid any interaction among them. The AVR time constant is in the order
of 0.5 sec, the QR time constant is in the order of 5 sec, whereas the time
| constant | of the PI controller | is in the order | of 50 sec. |     |
| -------- | -------------------- | --------------- | ---------- | --- |
The scheme can be further enhanced with the use of Tertiary Voltage
Regulation(TVR)which,basedonanoverallsystemeconomicoptimization,
will determine the setpoints of the above mentioned PI controller in a time
| scale of | 15 minutes. |     |     |     |
| -------- | ----------- | --- | --- | --- |
The described secondary closed-loop control scheme is already imple-
mented in some European power grids, particularly in France and in Italy
(since the early 1980’s). Other countries still follow an open-loop strat-
egy, in which the operator adjusts the setpoints manually with an expected
| performance | degradation. |     |     |     |
| ----------- | ------------ | --- | --- | --- |

7
Stability of Power Systems
In this chapter, factors influencing the stability of electric power systems
are discussed. First, a short introduction to damping in a power system is
given. Different sources of positive and negative damping are discussed, and
methods to improve the damping are given. Furthermore, the effect of the
loads on system stability is regarded in the second part of this chapter.
7.1 Damping in Power Systems
7.1.1 General
What damping in the context of electro–mechanical oscillations in a power
system means is quite self–evident. Normally, two different kinds of electri-
cal torques appear at a generator rotor that is oscillating: a synchronizing
torque ∆T and a damping torque ∆T . The synchronizing torque ∆T is
s d s
in phase with the deviation in rotor angle ∆θ, whereas the damping torque
∆T is in phase with the deviation in rotor speed ∆ω. The synchronizing
d
torque, also called the synchronizing power, strives, if it is positive, to bring
the rotor back to the stable equilibrium in which the mechanical power is
equal to the electrical power. When the generator has reached an operating
point where the synchronizing power no longer can return the system to
the stable equilibrium, the generator will fall out of phase. The variation
of the synchronizing torque with the rotor angle determines, together with
the machine’s moment of inertia, the frequency of rotor oscillations. The
partitioning into synchronizing and damping torque is shown in Figure 7.1.
Damping is neglected in the classical model. Therefore, the system will,
after a disturbance, either fall out of phase (instability) or oscillate with un-
changedamplitude. Thisisnotrealistic,sincerealsystemscontaindamping.
The damping torque depends on the time derivative of the rotor angle in
such a way that the oscillation is damped. Normally, the damping torque is
rather small and thus influences the oscillation frequency only marginally.
It mainly influences the amplitude. In a synchronous machine, the main
contributors to damping are the damper windings and the field winding.
If the modes of oscillation in a system are determined by computing
the eigenvalues of the linearised system’s Jacobian matrix, changes in the
synchronizing and damping torques will become apparent as follows: An
increase of the synchronizing torque moves the eigenvalue parallel to the
101

|     |     |     |     |     |     | 7. Stability | of Power | Systems |
| --- | --- | --- | --- | --- | --- | ------------ | -------- | ------- |
102
∆ω
∆T
|     |     | ∆T  |     |     |     | e   |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
d
|     |     |     |     |     | ∆T  |     | ∆θ  |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
s
| Figure  | 7.1.        | Partitioning |     | of  | electrical torque | in  | synchronizing | and |
| ------- | ----------- | ------------ | --- | --- | ----------------- | --- | ------------- | --- |
| damping | components. |              |     |     |                   |     |               |     |
imaginary axis towards larger values. This corresponds to an increase in the
spring constant in a mechanical analogy. If the damping torque is increased
instead, the eigenvalue will move parallel to the real axis to the left. In
the classical model, all eigenvalues will be situated on the imaginary axis.
Necessary for stability is that no eigenvalues are situated in the right half
plane. Thiscorrespondstopositive∆T aswellaspositive∆T inFigure7.1.
|       |        |            |     |     | s   |     | d   |     |
| ----- | ------ | ---------- | --- | --- | --- | --- | --- | --- |
| 7.1.2 | Causes | of Damping |     |     |     |     |     |     |
As mentioned earlier, the internal damping of a generator comes from the
windings in the rotor circuit. That damping is determined by phases and
amplitudes of the oscillating torques caused by induced currents in exciter
winding and damping windings. Further, some loads contribute with posi-
tive damping. Thesecontributions originate from thefrequencydependency
| of the loads, | but | also | their | voltage | dependency | contributes. |     |     |
| ------------- | --- | ---- | ----- | ------- | ---------- | ------------ | --- | --- |
Generally, theinnerdampingofthegenerators decreaseswithdecreasing
frequency of the oscillations. The currents in the damping windings decay,
| and hence, | for | very slow | oscillations, |     | their contribution |     | is small. |     |
| ---------- | --- | --------- | ------------- | --- | ------------------ | --- | --------- | --- |
Low or negative damping in a power system can lead to spontaneous ap-
pearance of large power oscillations. This can, in the worst case, necessitate
tripping of lines and it must be avoided. That type of instability is called
small signal instability or instability caused by low damping. (Earlier, that
| type of | instability | was | called | dynamic | instability.) |     |     |     |
| ------- | ----------- | --- | ------ | ------- | ------------- | --- | --- | --- |
A common reason for low damping is the use of voltage controllers with
high gain. That was experienced in generators feeding a strong net through
a line. Such a configuration can also be analyzed comparably easily. It can
be shown that an eigenvalue with positive real part can occur when large
amountsofpoweraretransmittedandvoltagecontrollerswithhighgainsare
used. Before the reason behind this phenomenon was known, the problem
was solved by operating the generator with manual voltage control, or by

| 7.1. Damping | in  | Power Systems |     |     |     |
| ------------ | --- | ------------- | --- | --- | --- |
103
∆U
ref
| ∆ω  |     |     | sT                      |     | 1+sT                  |
| --- | --- | --- | ----------------------- | --- | --------------------- |
|     | K   |     | ------------ W -------- |     | ----------------- 1 - |
STAB
|        |             |             | 1+sT          |             | 1+sT      |
| ------ | ----------- | ----------- | ------------- | ----------- | --------- |
|        |             |             | W             |             | 2         |
|        |             | Figure 7.2. | Block Diagram | of a simple | PSS.      |
| making | the voltage | controller  | slower or     | decreasing  | its gain. |
To explain that mechanism in detail is beyond the scope of this com-
pendium, but in summary, it can be said that the rotor angle influences
the generator voltage, which through the voltage controller influences the
transient emf, which influences the electrical torque. Now it turns out that,
when the load on the machine is high, the phase angle can be such that a
contribution with negative damping is obtained. If the amplification in the
voltage controller is high, that negative contribution can be significant.
| 7.1.3 | Methods | to Increase | Damping |     |     |
| ----- | ------- | ----------- | ------- | --- | --- |
Several methods for increasing thedampingin a power system are available.
The simplest and usually cheapest way is the installation of power system
stabilizers, PSS, in the generators. The operating principle for these is very
simple. To increase the damping in the system, a signal is added to the
reference voltage of the generator’s voltage controller. The phase of this
signal should of course be such that it results in a positive contribution to
thedamping. Thus,thesamephysicalmechanisminthesystemofgenerator
and voltage controller that above resulted in negative damping is used to
| obtain positive |     | damping. |     |     |     |
| --------------- | --- | -------- | --- | --- | --- |
Such a power system stabilizer usually utilizes the rotor deviation from
the synchronous frequency ∆ω as input signal. Sometimes, other signals
that contain the same information can be used, like P or T . A diagram
e e
illustrating the principle mode of operation of a PSS is given in Figure 7.2.
Theinputsignal,inthiscase∆ω,firstpassesahigh–passfiltertoensurethat
permanentfrequency deviations donot contribute. Thenext filter shifts the
phase appropriately for the critical oscillation frequency so that a positive
contribution to damping is obtained. The constant K stab determines the
size of that contribution. That constant should of course not be chosen
larger than necessary to obtain the needed damping, since this could lead
| to undesired | side | effects. |     |     |     |
| ------------ | ---- | -------- | --- | --- | --- |
Other possibilities for increasing the damping in a system are different
types of controllable equipment that may be installed in the system, such as
HVDC (High Voltage Direct Current) or SVC (Static Voltage Condensers).
These components can often give large contributions to damping, but they
are usually too expensive to install them only to increase the damping, and
theexistingequipmentisnotalwayslocatedoptimallyfordampingpurposes.

104 7. Stability of Power Systems
7.2 Load Modelling
Since, neglecting losses, an equal amount of power is consumed in the loads
inthesystemasisgeneratedinthegenerators, theload characteristicsare on
principle just as important for the system properties as the generators. That
is, however, not reflected in the level of detail and the accuracy usually used
in load models for analyzing system stability. This chapter discusses briefly
how load characteristics influence the system stability and which problems
arise in the derivation of appropriate load models. The most common load
models are presented.
7.2.1 The Importance of the Loads for System Stability
The characteristics of the loads influence the system stability and dynamics
in many different ways. The voltage characteristics of the loads have a
direct influence on the accelerating power for generators nearby and are
thus very important for the behaviour during the first oscillation after a
fault. It has been shown in section 2.1.2 that the frequency dependency of
theloadsinfluencesdirectlyhowlargethefrequencydeviation afterdifferent
system disturbances will become. The frequency dependency of the loads
also influences the system damping. The same is true for their voltage
dependency since it influences the voltage control.
This compendium concentrates on what is usually called angular stabil-
ity, or synchronous stability, that is, the ability of the generators to stay
synchronized after disturbances. Another important property of a power
system is the ability to keep the voltages in the system within acceptable
limits during disturbances. This is a measure for the voltage stability of
the system. Voltage stability is highly dependent on the balance of reactive
power in the system, but also the active power has some influence here. It
is obvious that the voltage dependency of the loads is of high importance
for the system’s voltage stability.
It is for several reasons difficult to derive good load models. (Of course,
deriving models for single load objects is formally not very difficult. Loads
here are, however, lumped loads as they are perceived from a bus in the
high voltage grid.) First, it is difficult to estimate the composition of the
loads, since it varies during the day as well as during the year. Further,
this composition varies from bus to bus. Thus, sometimes different load
models have to be used at different buses, depending on the composition of
the loads, for example industrial loads, domestic loads, and rural loads.
7.2.2 Load Models
For studies of angular stability, loads are usually modelled with static mod-
els. Sometimes, large induction motors have to be represented individually

| 7.2. | Load | Modelling |     |     |     |     |     |     |     |     |
| ---- | ---- | --------- | --- | --- | --- | --- | --- | --- | --- | --- |
105
by special models to obtain the correct dynamic behaviour. Dynamic load
models for lumped loads have begun to be used during the last few years,
especially for studying voltage stability, but those are expected to be used
| in     | the future | more   | widely |     | and | even for other | types | of  | studies. |     |
| ------ | ---------- | ------ | ------ | --- | --- | -------------- | ----- | --- | -------- | --- |
| Static | Load       | Models |        |     |     |                |       |     |          |     |
For traditional stability studies, where the investigated time frame is at
most around 10 s after the disturbance, the most commonly used model
types are static models. They are called static since they describe the load
using only algebraic equations. The modelled load dynamics are in these
cases sofastthatthey canbeconsideredinstantaneous comparedwithother
phenomena, like rotor oscillations, that are modelled. The most common
| model | for | voltage | dependency |     | is  |     |     |     |     |     |
| ----- | --- | ------- | ---------- | --- | --- | --- | --- | --- | --- | --- |
α
U
|     |     |     |     |     | P   | = P0 | ,   |     |     |     |
| --- | --- | --- | --- | --- | --- | ---- | --- | --- | --- | --- |
U0
|     |     |     |     |     |     | (cid:18) (cid:19) |     |     |     |     |
| --- | --- | --- | --- | --- | --- | ----------------- | --- | --- | --- | --- |
(7.1)
β
U
|     |     |     |     |     | Q   | = Q0 | .   |     |     |     |
| --- | --- | --- | --- | --- | --- | ---- | --- | --- | --- | --- |
U0
|     |     |     |     |     |     | (cid:18) | (cid:19) |     |     |     |
| --- | --- | --- | --- | --- | --- | -------- | -------- | --- | --- | --- |
However, the load can also be modelled as an arbitrary polynomial in
(U/U0),
|     |     |     |     |     |        |     | U αi |     |     |       |
| --- | --- | --- | --- | --- | ------ | --- | ---- | --- | --- | ----- |
|     |     |     |     |     | P = P0 | k   |      | .   |     | (7.2) |
i U0
|     |     |     |     |     |     | i (cid:18) | (cid:19) |     |     |     |
| --- | --- | --- | --- | --- | --- | ---------- | -------- | --- | --- | --- |
X
In Equations (7.1) and (7.2), U0 is the nominal voltage at nominal load,
P0 and Q0. In Equations (7.1), the voltage exponents α and β are often
different.
If α = 0, the load is called constant power load; if α = 1, it is called
constant current load; and if α = 2, it is a constant impedance load. It is
very common to model the (active) load for stability studies as consisting of
these three parts. Usually, a somewhat larger voltage exponent is used for
| the      | reactive | load.    |      |      |         |           |     |           |            |     |
| -------- | -------- | -------- | ---- | ---- | ------- | --------- | --- | --------- | ---------- | --- |
|          | Some     | examples | for  | the  | voltage | exponents | of  | different | loads are: |     |
| Electric |          | heating: | α =  | 2, Q | = 0.    |           |     |           |            |     |
| Light    | bulbs:   | α        | 1,6, | Q =  | 0.      |           |     |           |            |     |
≈
| Fluorescent |     | tubes: | α   | 0,9, | β   | 2.  |     |     |     |     |
| ----------- | --- | ------ | --- | ---- | --- | --- | --- | --- | --- | --- |
|             |     |        |     | ≈    | ≈   |     |     |     |     |     |
Tobeabletoincludeactiveandreactivelossesintheunderlyingdistribution
| grid, | the | above | models | have | to  | be modified. |     |     |     |     |
| ----- | --- | ----- | ------ | ---- | --- | ------------ | --- | --- | --- | --- |
A load model often used is the so called ZIP–Model. The ZIP-Model is
a special case of the model in Equation (7.2), which contains three terms
with:
|     | α1  | = 2, i.e. | constant |     | impedance | (Z) | load |     |     |     |
| --- | --- | --------- | -------- | --- | --------- | --- | ---- | --- | --- | --- |
•

|     |     |     |     |     |     | 7. Stability | of  | Power Systems |
| --- | --- | --- | --- | --- | --- | ------------ | --- | ------------- |
106
|     |     |     | X′  | = ωL′ | r   | i   |     |     |
| --- | --- | --- | --- | ----- | --- | --- | --- | --- |
s
+
+
e′
e
|     |     | Figure | 7.3. Representation |     | of  | induction | motor. |     |
| --- | --- | ------ | ------------------- | --- | --- | --------- | ------ | --- |
|     |     |        | L                   |     | L   | r         |        |     |
|     |     |        | r                   |     | s   |           | s      |     |
r
|     |     | r    |     | L   |     |     |     |     |
| --- | --- | ---- | --- | --- | --- | --- | --- | --- |
|     |     | ---- |     | m   |     |     |     |     |
s
|     |      | Figure           | 7.4. Equivalent | circuit | for  | induction | motor. |     |
| --- | ---- | ---------------- | --------------- | ------- | ---- | --------- | ------ | --- |
|     | α2 = | 1, i.e. constant | current         | (I)     | load |           |        |     |
•
|     | α3 = | 0, constant | power (P) | load |     |     |     |     |
| --- | ---- | ----------- | --------- | ---- | --- | --- | --- | --- |
•
Motor Loads
Around half of all electric power used by the industry is used for operation
of motors. Sometimes, the load in certain nodes is dominated by electric
| motors. | It  | can then | be justified | to model | those | explicitly. |     |     |
| ------- | --- | -------- | ------------ | -------- | ----- | ----------- | --- | --- |
For small changes in voltage, a motor load behaves approximately like a
constant power load. For larger voltage changes, it can be necessary to use
a more accurate representation. Synchronous machines are then modelled
according to the models derived in Chapter 5, with the mechanical part P m
depending on the characteristic of the mechanical load. A large part of the
motor load consists of induction motors that can be modelled as follows:
An induction motor is basically a synchronous machine with short–circuited
exciter coil. If the exciter coil rotates with an angular speed different from
the rotating fluxes generated by the three phase coils, a current that gener-
ates a flux is induced in the exciter coil. Between the rotating synchronous
flux generated in the phase windings and the flux from the exciter wind-
ing, energy is exchanged. This is the basis for the function of the induction
motor.
The induction motor can, according to Figure 7.3, be described by a
voltage source behind an impedance. The value of L ′ can be obtained from
| the | equivalent | circuit | of the induction |     | motor | shown | in Figure | 7.4. |
| --- | ---------- | ------- | ---------------- | --- | ----- | ----- | --------- | ---- |

| 7.2. Load | Modelling |     |     |     |     |     |     |     |     |
| --------- | --------- | --- | --- | --- | --- | --- | --- | --- | --- |
107
| In Figure | 7.4         |            |             |            |     |             |     |     |     |
| --------- | ----------- | ---------- | ----------- | ---------- | --- | ----------- | --- | --- | --- |
| r and     | L are       | the stator |             | resistance | and | inductance, |     |     |     |
| s         | s           |            |             |            |     |             |     |     |     |
| L is the  | magnetizing |            | inductance, |            |     |             |     |     |     |
m
| r and | L are  | rotor      | resistance |     | and inductance. |     |     |     |       |
| ----- | ------ | ---------- | ---------- | --- | --------------- | --- | --- | --- | ----- |
| r     | r      |            |            |     |                 |     |     |     |       |
| The   | slip s | is defined | by         |     |                 |     |     |     |       |
|       |        |            |            |     |                 | ω0  | ω   |     |       |
|       |        |            |            |     | s =             | −   |     |     | (7.3) |
ω0
′
| and thus | L is | given | by  |     |     |     |     |     |     |
| -------- | ---- | ----- | --- | --- | --- | --- | --- | --- | --- |
L L
|     |     |     |     | ′   |       | m   | r   |     |       |
| --- | --- | --- | --- | --- | ----- | --- | --- | --- | ----- |
|     |     |     |     | L = | L s + |     | .   |     | (7.4) |
L +L
|              |     |               |     |     |     | m   | r   |     |     |
| ------------ | --- | ------------- | --- | --- | --- | --- | --- | --- | --- |
| The dynamics |     | are described |     | by  |     |     |     |     |     |
′
|     |     | de  | 1 ′       |     |     |       | ′          | ′     |       |
| --- | --- | --- | --------- | --- | --- | ----- | ---------- | ----- | ----- |
|     |     | +   | (e +jω0(L |     | +L  |       | L)i)+jω0se | = 0 , | (7.5) |
|     |     |     | τ′        |     | s   | m     |            |       |       |
|     |     | dt  | 0         |     |     | −     |            |       |       |
|     |     |     |           |     |     | e e ′ |            |       |       |
|     |     |     |           | i=  |     | −     | ,          |       | (7.6) |
r +jω0L′
s
|     |     |     |     | dω  | 1   |        |       |     |       |
| --- | --- | --- | --- | --- | --- | ------ | ----- | --- | ----- |
|     |     |     |     |     | =   | (T     | T ) , |     | (7.7) |
|     |     |     |     |     |     | e      | l     |     |       |
|     |     |     |     | dt  | 2H  | m      | −     |     |       |
|     |     |     |     | T   | =   | (e ′ i | ∗ ) . |     | (7.8) |
e
|     |     |     |     |     | ℜ   | ·   |     |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
Here,
| ω is the  | machine’s |         | angular | speed, |     |     |     |     |     |
| --------- | --------- | ------- | ------- | ------ | --- | --- | --- | --- | --- |
| ω0 is the | system’s  | angular |         | speed, |     |     |     |     |     |
| T is the  | load      | torque, |         |        |     |     |     |     |     |
l
′
| τ = (L     | +L      | )/r | are no | load | operation |     | constants. |     |     |
| ---------- | ------- | --- | ------ | ---- | --------- | --- | ---------- | --- | --- |
| 0          | r       | m r |        |      |           |     |            |     |     |
| Equivalent | Dynamic |     | Loads  |      |           |     |            |     |     |
The load models presented above are, as mentioned, valid for studying phe-
nomena that do not last longer than about ten seconds after a disturbance.
If phenomena taking place in a longer time frame should be studied, slow
dynamics in the system have to be accounted for. These dynamics origi-
nate mainly from two different sources: The tap changers installed at lower
voltage levels that try to restore the voltage to the desired value and the
| controllers | installed |     | at the | loads. |     |     |     |     |     |
| ----------- | --------- | --- | ------ | ------ | --- | --- | --- | --- | --- |
The control of tap changers can be done in several different ways, but
common to most systems are that tap changers are stepped, typically in
intervals of some tens of seconds, until the voltage is restored . Since this
control exists at different voltage levels (cascade coupled controllers), un-
desirable overshoots in the control can occur if the control loops are not
coordinated. Generally, the control has to be slower the lower the voltage
level is.

|     |     |     |     |     |     | 7. Stability | of Power | Systems |
| --- | --- | --- | --- | --- | --- | ------------ | -------- | ------- |
108
In Sweden, a large part of the load, at least in winter, consists in many
areas of heating loads. The changes in this type of load are determined by
thermostats. Hence, it takes some time until, for example, a voltage drop
becomes apparent. That time is determined by the thermal time constants
for what is heated, such as houses, and by the design of the thermostats.
Summarizing, it can be said that the dynamics determined by tap–chan-
ger control and load dynamics are highly complicated. Measurements are
needed to get reliable results. Measurements of load characteristics have
during the last few years become very important, and much work is be-
ing done in many utilities to investigate load characteristics under different
loading conditions.
A typical example of a load behaviour after a voltage drop is shown in
Figure7.5. Itis clearly visiblehow theload dropsmomentarily, as described
by the load models from Section 7.2.2, to recover later to a considerably
| higher | level. A rather | general |     | description | is  | given by |     |     |
| ------ | --------------- | ------- | --- | ----------- | --- | -------- | --- | --- |
dP
|     |     | T   | r   | +P =P   | (U)    | P (U) , |     | (7.9)  |
| --- | --- | --- | --- | ------- | ------ | ------- | --- | ------ |
|     |     |     | p   | r       | s      | t       |     |        |
|     |     |     | dt  |         | −      |         |     |        |
|     |     |     | P   | (t) = P | +P (U) | ,       |     | (7.10) |
|     |     |     | l   | r       | t      |         |     |        |
where
| P r (t) is | a state variable, |       |         |           |      |            |     |     |
| ---------- | ----------------- | ----- | ------- | --------- | ---- | ---------- | --- | --- |
| P (U)      | is a static       | model | for the | long term | load | behaviour, |     |     |
s
| P (U) is | a static | model | for the | transient | load | behaviour, |     |     |
| -------- | -------- | ----- | ------- | --------- | ---- | ---------- | --- | --- |
t
| P (t) is | the value | of the | active | load at | the time | t.  |     |     |
| -------- | --------- | ------ | ------ | ------- | -------- | --- | --- | --- |
l
| Of course, | U =U(t)      | in    | the equations |           | above. |               |            |     |
| ---------- | ------------ | ----- | ------------- | --------- | ------ | ------------- | ---------- | --- |
| For        | the reactive | load, | similar       | behaviour |        | and equations | are valid. |     |

7.2. Load Modelling
109
Load Recovery Factor Definition
1.05
1
∆P
s
0.95
]up[ rewoP evitcA
| ∆P    |     | ∆P - | ∆P  |     |     |
| ----- | --- | ---- | --- | --- | --- |
| 0.9 t |     | t    | s   |     |     |
PRF=
∆P
t
0.85
0.8
0.75
| -5  | 0   | 5   | 10  | 15  | 20  |
| --- | --- | --- | --- | --- | --- |
Time [minutes]
| Figure 7.5. | The Transient   | Behaviour    | of the Load | in Equations (7.9) |     |
| ----------- | --------------- | ------------ | ----------- | ------------------ | --- |
| and (7.10)  | after a Step in | the Voltage. |             |                    |     |

110 7. Stability of Power Systems

References
[1] P. Kundur: Power System Stability and Control, McGraw-Hill Inc.,
| New York, | 1994 | (ISBN | 0-07-035958-X). |     |     |     |     |
| --------- | ---- | ----- | --------------- | --- | --- | --- | --- |
[2] DynamicModels forSteam andHydroTurbinesin Power SystemStud-
| ies, IEEE | Trans. | Power | Appar. | Syst. | 1904-1915, | Nov./Dec. | 1973. |
| --------- | ------ | ----- | ------ | ----- | ---------- | --------- | ----- |
[3] G.Andersson: ModellingandAnalysisofElectric Power Systems,ETH
Zurich, 2009.
[4] W.G. Heffron and P.A. Phillips: Effect of modern aplidyne voltage
regulatoronunder-excitedoperationoflargeturbinegenerators, Trans.
Am.Inst. Electr.Eng.,Part3,71,692–697,1952.Ascitedin: Yao-Nan
| Yu, Electric | Power | System | Dynamics, |     | Academic | Press, | 1983. |
| ------------ | ----- | ------ | --------- | --- | -------- | ------ | ----- |
[5] A.R. Bergen and V. Vittal: Power System Analysis, Second Edition,
| Prentice | Hall, | 2000. |     |     |     |     |     |
| -------- | ----- | ----- | --- | --- | --- | --- | --- |
[6] A. Gomez-Exposito, A. J. Conejo and C. Canizares: Electric Energy
| Systems: | Analysis | and | Operation, |     | CRC Press, | 2009. |     |
| -------- | -------- | --- | ---------- | --- | ---------- | ----- | --- |
111

112 REFERENCES

| Appendix   |         | A       |       |     |          |          |     |     |
| ---------- | ------- | ------- | ----- | --- | -------- | -------- | --- | --- |
| Connection |         | between |       |     |          | per unit | and | SI  |
| Units      | for the |         | Swing |     | Equation |          |     |     |
If nothing else is given after a quantity, that quantity is in SI–units. If a
quantity is expressed in per unit, p.u. is given in brackets after the quan-
tity (p.u.). For simplicity, it is assumed that the nominal electrical and
| mechanical | frequencies | are | equal, | (rad/s). |     |     |     |     |
| ---------- | ----------- | --- | ------ | -------- | --- | --- | --- | --- |
In SI–units,
2
d θ
|     |     |     | J   | =   | ∆T  | ,   |     | (A.1) |
| --- | --- | --- | --- | --- | --- | --- | --- | ----- |
dt2
with
2
| J = moment     | of inertia       | for      | rotor     | turbine  | (kgm | ),               |         |     |
| -------------- | ---------------- | -------- | --------- | -------- | ---- | ---------------- | ------- | --- |
| θ = angle      | (rad),           |          |           |          |      |                  |         |     |
| ω = angular    | velocity         | (rad/s), |           |          |      |                  |         |     |
| ∆T = effective | torque           | on       | the rotor | turbine  |      | (Nm).            |         |     |
| When           | using electrical |          | degrees,  | Equation |      | (A.1) is usually | written | as  |
2
|     |     |     | M   | d θ |      |     |     |       |
| --- | --- | --- | --- | --- | ---- | --- | --- | ----- |
|     |     |     |     |     | = ∆T | ,   |     | (A.2) |
dt2
|     |     |     | ω0  | ·   |     |     |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
with
|            |            |     | 180 |        | ◦   |     |     |     |
| ---------- | ---------- | --- | --- | ------ | --- | --- | --- | --- |
| M = moment | of inertia | =   | Jω0 | (Js/el | ).  |     |     |     |
π
The H-factor, or constant of inertia, for synchronous machine i is defined
by
|     |     |     |     | 1   | 2    |     |     |       |
| --- | --- | --- | --- | --- | ---- | --- | --- | ----- |
|     |     |     |     | 2   | Jω 0 |     |     |       |
|     |     |     | H   | =   |      | ,   |     | (A.3) |
i
S i
with
| H = constant | of inertia | for | synchronous |     | machine | i (s), |     |     |
| ------------ | ---------- | --- | ----------- | --- | ------- | ------ | --- | --- |
i
| S = rated | power of | synchronous |     | machine. |     |     |     |     |
| --------- | -------- | ----------- | --- | -------- | --- | --- | --- | --- |
i
The per unit base for torques at synchronous machine i, T bas,i , is given by
S
i
|     |     |     | T   | =     |     | ,   |     | (A.4) |
| --- | --- | --- | --- | ----- | --- | --- | --- | ----- |
|     |     |     |     | bas,i | ω0  |     |     |       |
leading to
|     |     |     |      |          |     | S i |     |       |
| --- | --- | --- | ---- | -------- | --- | --- | --- | ----- |
|     |     |     | ∆T = | ∆T(p.u.) |     | .   |     | (A.5) |
ω0
| Using (A.3) | and (A.5), | (A.1) | can | be written |     | as  |     |     |
| ----------- | ---------- | ----- | --- | ---------- | --- | --- | --- | --- |
2
|     |     | 2H  | i S i d | θ   | S i     |     |     |       |
| --- | --- | --- | ------- | --- | ------- | --- | --- | ----- |
|     |     |     |         | =   | ∆T(p.u) | ,   |     | (A.6) |
2 dt2
|     |     | ω   | 0 · |     | ω0  |     |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
113

A. Connection between per unit and SI Units for the Swing Equation
114
or
2
|     |     | d   | θ ω0      |     |     |       |
| --- | --- | --- | --------- | --- | --- | ----- |
|     |     |     | = ∆T(p.u) |     | .   | (A.7) |
dt2
2H i
| Equation (A.7) | can  | also be | written as |         |     |       |
| -------------- | ---- | ------- | ---------- | ------- | --- | ----- |
|                |      | d       | (θ˙) ω0    |         |     |       |
|                |      |         | =          | ∆T(p.u) | ,   | (A.8) |
|                |      | dt      | 2H i       |         |     |       |
| which is the   | same | as      |            |         |     |       |
|                |      | d       | ω0         |         |     |       |
|                |      | (ω)     | = ∆T(p.u)  |         | ,   | (A.9) |
|                |      | dt      | 2H i       |         |     |       |
or
|     |     | d   |             | ∆T(p.u) |     |        |
| --- | --- | --- | ----------- | ------- | --- | ------ |
|     |     |     | (ω(p.u.)) = |         | .   | (A.10) |
|     |     | dt  |             | 2H      |     |        |
i
Generally,
|     |     |     | P = Tω | ,   |     | (A.11) |
| --- | --- | --- | ------ | --- | --- | ------ |
m
with the actual mechanical angular speed of the rotor ω that, according
m
to the assumptions, is equal to the electrical angular speed ω. With the
| equations       | above, this | gives    |                |           |     |        |
| --------------- | ----------- | -------- | -------------- | --------- | --- | ------ |
|                 |             | P(p.u)   | = T(p.u)ω(p.u) |           | .   | (A.12) |
| Equation (A.10) | now         | becomes  |                |           |     |        |
|                 |             |          | ∆P(p.u.)       |           | 1   |        |
|                 |             | ω˙(p.u.) | =              |           | .   | (A.13) |
|                 |             |          | 2H             | · ω(p.u.) |     |        |
i
For rotor oscillations, ω(p.u.) 1 and (A.13) can be approximated by
≈
∆P(p.u.)
|     |     | ω˙(p.u.) | =   |     | ,   | (A.14) |
| --- | --- | -------- | --- | --- | --- | ------ |
2H
i
or
ω0
|     |     |     | ω˙ = ∆P(p.u.) |     | .   | (A.15) |
| --- | --- | --- | ------------- | --- | --- | ------ |
2H
i
The most common equations in literature are (A.9), (A.10), (A.14), and
(A.15). Of these, (A.9) and (A.10) are exact if ω is the actual angular
frequency. Equations (A.14) and (A.15) are good approximations as long as
| ω ω0. That | is valid | for “normal” | oscillations |     | in power systems. |     |
| ---------- | -------- | ------------ | ------------ | --- | ----------------- | --- |
≈

Appendix B
Influence of Rotor Oscillations on the
Curve Shape
Iftherelativemovementbetweenthefieldwindingofasynchronousmachine
and its phase windings is a purely rotating motion with constant angular
speed, the resulting induced voltages in the phase windings will be shaped
ideallylikeasinusoid. Fromnowon,itisassumedthatthefieldwindingisin
the rotor, while the phase windings are on the stator, but since the relative
motion determines the voltage in the phase windings, it is even possible
to think of stationary field windings and rotating phase windings. In all
modern larger synchronous machines, the field winding is on the rotor, so
the assumption above does have a practical background. However, almost
all relationships and conclusions are independent of this assumption.
For simplicity, consider a single phase synchronous machine according
to Figure B.1. A three phase machine has two more phase windings shifted
◦
120 relative to the phase winding in the figure. The phase winding and
±
the exciter winding are arranged so that the flux linkage through the phase
winding is sinusoidally shaped as a function of the angle θ in Figure B.1:
m
Φ(t) = Φ0cosθ
m
= Φ0cosω0t , (B.1)
with the angular speed of the rotor ω0 according to the system’s electrical
frequency. That flux induces a voltage in the phase windingthat is given by
dΦ
U(t)= = Φ0ω0sinω0t = Uˆ sinω0t . (B.2)
dt − −
Now, we shall study how the flux linkage through the phase windings will
be influenced when rotor oscillations appear in the system. If the balance
betweenpowerintothegeneratorandpowerfromthegenerator, i.e.between
mechanical torque and electrical power, is disturbed, the rotor will start to
oscillate relative to an undisturbed reference rotor that continues to rotate
with the angular speed ω0. The rotor position can generally be described
by
θ
m
(t) = ω0t+θ(t) , (B.3)
where θ(t) is a solution of the swing equation. It has earlier been mentioned
that stable solutions of the swing equation for a synchronous machine con-
nected to a strong grid consist of oscillations that are nearly sinusoidal with
frequencies on the order of magnitude of some tenths of a Hertz to some
115

|     |     | B.  | Influence | of Rotor | Oscillations |     | on  | the Curve | Shape |
| --- | --- | --- | --------- | -------- | ------------ | --- | --- | --------- | ----- |
116
θ
m
N
S
| Figure | B.1. |           |         |           |       |             |     |          |     |
| ------ | ---- | --------- | ------- | --------- | ----- | ----------- | --- | -------- | --- |
|        |      | Schematic | picture | of single | phase | synchronous |     | machine. |     |
Hertz. To investigate how the linked flux, and thus the voltage and the
current, look during an oscillatory movement, a rotor motion according to
|     |     |     | θ (t) = | ω0t+µsin(ω | t+θ | )   | ,   |     | (B.4) |
| --- | --- | --- | ------- | ---------- | --- | --- | --- | --- | ----- |
|     |     |     | m       |            | r   | r   |     |     |       |
with the angular speed ω corresponding to the oscillation frequency and
r
the amplitude of the oscillatory movement µ, is assumed. The flux linkage
| can now | be written | as       |     |                    |     |     |     |      |       |
| ------- | ---------- | -------- | --- | ------------------ | --- | --- | --- | ---- | ----- |
|         | Φ(t)       | = Φ0cosθ | (t) | = Φ0cos(ω0t+µsin(ω |     |     | t+θ | )) , | (B.5) |
|         |            |          | m   |                    |     |     | r   | r    |       |
which implies that the oscillatory movement contains a phase–angle modu-
lationofthefluxlinkage. Themomentaryangularfrequency,Ω(t),isdefined
| for Ψ(t) | as  |     |     |     |     |     |     |     |     |
| -------- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
d
|     |     | Ω(t)= |     | (ω0t+µsin(ω | r   | t+θ r | ))  |     | (B.6) |
| --- | --- | ----- | --- | ----------- | --- | ----- | --- | --- | ----- |
dt
and varies between ω0+µω and ω0 µω . It can be shown (cf. text books
|     |     |     | r   |     | r   |     |     |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
−
| on modulation |     | theory) | that Equation | (B.5) | can | be  | written | as  |     |
| ------------- | --- | ------- | ------------- | ----- | --- | --- | ------- | --- | --- |
n=∞
|     | Φ(t) | = Φ0 |     | J n (µ)cos((ω0+nω |     | r )t+nθ |     | r ) . | (B.7) |
| --- | ---- | ---- | --- | ----------------- | --- | ------- | --- | ----- | ----- |
n=−∞
X
J n (µ) is a Bessel function of the first kind with the argument µ and degree
| n, as given | by  |     |     |     |     |     |     |     |     |
| ----------- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
1 π
|     |     | J   | (µ)= | cos(µsinx |     | nx)dx | .   |     | (B.8) |
| --- | --- | --- | ---- | --------- | --- | ----- | --- | --- | ----- |
|     |     | n   | π    |           |     | −     |     |     |       |
−π
Z
| An important |     | property | of J (µ) | that will | be used | later | is  |     |     |
| ------------ | --- | -------- | -------- | --------- | ------- | ----- | --- | --- | --- |
n
|     |     |     | J−n | (µ)= ( 1)nJ | (µ) | .   |     |     | (B.9) |
| --- | --- | --- | --- | ----------- | --- | --- | --- | --- | ----- |
n
−

117
1
0.9
0.8
J(µ)
0
0.7
0.6
0.5
J(µ)
1
0.4
0.3
0.2
J(µ)
0.1 2
J(µ)
0 3
0 0.1 0.2 0.3 0.4 0.5 0.6 0.7 0.8 0.9 1
µ
Figure B.2. Bessel functions of the first kind of order 0 to 3.
From Equation (B.7) follows that, in spite of that the momentary angular
frequencyforΦ(t)is between ω0+µω
r
andω0 µω
r
,Φ(t)willhaveinfinitely
−
many side bands with the frequencies ω0 nω
r
beside the fundamental
±
frequency ω0. A relevant question is how large the amplitudes of these
side bands are. Generally, the coefficients J (µ) decay rapidly when the
n
order n becomes larger than the argument µ. In Figure B.2, values for
the first four Bessel functions are shown for the argument µ between 0
and 1. It should be observed that µ is measured in radians, so that 1
◦
corresponds to approximately 57 , which in this context is quite a large
amplitude. Figure B.2 shows that side bands with n = 3 and larger can
be neglected even for amplitudes as large as µ = 1. Φ(t) can thus be
approximated quite accurately by
n=2
Φ(t) Φ0 J
n
(µ)cos((ω0+nω
r
)t+nθ
r
) . (B.10)
≈
n=−2
X
Typical oscillation frequencies are, in most cases considerably, lower than
3 Hz, so that practically the whole energy spectrum for Φ(t) lies in the
frequency area f0 6 Hz, i.e. 50(60) 6 Hz. This justifies the usual
± ±
representation of the grid with the traditional phasor modelwith a constant
frequency corresponding to f0.
If the amplitude is very small, say less than µ 0.2, corresponding to
◦ ≈
an amplitude of approximately 10 , side bands with n = 2 and higher can

|     |     | B.  | Influence | of Rotor | Oscillations |     | on  | the Curve | Shape |
| --- | --- | --- | --------- | -------- | ------------ | --- | --- | --------- | ----- |
118
|     | ω   |     |     |     | ω   |     |     |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
r
r
ω
|        |      | µ      | µ                 |     |              |     |           | r      |       |
| ------ | ---- | ------ | ----------------- | --- | ------------ | --- | --------- | ------ | ----- |
|        |      | ---    | ---               |     |              |     |           |        |       |
|        |      | 2      | 2                 |     |              |     |           | 1      |       |
| Figure | B.3. | Vector | with superimposed |     | oscillation, |     | according | to the | text. |
be neglected, see Figure B.2. Further, it can be shown that, if µ is small,
2
µ
|     |     |     | J0(µ) |     | 1   | ,   |     |     |     |
| --- | --- | --- | ----- | --- | --- | --- | --- | --- | --- |
|     |     |     |       | ≈   | − 4 |     |     |     |     |
(B.11)
µ
|            |     |          | J1(µ)      |     | ,   |     |     |     |     |
| ---------- | --- | -------- | ---------- | --- | --- | --- | --- | --- | --- |
|            |     |          |            | ≈   | 2   |     |     |     |     |
| are valid, | and | Φ(t) can | be written | as  |     |     |     |     |     |
2
|      |       | µ        | µ   |           |      |     | µ       |     |           |
| ---- | ----- | -------- | --- | --------- | ---- | --- | ------- | --- | --------- |
| Φ(t) | Φ0((1 | )cosω0t+ |     | cos((ω0+ω | )t+θ | )   | cos((ω0 | ω   | )t θ )) . |
|      |       |          |     |           | r    | r   |         | r   | r         |
| ≈    |       | − 4      | 2   |           |      | −2  |         | −   | −         |
(B.12)
Equation (B.9) has here been used. That approximation is used even in a
context of power system analysis other than rotor oscillations, namely when
studying so–called subsynchronous oscillations, SSO. If there is a resonance
phenomenon at a subsynchronous frequency it is called subsynchronous res-
onance, SSR. The most common cause of SSO are torsional oscillations on
the axis connecting the turbine(s) and the generator rotor. The frequencies
of the natural oscillations on that axis are typically 5 Hz and higher. (For
an axis with n distinct “masses”, including generator rotor and, maybe,
exciter, there are n 1 different eigenfrequencies.) For the side band in
−
Equation (B.12), i.e. for ω0 ω r , the frequency can deviate significantly
±
fromthenominalfrequency,sothatitisnormallynotpossibletolookonlyat
thecomponent with nominalfrequency. Since the electrical dampingfor the
lower side band, the subsynchronous frequency, can be negative, due to, for
example,seriescompensation,thepartitioningaccordingtoEquation(B.12)
has to be kept. The damping in the upper side band, the supersynchronous
| frequency, | is  | almost always | positive. |     |     |     |     |     |     |
| ---------- | --- | ------------- | --------- | --- | --- | --- | --- | --- | --- |
To increase the understanding for the partitioning in Equation (B.12), a
more intuitive derivation than the stringent mathematical one using Bessel

119
functions can be given. Consider a vector with amplitude 1 that performs
small oscillations with an angular frequency ω and amplitude µ. This can
r
be illustrated geometrically according to Figure B.3. The vector with filled
arrowhead oscillates symmetrically around the horizontal axis with the fre-
quency ω and the amplitude µ. That vector can now be partitioned into
r
the three vectors with unfilled arrowheads. One vector does not move and
lies along the horizontal axis. Two vectors with amplitude µ/2 rotate with
the angular frequency ω according to Figure B.3. It is easily observed
r
±
that the sum of the vectors with hollow arrowhead is at all times equal to
the vector with filled arrowhead. Since the vectors rotate with the angular
frequency ω0 with respect to a stationary system, Equation (B.12) is ob-
tained directly from the projection of the vectors on to the horizontal axis,
with the modification that the factor for the fundamental frequency is one.