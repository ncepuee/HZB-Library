PID Controllers, 2nd Edition
E
bY
Karl J. htrom
and
Tore Hdgglund

Copyright 0 1995 by Instrument Society of America
67 Alexander Drive
P.O. Box 12277
Research Triangle Park, NC 27709
All rights reserved.
Printed in the United States of America.
1 0 9 8 7 6 5 4
ISBN 1-55617 -5 16-7
No part of this work may be reproduced, stored in a retrieval system, or
transmitted in any form or by any means, electronic, mechanical, photocopying,
recording or otherwise, without the prior written permission of the publisher.
Library of Congress Cataloging-in-Publication Data
AstriSm, Karl J (Karl Johan), 1934 -
PID controllers; theory, design, and tuning/Karl Johan Astrom and Tore Hiigglund.--2nd ed
p. cm.
Rev. ed. of: Automatic tuning of PID controllers. C19SS.
Includes bibliographical references and index.
ISBN 1-55617-516-7
1. PID controllers. 1. Hagglund, Tore. 11. Astrorn, Karl J. (Karl, Johan), 1934-
Automatic tuning of PID controllers. 111. Title
TJ223.P55A87 1994
629.8--dc20 94-10735
CIP

Preface
In 1988 we published the book Automatic Thing of PID Controllers,
which summarized experiences gained in the development of an au-
tomatic tuner for a PID controller. The present book may be regarded
as a continuation of that book, although it has been significantly ex-
panded. Since 1988 we have learned much more about PID control as
a result of our involvement in research and industrial development of
PID controllers. Because of this we strongly believe that the practice
of PID can be improved considerably, and that this will contribute
significantly to improved quality of manufacturing. This belief has
been strongly reinforced by recent publications of the industrial state
of the art, which are referenced in Chapter 1.
The main reason for writing this book is to contribute to a bet-
ter understanding of PID control. Another reason is that information
about PID control is scattered in the control literature. The PID con-
troller has not attracted much attention from the research community
during the past decades, and it is often covered inadequately in stan-
dard textbooks in control, We believe that this book will be useful to
users and manufacturers of PID controllers as well as educators. It
is important to teach PID controI in introductory courses on feedback
control at universities, and we hope that this book can give useful
background for such courses.
It is assumed that the reader has a control background. A reader
should be familiar with concepts such as transfer functions, poles,
and zeros. Even so, the explanations are elementary. Occasionally,
we have stated facts without supporting detailed arguments, when
they have seemed unnecessary, in an effort to focus on the practical
aspects rather than the theory. A reader who finds that he needs som
specific background in process control is strongly advised to consult
a text in process control such as Seborg et al. (1989).
Compared to the earlier book we have expanded the material
substantially. The chapters on modeling, PID control, and design
of PID controllers have been more than doubled. The chapter on
automatic tuning has been completely rewritten to account for the
dynamic product development that has taken place in the last years.
There are two new chapters. One describes new tuning methods. This
V

vi Preface
material has not been published before. There is also a new chapter
on control paradigms that describes how complex systems can be
obtained by combining PID controllers with other components.
We would like to express our gratitude to several persons who
have provided support and inspiration. Our original interest in PID
control was stimulated by Axel Westrenius and Mike Sommerville
of Eurotherm who shared their experience of design and of PID
controllers with us. We have also benefited from discussions with
Manfred Morari of Caltech, Edgar Bristol of Foxboro, Ken Goff for-
merly of Leeds and Northrup, Terry Blevins of Fisher-Rosemount
Control, Gregory McMillan of Monsanto. Particular thanks are due to
Sune Larsson who initiated our first autotuner experiments and Lars
BBHth with whom we shared the pleasures and perils of developing
our first industrial auto-tuner. We are also grateful to many instru-
men\ engineers who participated in experiments and who generously
shared their experiences with us. Among our research colleagues we
have learned much from Professor C. C. Hang of Singapore National
University with whom we have done joint research in the field over
a long period of time. We are also grateful to Per Persson, who devel-
oped the dominant pole design method.
Several persons have read the manuscript of the book. WiTIy
Wojsznis of Fisher-Rosemount gave many valuable suggestions for im-
provements. Many present and former colleagues at our department
have provided much help. Special thanks are due to Eva DagnegArd
and Leif Andersson who made the layout for the final version and
Britt-Marie Mdrtensson who drew many of the figures. Ulf Holm-
berg, Karl-Erik &Zen and Mikael Sohansson gave very useful input
on several versions of the manuscript.
Finally we would like to express our deep gratitude to the Swedish
National Board of Industrial and Technical Development QWTEK)
who have supported our research.
ASTROM
KARL JOHAN
Tom HAGGLUND
Department of Automatic Control
Lund Institute of Technology
Box 118, S-22100L und, Sweden
karl-johan.astromQcontrol.lth.se
tore.hagglundQcontrol.1th.se

| Table                |                | of          | Contents        |          |     |
| -------------------- | -------------- | ----------- | --------------- | -------- | --- |
| 1. Introduction      |                | 1           |                 |          |     |
| 2. Process           | Models         | 5           |                 |          |     |
| 2.1 Introduction     |                | 5           |                 |          |     |
| 2.2 Static           | Models         | 6           |                 |          |     |
| 2.3 Dynamic          |                | Models      | 8               |          |     |
| 2.4 Step             | Response       | Methods     | 11              |          |     |
| 2.5 Methods          |                | of Moments  | 24              |          |     |
| 2.6 Frequency        |                | Responses   | 34              |          |     |
| 2.7 Parameter        |                | Estimation  | 43              |          |     |
| 2.8 Disturbance      |                | Models      | 46              |          |     |
| 2.9 Approximate      |                | Models      | and Unmodeled   | Dynamics | 51  |
| 2.10 Conclusions     |                | 57          |                 |          |     |
| 2.11 References      |                | 58          |                 |          |     |
| 3. PID Control       |                | 59          |                 |          |     |
| 3.1 Introduction     |                | 59          |                 |          |     |
| 3.2 The              | Feedback       | Principle   | 60              |          |     |
| 3.3 PID              | Control        | 64          |                 |          |     |
| 3.4 Modifications    |                | of the      | PID Algorithm   | 70       |     |
| 3.5 Integrator       |                | Windup      | 80              |          |     |
| 3.6 Digital          | Implementation |             | 93              |          |     |
| 3.7 Operational      |                | Aspects     | 103             |          |     |
| 3.8 Commercial       |                | Controllers | 108             |          |     |
| 3.9 When             | Can            | PID Control | Be Used?        | 109      |     |
| 3.10 Conclusions     |                | 116         |                 |          |     |
| 3.11 References      |                | 117         |                 |          |     |
| 4. Controller        | Design         | 120         |                 |          |     |
| 4.1 Introduction     |                | 120         |                 |          |     |
| 4.2 Specifications   |                | 121         |                 |          |     |
| 4.3 Ziegler-Nichols’ |                | and         | Related Methods | 134      |     |
| 4.4 Loop             | Shaping        | 151         |                 |          |     |
| 4.5 Analytical       |                | Tuning      | Methods 156     |          |     |
vii

| viii Table             | of        | Contents        |             |            |     |
| ---------------------- | --------- | --------------- | ----------- | ---------- | --- |
| 4.6 Optimization       |           | Methods         |             | 164        |     |
| 4.7 Pole               | Placement |                 | 173         |            |     |
| 4.8 Dominant           |           | Pole            | Design      | 179        |     |
| 4.9 Design             |           | for Disturbance |             | Rejection  | 193 |
| 4.10 Conclusions       |           | 196             |             |            |     |
| 4.11 References        |           | 197             |             |            |     |
| 5. New                 | Tuning    | Methods         |             | 200        |     |
| 5.1 Introduction       |           |                 | 200         |            |     |
| 5.2 A                  | Spectrum  | of              | Tools       | 201        |     |
| 5.3 Step-Response      |           |                 | Methods     | 203        |     |
| 5.4 Frequency-Response |           |                 |             | Methods    | 212 |
| 5.5 Complete           |           | Process         | Knowledge   |            | 218 |
| 5.6 Assessment         |           | of              | Performance |            | 220 |
| 5.7 Examples           |           | 224             |             |            |     |
| 5.8 Conclusions        |           | 228             |             |            |     |
| 5.9 References         |           | 228             |             |            |     |
| 6. Automatic           |           | Tuning          | and         | Adaptation | 230 |
| 6.1 Introduction       |           |                 | 230         |            |     |
| 6.2 Process            |           | Knowledge       |             | 232        |     |
| 6.3 Adaptive           |           | Techniques      |             | 232        |     |
| 6.4 Model-Based        |           | Methods         |             | 237        |     |
| 6.5 Rule-Based         |           | Methods         |             | 241        |     |
| 6.6 Commercial         |           | Products        |             | 243        |     |
| 6.7 Integrated         |           | Tuning          | and         | Diagnosis  | 262 |
| 6.8 Conclusions        |           | 270             |             |            |     |
| 6.9 References         |           | 270             |             |            |     |
| 7. Control             | Paradigms |                 | 273         |            |     |
| 7.1 Introduction       |           |                 | 273         |            |     |
| 7.2 Cascade            |           | Control         | 274         |            |     |
| 7.3 Feedforward        |           | Control         |             | 281        |     |
| 7.4 Model              |           | Following       | 284         |            |     |
| 7.5 Nonlinear          |           | Elements        |             | 287        |     |
| 7.6 Neural             |           | Network         | Control     | 295        |     |
| 7.7 Fuzzy              |           | Control         | 298         |            |     |
| 7.8 Interacting        |           | Loops           | 304         |            |     |
| 7.9 System             |           | Structuring     |             | 313        |     |
| 7.10 Conclusions       |           | 321             |             |            |     |
| 7.11 References        |           | 321             |             |            |     |
| Bibliography           |           | 323             |             |            |     |
| Index                  | 339       |                 |             |            |     |

Introduction
The PID controller has several important functions: it provides feed-
back; it has the ability to eliminate steady state offsets through in-
tegral action; it can anticipate the future through derivative action.
PIDcontrollers aresufficient for many control problems, particularly
whenprocessdynamicsarebenignandtheperformancerequirements
are modest. PID controllers are found in large numbers in all indus-
tries. The controllers come in many different forms. There are stand-
alonesystemsinboxesforoneorafewloops,whicharemanufactured
by the hundred thousands yearly. PID control is an important ingre-
dient of a distributed control system. The controllers are also em-
bedded in many special-purpose control systems. In process control,
more than 95% of the control loops are of PID type, most loops are
actuallyPIcontrol.ManyusefulfeaturesofPIDcontrolhavenotbeen
widelydisseminated becausetheyhavebeenconsideredtradesecrets.
Typical examples are techniques for mode switches and anti-windup.
PIDcontrolisoftencombinedwithlogic,sequentialmachines,se-
lectors, and simple function blocks to build the complicated automa-
tion systems used for energy production, transportation, and manu-
facturing. Many sophisticated control strategies, such as model pre-
dictive control, are also organized hierarchically. PID control is used
at the lowest level; the multivariable controller gives the setpoints to
thecontrollers atthelower level. ThePIDcontroller canthus besaid
tobethe“breadandbutter”ofcontrolengineering. Itisanimportant
component in every control engineer’s toolbox.
PID controllers have survived many changes in technology rang-
ing from pneumatics to microprocessors via electronic tubes, tran-
sistors, integrated circuits. The microprocessor has had a dramatic
influence on the PID controller. Practically all PID controllers made
today are based on microprocessors. This has given opportunities to
provide additional features like automatic tuning, gain scheduling,
and continuous adaptation. The terminology in these areas is not
well-established. For purposes of this book, auto-tuning means that
the controller parameters are tuned automatically on demand from
an operator or an external signal, and adaptation means that the
parameters of a controller are continuously updated. Practically all
1

2 Chapter 1 Introduction
new PID controllers that are announced today have some capability
for automatic tuning. Tuning and adaptation can be done in many
different ways. The simple controller has in fact become a test bench
for many new ideas in control.
Theemergence of thefieldbus isanother important development.
This will drastically influence the architecture of future distributed
control systems. The PID controller is an important ingredient of
the fieldbus concept. It may also be standardized as a result of the
fieldbus development.
A large cadre of instrument and process engineers are familiar
with PID control. There is a well-established practice of installing,
tuning,andusingthecontrollers.Inspiteofthistherearesubstantial
potentials for improving PID control. Evidence for this can be found
inthecontrolroomsofanyindustry.Manycontrollersareputinman-
ual mode, and among those controllers that are in automatic mode,
derivative action is frequently switched off for the simple reason that
it is difficult to tune properly. The key reasons for poor performance
is equipment problems in valves and sensors, and bad tuning prac-
tice.Thevalveproblemsincludewrongsizing,hysteresis,andstiction.
The measurement problems include: poor or no anti-aliasing filters;
excessive filtering in “smart” sensors, excessive noise and improper
calibration. Substantial improvements canbemade.Theincentive for
improvement is emphasized by demands for improved quality, which
is manifested by standards such as ISO 9000. Knowledge and un-
derstanding are the key elements for improving performance of the
control loop. Specific process knowledge is required as well as knowl-
edge about PID control.
Basedonourexperience, webelieve thataneweraofPIDcontrol
is emerging. This book will take stock of the development, assess its
potential, and try to speed up the development by sharing our expe-
riencesinthisexciting andusefulfieldofautomatic control. Thegoal
of the book is to provide the technical background for understanding
PIDcontrol. Suchknowledgecandirectlycontribute tobetter product
quality.
Processdynamicsisakeyforunderstanding anycontrolproblem.
Chapter 2 presents different ways to model process dynamics that
areuseful for PID control. Methods based on step tests arediscussed
togetherwithtechniquesbasedonfrequencyresponse.Itisattempted
toprovideagoodunderstanding oftherelationsbetweenthedifferent
approaches. Different ways to obtain parameters in simple transfer
function models based on the tests are also given. Two dimension-
free parameters are introduced: the normalized dead time and the
gain ratio are useful to characterize dynamic properties of systems
commonlyfoundinprocesscontrol.Methodsforparameterestimation
arealsodiscussed. Abriefdescription ofdisturbance modeling isalso

Chapter 1 Introduction 3
given.
An in depth presentation of the PID controller is given in Chap-
ter 3. This includes principles as well as many implementation de-
tails,suchaslimitation ofderivative gain,anti-windup, improvement
ofsetpoint response, etc.ThePIDcontroller canbestructured indif-
ferent ways. Commonly used forms are the series and the parallel
forms. The differences between these and the controller parameters
usedinthedifferent structures aretreated indetail. Implementation
of PID controllers using digital computers is also discussed. The un-
derlying concepts of sampling, choice of sampling intervals, and anti-
aliasing filters are treated thoroughly. The limitations of PID control
are also described. Typical cases where more complex controllers are
worthwhile aresystems with long dead time and oscillatory systems.
Extensions of PID control to deal with such systems are discussed
briefly.
Chapter 4 describes methods for the design of PID controllers.
Specifications are discussed in detail. Particular attention is given to
the information required to use the methods. Many different meth-
odsfortuningPIDcontrollersthathavebeendevelopedovertheyears
arethen presented. Their properties arediscussed thoroughly. Area-
sonable design method should consider load disturbances, model un-
certainty, measurement noise, and set-point response. A drawback
of many of the traditional tuning rules for PID control is that such
rules donot consider allthese aspects inabalanced way.Newtuning
techniques that do consider all these criteria are also presented.
Theauthorsbelievestronglythatnothingcanreplaceunderstand-
ing and insight. In view of the large number of controllers used in
industry there is a need for simple tuning methods. Such rules will
atleast be much better than “factory tuning,” but they can always be
improved by process modeling and control design. In Chapter 5 we
presentacollection ofnew tuning rulesthatgivesignificant improve-
ment over previously used rules.
In Chapter 6 we discuss some techniques for adaptation and au-
tomatic tuning of PID controllers. This includes methods based on
parametric models and nonparametric techniques. A number of com-
mercial controllers are also described to illustrate the different tech-
niques.Thepossibilities ofincorporatingdiagnosisandfaultdetection
in the primary control loop is also discussed.
In Chapter 7 it is shown how complex control problems can be
solved by combining simple controllers in different ways. The control
paradigms of cascade control, feedforward control, model following,
ratio control, split range control, and control with selectors are dis-
cussed. Use of currently popular techniques such as neural networks
and fuzzy control are also covered briefly.

| 4 Chapter | 1 Introduction |     |     |     |     |     |
| --------- | -------------- | --- | --- | --- | --- | --- |
References
A treatment of PID control with many practical hints is given in
(Shinskey, 1988). There is a Japanese text entirely devoted to PID
|            | (Suda   | 1992). |       |              |        |        |
| ---------- | ------- | ------ | ----- | ------------ | ------ | ------ |
| control by | et al., |        | Among | the books on | tuning | of PID |
controllers, we can mention (McMillan, 1983) and (Corripio, 1990),
| which are | published by ISA. |     |     |     |     |     |
| --------- | ----------------- | --- | --- | --- | --- | --- |
There are several studies that indicate the state of the art of in-
dustrialpracticeofcontrol.TheJapanElectricMeasuringInstrument
Manufacturers’ Association conducted asurveyofthestateofprocess
control systems in 1989, see (Yamamoto and Hashimoto, 1991). Ac-
cording to the survey more than than 90% of the control loops were
| of the PID | type. |     |     |     |     |     |
| ---------- | ----- | --- | --- | --- | --- | --- |
The paper, (Bialkowski, 1993), which describes audits of paper
millsinCanada,showsthatatypicalmillhasmorethan2000control
| loopsandthat97%usePIcontrol. |     |     | Only20%ofthecontrol |     | loopswere |     |
| ---------------------------- | --- | --- | ------------------- | --- | --------- | --- |
found to work well and decrease process variability. Reasons for poor
|             |                  |     | (30%) |                    | (30%). |     |
| ----------- | ---------------- | --- | ----- | ------------------ | ------ | --- |
| performance | were poor tuning |     |       | and valve problems |        | The |
remaining 20% of the controllers functioned poorly for a variety of
reasons such as: sensor problems, bad choice of sampling rates, and
(Ender, 1993),
| anti-aliasing | filters. Similar | observations |     | are given in |     |     |
| ------------- | ---------------- | ------------ | --- | ------------ | --- | --- |
where it is claimed that 30% of installed process controllers operate
in manual, that 20% of the loops use “factory tuning,” i.e., default
parameters set by the controller manufacturer, and that 30% of the
loops function poorly because of equipment problems in valves and
sensors.

Process Models
2.1 Introduction
A block diagram of a simple control loop is shown in Figure 2.1. The
systemhastwomajorcomponents,theprocessandthecontroller,rep-
resented as boxes with arrows denoting the causal relation between
inputsandoutputs. Theprocesshasoneinput, themanipulated vari-
able, also called the control variable. It is denoted by u. The process
output is called process variable (PV) and is denoted by y. This vari-
ableismeasuredbyasensor.Thedesiredvalueoftheprocessvariable
iscalled the setpoint (SP)or the reference value. Itis denoted by y .
sp
The control error e is the difference between the setpoint and the
process variable, i.e., e = y − y. The controller in Figure 2.1 has
sp
one input, the error, and one output, the control variable. The figure
shows that the process and the controller are connected in a closed
feedback loop.
The purpose of the system is to keep the process variable close
to the desired value in spite of disturbances. This is achieved by the
feedback loop, which works as follows. Assume that the system is in
equilibriumandthatadisturbanceoccurssothattheprocessvariable
becomes larger than the setpoint. The error is then negative and the
controller output decreases which in turn causes the process output
todecrease.Thistypeoffeedbackiscallednegativefeedback,because
the manipulated variable moves in direction opposite to the process
variable.
The controller has several parameters that can be adjusted. The
control loop performs well if the parameters are chosen properly. It
performs poorly otherwise, e.g., the system may become unstable.
The procedure of finding the controller parameters is called tuning.
This can be done in two different ways. One approach is to choose
some controller parameters, to observe the behavior of the feedback
system, and to modify the parameters until the desired behavior is
obtained. Another approach is to first develop a mathematical model
that describes the behavior of the process. The parameters of the
controller arethendetermined using somemethod forcontrol design.
5

| 6   | Chapter | 2 Process | Models |     |     |     |
| --- | ------- | --------- | ------ | --- | --- | --- |
|     | y       | e         |        | u   | y   |     |
sp Σ
|     |     |     | Controller | Process |     |     |
| --- | --- | --- | ---------- | ------- | --- | --- |
−1
|     | Figure | 2.1 Block | diagram | of asimple | feedback system. |     |
| --- | ------ | --------- | ------- | ---------- | ---------------- | --- |
An understanding of techniques for determining process dynamics is
a necessary background for both methods for controller tuning. This
| chapter | will | present such | techniques. |     |     |     |
| ------- | ---- | ------------ | ----------- | --- | --- | --- |
Static models are discussed in the next section. Dynamic models
are discussed in Section 2.3. Transient response methods, which are
usefulfordetermining simpledynamic modelsoftheprocess, arepre-
sented in Section 2.4. Section 2.5 treats methods based on moments.
These methods areless sensitive to measurement noise and, further-
more, are not restricted to any specific input signal. The frequency
response methods, described in Section 2.6, can be used to obtain
both simple models and more detailed descriptions. Methods based
on estimation of parametric models are more complex methods that
require more computations but less restrictions on the experiments.
These methods are presented in Section 2.7.The models discussed so
far describe the relation between the process input and output. It is
also important to model the disturbances acting on the system. This
is discussed in Section 2.8. Section 2.9 treats methods to simplify a
| complex | model | and the | problem | of unmodeled | dynamics and | mod- |
| ------- | ----- | ------- | ------- | ------------ | ------------ | ---- |
eling errors. Conclusions and references are given in Sections 2.10
and 2.11.
| 2.2 | Static | Models |     |     |     |     |
| --- | ------ | ------ | --- | --- | --- | --- |
Thestatic processcharacteristic isacurvethatgives thesteadystate
relation between process input signal u and process output y. See
Figure 2.2. Notice that the curve has a physical interpretation only
| for a | stable | process. |     |     |     |     |
| ----- | ------ | -------- | --- | --- | --- | --- |
All process investigations should start by a determination of the
static process model. It canbe used todetermine the range of control
signals required tochange the process output over the desired range,
to size actuators, and to select sensor resolution. It can also be used
to assess whether static gain variations are so large that they have
| to be | accounted | for in | the control | design. |     |     |
| ----- | --------- | ------ | ----------- | ------- | --- | --- |

2.2 Static Models 7
y
u
Figure 2.2 Static process characteristic. Shows process output y
as afunctionof process input uunder static conditions.
The static model can be obtained in several ways. It can be de-
termined by an open-loop experiment where the input signal is set
to a constant value and the process output is measured when it has
reached steady state. Thisgives one point onthe process characteris-
tics.Theexperimentisthenrepeatedtocoverthefullrangeofinputs.
An alternative procedure is to make a closed-loop experiment.
The setpoint is then given a constant value and the corresponding
control variable is measured in steady state. The experiment is then
repeated to cover the full range of setpoints.
The experiments required to determine the static process model
oftengiveagoodintuitive feelforhoweasyitistocontroltheprocess,
if it is stable, and if there are many disturbances.
Sometimesprocessoperationsdonotpermittheexperimentstobe
doneasdescribedabove.Smallperturbationsarenormallypermitted,
but it may not be possible to move the process over the full operating
range.Insuchacasetheexperiment mustbedone over along period
of time.
ProcessNoise
Process disturbances are easily determined by logging the process
output when the control signal is constant. Such a measurement
willgiveacombination ofmeasurementandloaddisturbances. There
are many sophisticated techniques such as time-series analysis and
spectral analysis that can be used to determine the characteristics
of the process noise. Crude estimates of the noise characteristics
are obtained simply by measuring the peak-to-peak value and by
determining the average time between zero crossings of the error

| 8 Chapter    | 2 Process    | Models  |                 |     |     |
| ------------ | ------------ | ------- | --------------- | --- | --- |
| signal. This | is discussed | further | in Section 2.8. |     |     |
| 2.3 Dynamic  |              | Models  |                 |     |     |
A static process model like the one discussed in the previous section
tellsthesteadystaterelationbetweentheinputandtheoutputsignal.
A dynamic model should give the relation between the input and the
output signal during transients. It is naturally much more difficult
to capture dynamic behavior. This is, however, very significant when
| discussing | control problems. |     |     |     |     |
| ---------- | ----------------- | --- | --- | --- | --- |
Fortunately there isarestricted classofmodels thatcanoften be
used. This applies to linear time-invariant systems. Such models can
often be used to describe the behavior of control systems when there
are small deviations from an equilibrium. The fact that a system is
linearimpliesthatthesuperposition principleholds.Thismeansthat
if the input u gives the output y and the input u gives the output
|     | 1   |     | 1   | 2   |     |
| --- | --- | --- | --- | --- | --- |
y it then follows that the input au +bu gives the output ay +by .
| 2   |     |     | 1 2 |     | 1 2 |
| --- | --- | --- | --- | --- | --- |
A system is time-invariant if its behavior does not change with time.
| Averynicepropertyoflineartime-invariant |     |     |     | systemsisthattheir |     |
| --------------------------------------- | --- | --- | --- | ------------------ | --- |
response to an arbitrary input can be completely characterized in
termsoftheresponsetoasimplesignal.Manydifferentsignalscanbe
used to characterize a system. Broadly speaking we can differentiate
| between | transient and | frequency | responses. |     |     |
| ------- | ------------- | --------- | ---------- | --- | --- |
In a control system we typically have to deal with two signals
only, the control signal and the measured variable. Process dynamics
aswe have discussed here only deals with the relation between those
signals.Themeasuredvariableshouldideallybecloselyrelatedtothe
physicalprocessvariablethatweareinterestedin.Sinceitisdifficult
to construct sensors it happens that there is considerable dynamics
in the relation between the true process variable and the sensor. For
example, it is very common that there aresubstantial time constants
in temperature sensors. There may also be measurement noise and
other imperfections. There may also be significant dynamics in the
actuators. To do a good job of control, it is necessary to be aware of
the physical origin the process dynamics to judge if a good response
in the measured variable actually corresponds to a good response in
| the physical | process | variable. |     |     |     |
| ------------ | ------- | --------- | --- | --- | --- |
TransientResponses
Intransientresponseanalysisthesystemdynamicsarecharacterized
in terms of the response to a simple signal. The particular signal is
often chosen so that it is easy to generate experimentally. Typical

|     |     |     |     |     | 2.3 | Dynamic | Models 9 |
| --- | --- | --- | --- | --- | --- | ------- | -------- |
examples are steps, pulses, and impulses. Because of the superpo-
sition principle the amplitude of the signals can be normalized. For
example, it is sufficient to consider the response to a step with unit
|     |     | s(t) |     |     |     |     | y(t) |
| --- | --- | ---- | --- | --- | --- | --- | ---- |
amplitude. If is the response to a unit step, the output to an
u(t)
| arbitrary | input | signal  | is      | given by |         |              |       |
| --------- | ----- | ------- | ------- | -------- | ------- | ------------ | ----- |
|           |       | (cid:1) |         |          | (cid:1) |              |       |
|           |       | t       | ds(t−τ) |          | t       |              |       |
|           | y(t)= | u(τ)    |         | dτ=      |         | u(τ)h(t−τ)dτ | (2.1) |
|           |       | −∞      |         | dt       | −∞      |              |       |
h(t)
where the impulse response is introduced as the time derivative
| of the | step response. |     |     |     |     |     |     |
| ------ | -------------- | --- | --- | --- | --- | --- | --- |
In early process control literature the step response was also
| called | the reaction | curve. |     |     |     |     |     |
| ------ | ------------ | ------ | --- | --- | --- | --- | --- |
Pulse response analysis is common in medical and biological ap-
plications, but rather uncommon in process control. Ramp response
analysis is less common. One application is the determination of the
derivative part of a PID controller. In process control, the step re-
sponse is the most common transient used for process identification.
This is primarily because this is the type of disturbance that is easi-
esttogeneratemanually.Stepresponse methods aretreatedindetail
| in Section | 2.4. |     |     |     |     |     |     |
| ---------- | ---- | --- | --- | --- | --- | --- | --- |
FrequencyResponse
Another way to characterize the dynamics of a linear time-invariant
system is to use sine waves as a test signal. This idea goes back
to Fourier. The idea is that the dynamics can be characterized by
| investigating |     | how sine | waves | propagate | through | a system. |     |
| ------------- | --- | -------- | ----- | --------- | ------- | --------- | --- |
Consider a stable linear system. If the input signal to the system
is a sinusoid, then the output signal will also be a sinusoid after a
transient(seeFigure2.3).Theoutputwillhavethesamefrequencyas
theinputsignal.Onlythephaseandtheamplitudearedifferent.This
meansthatunderstationary conditions, therelationship between the
input and the output can be described by two numbers: the quotient
(a) between the input and the output amplitude, and the phase shift
| (ϕ)betweentheinputandtheoutputsignals. |     |     |     |     |     |     | a(ω)and |
| -------------------------------------- | --- | --- | --- | --- | --- | --- | ------- |
Thefunctions
| ϕ(ω)describe |     | aandϕfor      |                  |              | (ω).Itisconvenient |              |        |
| ------------ | --- | ------------- | ---------------- | ------------ | ------------------ | ------------ | ------ |
|              |     |               | allfrequencies   |              |                    |              | toview |
| a andϕas     |     | the magnitude | and              | the argument |                    | of a complex | number |
|              |     |               | G(iω)=a(ω)eiϕ(ω) |              |                    |              | (2.2)  |
G(iω)
The function is called the frequency response function of the
system.Thefunction a(ω)=(cid:2)G(iω)(cid:2)iscalledtheamplitude function,
and the function ϕ(ω)= ar(cid:3)(G(iω)) is called the phase function.
G(iω)
| The | complex | number |     | can | be represented | by  | a vector with |
| --- | ------- | ------ | --- | --- | -------------- | --- | ------------- |
length a(iω) that forms angle ϕ(iω) with the real axis (see Figure

| 10 Chapter | 2 Process | Models |     |     |
| ---------- | --------- | ------ | --- | --- |
y
0.1
0
| 0   |     | 5   | 10  | 15  |
| --- | --- | --- | --- | --- |
1 u
−1
| 0   |     | 5   | 10  | 15  |
| --- | --- | --- | --- | --- |
Figure 2.3 Input signal u is a sinusoid and output signal y be-
| comessinusoidal | aftera | transient. |     |     |
| --------------- | ------ | ---------- | --- | --- |
 I m  G   (iω)
Ultimate point
 R e  G   (iω)
|     | −1  | ϕ   |     |     |
| --- | --- | --- | --- | --- |
a
ω
|                       | Figure 2.4 | The Nyquist              | curve of a system. |     |
| --------------------- | ---------- | ------------------------ | ------------------ | --- |
| 2.4).Whenthefrequency |            | goesfrom0to∞,theendpoint |                    |     |
ofthevector
describes a curve in the plane, which is called the frequency curve
or the Nyquist curve. The Nyquist curve gives a complete description
of the system. It can be determined experimentally by sending sinu-
soids of different frequencies through the system. This may be time
consuming. Normally, it suffices to know only parts of the Nyquist
curve. For controller tuning there are some parts that are of particu-
−180 ○
lar interest. The lowest frequency where the phase is is called
the ultimate frequency (ω ). The corresponding point on the Nyquist
u
curve is called the ultimate point. The value of G(iω ) is all that is
u
needed for the tuning methods developed by Ziegler and Nichols.
ThefrequencyresponseisintimatelyrelatedtotheLaplacetrans-

|     |     |     |     | 2.4 | StepResponse | Methods |     | 11  |
| --- | --- | --- | --- | --- | ------------ | ------- | --- | --- |
form. Let f(t) be a signal. The Laplace transform of the signal, F(s),
| is then | defined | by  |     | (cid:1) |     |     |     |     |
| ------- | ------- | --- | --- | ------- | --- | --- | --- | --- |
∞
|     |     |     | F(s)= | e −stf(t)dt |     |     |     | (2.3) |
| --- | --- | --- | ----- | ----------- | --- | --- | --- | ----- |
0
Let U(s) and Y(s) be the Laplace transforms of the input and the
output of a linear time-invariant dynamical system. Assume that the
t=0.
| system     | is at rest | at time  |          | The following | relation | then | holds |       |
| ---------- | ---------- | -------- | -------- | ------------- | -------- | ---- | ----- | ----- |
|            |            |          | Y(s)=    | G(s)U(s)      |          |      |       | (2.4) |
| where G(s) | is the     | transfer | function | of the        | system.  |      |       |       |
(2.3)
| It follows | from | Equation |     | that the | Laplace | transform |     | of an |
| ---------- | ---- | -------- | --- | -------- | ------- | --------- | --- | ----- |
impulse is 1. From Equation (2.4) we can conclude that G(s) is the
Laplace transform of the impulse response. The frequency response
G(iω).
is simply
Inthefollowingsectionswewillshowhowlinearsystemdynamics
canbe obtained experimentally. We will illustrate both transient and
| frequency | response | methods. |     |         |     |     |     |     |
| --------- | -------- | -------- | --- | ------- | --- | --- | --- | --- |
| 2.4       | Step     | Response |     | Methods |     |     |     |     |
The dynamics of a process can be determined from the response of
the process to pulses, steps, ramps, or other deterministic signals.
The dynamics of a linear system is, in principle, uniquely given from
such a transient response experiment. This requires, however, that
| thesystem | isatrestbeforetheinputisapplied, |     |     |     | andthatthereareno |     |     |     |
| --------- | -------------------------------- | --- | --- | --- | ----------------- | --- | --- | --- |
measurementerrors.Inpractice,however,itisdifficulttoensurethat
the system is at rest. There will also be measurement errors, so the
transientresponsemethod,inpractice,islimitedtothedetermination
of simple models. Models obtained from a transient experiment are,
however, often sufficient for PID controller tuning. The methods are
also very simple to use. This section focuses on the step response
method.
TheStepResponse
Assuming a control loop with a controller, the step response experi-
ment can be determined as follows. Wait until the process is at rest.
Setthecontrollertomanual.Changethecontrolvariablerapidly,e.g.,
throughtheuseofincrease/decreasebuttons.Recordtheprocessvari-
able and scale it by dividing by the change in the control variable.
Thechangein control variable should beaslargeaspossible inorder
togetamaximumsignaltonoiseratio.Thelimitissetbypermissible

| 12 Chapter | 2 Process | Models |     |     |     |
| ---------- | --------- | ------ | --- | --- | --- |
| A          |           |        | B   |     |     |
0.8
1
0.4
| 0   |     |     | 0   |     |     |
| --- | --- | --- | --- | --- | --- |
| 0   | 2 4 | 6 8 | 0 2 | 4 6 | 8   |
| C   |     |     | D   |     |     |
0.4
2
| 0   |     |     | 0   |     |     |
| --- | --- | --- | --- | --- | --- |
| 0   | 2 4 | 6 8 | 0 2 | 4 6 | 8   |
| E   |     |     | F   |     |     |
0.8
0.5
0.4
| 0   |        |               | −0.5           |     |     |
| --- | ------ | ------------- | -------------- | --- | --- |
| 0   | 2 4    | 6 8           | 0 2            | 4 6 | 8   |
|     | Figure | 2.5 Open-loop | stepresponses. |     |     |
process operation. It is also useful to record the fluctuations in the
measurement signal when the control signal is constant. This gives
| data about | the process | noise. |     |     |     |
| ---------- | ----------- | ------ | --- | --- | --- |
It is good practice to repeat the experiment for different ampli-
tudes of the input signal and at different operating conditions. This
gives an indication of the signal ranges when the model is linear. It
also indicates if the process changes with the operating conditions.
Examples of open-loop step responses are shown in Figure 2.5.
Many properties of the system can be read directly from the step re-
sponse. In Figure 2.5A, the process output is monotonically changed
to a new stationary value. This is the most common type of step re-
sponse encountered in process control. In Figure 2.5B, the process
output oscillates around its final stationary value. This type of pro-
cess is uncommon in process control. One case where it occurs is in
concentration control of recirculation fluids. In mechanical designs,
however,oscillatingprocessesarecommonwhereelasticmaterialsare
used, e.g., weak axles in servos, spring constructions, etc. The sys-
tems in Figures 2.5A and B are stable, whereas the systems shown
in Figures 2.5C and 2.5D are unstable. The system in Figure 2.5C
shows the output of an integrating process. Examples of integrating
processes are level control, pressure control in a closed vessel, con-
centrationcontrolinbatches,andtemperaturecontrolinwellisolated
| chambers.Thecommonfactorinalltheseprocesses |     |     |     | isthatsomekind |     |
| ------------------------------------------- | --- | --- | --- | -------------- | --- |
ofstorageoccursinthem.Inlevel,pressureandconcentration control

2.4 StepResponse Methods 13
storageofmassoccurs, whileinthecaseoftemperature control there
is a storage of energy. The system in Figure 2.5E has a long dead
time. The dead time occurs when there are transportation delays in
the process. The system in Figure 2.5F is a non-minimum phase sys-
tem, where the measurement signal initially moves in the “wrong”
direction. The water level in boilers often reacts like this after a step
change in feed water flow.
If the system is linear, all step responses are proportional to
the size of the step in the input signal. It is then convenient to
normalize the responses by dividing the measurement signal by the
step size of the control signal. Throughout this book we assume that
this normalization is done.
The step response is a convenient way to characterize process
dynamics because of its simple physical interpretation. Many tuning
methods are based on it. A formal mathematical model can also be
obtained from the step response. General methods for the design of
control systems can then be used.
Forsmallperturbations thestaticprocessmodelcanbedescribed
by one parameter called the process gain. This is simply the ratio of
thesteadystatechangesofprocessoutputandprocessinput.Thegain
can be obtained as the slope of the curve in Figure 2.2. It can also
be obtained directly from a step response. For nonlinear systems the
process gain will depend on the operating conditions. It is, however,
constantforlinearsystems.Forsuchsystemsthestaticpropertiesare
thus described by one parameter. Additional parameters are needed
to also capture dynamics. Some simple parametric models will be
described below. Stable processes with a monotone step response, as
shown in Figure 2.5A, are quite common. Many methods to obtain
parametric models from such a step response have been presented in
the literature over the years. We will present here models with two,
three, and, four parameters respectively.
Two-ParameterModels
Thesimplestparametricmodelsofprocessdynamicshavetwoparam-
eters. One parameter can be process gain. The other has to capture
the time behavior. The average residence time T is a useful param-
ar
eter. This is obtained as
A
T = 0
ar K
where K is the static process gain and A is defined as
0
(cid:1)∞
A = (s(∞)−s(t))dt
0
0

| 14 Chapter |     | 2 Process | Models |     |     |     |     |     |
| ---------- | --- | --------- | ------ | --- | --- | --- | --- | --- |
where s(t) is the step response. Notice that K = s(∞) and that A is
0
| the shaded | area | in  | Figure 2.6. |     |     |     |     |     |
| ---------- | ---- | --- | ----------- | --- | --- | --- | --- | --- |
The time T is a rough measure of the time it takes for the step
ar
response to settle. Using the static gain and the average residence
| time, the | process | can | be approximated |     | by the | model |     |     |
| --------- | ------- | --- | --------------- | --- | ------ | ----- | --- | --- |
K
|     |     |     | G   | (s)= |      |     |     | (2.5) |
| --- | --- | --- | --- | ---- | ---- | --- | --- | ----- |
|     |     |     | 2a  |      | 1+sT |     |     |       |
ar
| We call    | this model    |       | the residence   | time | approximation. |      |      |         |
| ---------- | ------------- | ----- | --------------- | ---- | -------------- | ---- | ---- | ------- |
| Another    | approximation |       | to              | the  | step response  | that | also | has two |
| parameters | is            | given | by the transfer |      | function       |      |      |         |
a
|     |     |     | G   | (s)= | e −sL |     |     | (2.6) |
| --- | --- | --- | --- | ---- | ----- | --- | --- | ----- |
2b
sL
This model corresponds to an integrator with dead time. This model
is characterized by the two parameters, a and L, that are easily de-
termined graphically from the step response (see Figure 2.6). The
s(t)
tangent to the step response that has the largest slope is drawn,
and the intersections of this tangent with the vertical and horizontal
axes give a and L, respectively. The model given by Equation (2.6) is
thebasis for the Ziegler-Nichols tuning procedure discussed in Chap-
ter 4. Notice that the model can also be fitted to unstable processes.
|                   |             |     |                       |     | (2.5) |           | (2.6)  |            |
| ----------------- | ----------- | --- | --------------------- | --- | ----- | --------- | ------ | ---------- |
| The               | properties  |     | of the approximations |     |       | and       |        | are illus- |
| trated by         | an example. |     |                       |     |       |           |        |            |
| EXAMPLE           | 2.1         |     |                       |     |       |           |        |            |
|                   |             |     | (2.5)                 |     | (2.6) |           |        |            |
| The two-parameter |             |     | models                | and |       | have been | fitted | to the     |
K
A
0
a
L
| Figure | 2.6 | Graphical | determination |     | of a | two-parameter |     | model |
| ------ | --- | --------- | ------------- | --- | ---- | ------------- | --- | ----- |
from a step response for a stable system with a monotone step
response.

|     |     |     |     |     | 2.4 StepResponse |     | Methods | 15  |
| --- | --- | --- | --- | --- | ---------------- | --- | ------- | --- |
process model
1
|     |     |     | G(s)= |     |     |     |     | (2.7) |
| --- | --- | --- | ----- | --- | --- | --- | --- | ----- |
(s+1)8
| The following |     | models were | obtained |     |        |      |       |     |
| ------------- | --- | ----------- | -------- | --- | ------ | ---- | ----- | --- |
|               |     |             | 1        |     |        | 0.64 | −4.3s |     |
|               | G   | (s)=        |          |     | G (s)= |      | e     |     |
|               | 2a  | 1+8.0s      |          |     | 2b     |      |       |     |
4.3s
Figure 2.7 shows the step responses and the Nyquist curves of the
transfer functions.
| Notice | that | the model | G   | gives | a good | description | of the | step |
| ------ | ---- | --------- | --- | ----- | ------ | ----------- | ------ | ---- |
2a
response for long times. The static gain is correct and the step re-
sponse is very close to the correct one for large t. There are, however,
large discrepances for small t. The system given by G has, for ex-
2a
|        |               |          |     |         | =   |        |            | (2.7) |
| ------ | ------------- | -------- | --- | ------- | --- | ------ | ---------- | ----- |
| ample, | a significant | response |     | at time | t   | 2, but | the system |       |
has barely responded at that time. The model G has the opposite
2b
properties. It approximates the true step response very well in the
|          | 5≤ t≤9, |     |                   |     |     |           |           |     |
| -------- | ------- | --- | ----------------- | --- | --- | --------- | --------- | --- |
| interval |         | but | the approximation |     | is  | very poor | for large | t.  |
These properties are also reflected in the Nyquist curves. They
show that the average residence time approximation is quite good at
low frequencies but very poor at high frequencies. The model G , on
2b
the other hand, is poor at low frequencies but reasonable at middle
range frequencies.
Three-ParameterModels
Better approximations are obtained by increasing the number of pa-
1
1
x
x
Im0
x
x
x
x
x
x
| 0   |     |     |     |     | –1  |     |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| 0   |     | 10  |     | 20  | –1  |     | 0   | 1   |
Re
| Figure        | 2.7 | Step responses                       |     | and | Nyquist | curves | of the process |     |
| ------------- | --- | ------------------------------------ | --- | --- | ------- | ------ | -------------- | --- |
| G(s)=1/(s+1)8 |     | (solidline)andthetwo-parametermodels |     |     |         |        | G              | (s) |
2a
| (dotted | line) | and G | (s)(dashed | line). |     |     |     |     |
| ------- | ----- | ----- | ---------- | ------ | --- | --- | --- | --- |
2b

| 16 Chapter | 2 Process | Models |     |     |     |     |
| ---------- | --------- | ------ | --- | --- | --- | --- |
| rameters.  | The model |        |     |     |     |     |
K
|     |     | G(s)= | −sL |     |     | (2.8) |
| --- | --- | ----- | --- | --- | --- | ----- |
e
1+sT
is characterized by three parameters: the static gain K, the time
constant T, and the dead time L. This is the most common process
model used in papers on PID controller tuning. The parameters L
and T are often called the apparent dead time and the apparent time
constant, respectively. The step response of the model (2.8) is
|     |     | (cid:2) |              | (cid:3) |     |     |
| --- | --- | ------- | ------------ | ------- | --- | --- |
|     |     | s(t)= K | 1−e −(t−L)/T |         |     |     |
From this equation, it follows that the average residence time is
(cid:4)∞
(s(∞)−s(t))dt
|     |     | = 0 |     | = L+T |     |     |
| --- | --- | --- | --- | ----- | --- | --- |
T ar
K
The ratio
|     |     | L   | L   |     |     |       |
| --- | --- | --- | --- | --- | --- | ----- |
|     |     | τ=  | =   |     |     | (2.9) |
L+T
T ar
| whichhastheproperty |     | 0≤τ≤1,iscalledthenormalizeddeadtime. |     |     |     |     |
| ------------------- | --- | ------------------------------------ | --- | --- | --- | --- |
This quantity can be used to characterize the difficulty of controlling
aprocess.Itissometimesalsocalledthecontrollabilityratio.Roughly
speaking, it has been found that processes with small τare easy to
control and that the difficulty in controlling the system increases
as τ increases. Systems with τ = 1 correspond to pure dead-time
| processes, | which are | indeed difficult | to control | well. |     |     |
| ---------- | --------- | ---------------- | ---------- | ----- | --- | --- |
Theparametersinthemodel(2.8)canbedetermined
graphically.
Thestaticgain(K)isobtainedfromthefinalsteady-state levelofthe
process output. Remember that the process output must be scaled
with the change in the control variable. The intercept of the tangent
to the step response that has the largest slope with the horizontal
|            | (see     | 2.8). |           |            |     |          |
| ---------- | -------- | ----- | --------- | ---------- | --- | -------- |
| axes gives | L Figure | The   | dead time | L can also | be  | obtained |
as the time between the onset of the step and the time s(t) has
reached a few percent of its final value. There are different ways
to determine T. One method determines T from the distance AC in
| Figure2.8,wherethepoint |            | C isthetimewhenthetangentintersects |            |        |     |          |
| ----------------------- | ---------- | ----------------------------------- | ---------- | ------ | --- | -------- |
|                         | s(t) =     |                                     |            |        |     |          |
| the line                | K. Another | method                              | determines | T from | the | distance |
AB in Figure 2.8, where B is the time when the step response has
reached the value 0.63K. Both methods give identical results if the
process dynamics are given by Equation (2.8), but they may differ
significantly in other cases. The method based on the point B gives
| normallybetterapproximations. |       |     | Theother | methodtendstogiveatoo |     |     |
| ----------------------------- | ----- | --- | -------- | --------------------- | --- | --- |
| large value                   | of T. |     |          |                       |     |     |

|     |     |     |     |     | 2.4 StepResponse |     | Methods | 17  |
| --- | --- | --- | --- | --- | ---------------- | --- | ------- | --- |
K
0.63 K
|     |     | L   |     |     |           |     |     |     |
| --- | --- | --- | --- | --- | --------- | --- | --- | --- |
B      C
A
|         | Figure 2.8      | Graphical | determination |               | of three-parameter |     | models |     |
| ------- | --------------- | --------- | ------------- | ------------- | ------------------ | --- | ------ | --- |
|         | for systemswith | amonotone |               | stepresponse. |                    |     |        |     |
| EXAMPLE | 2.2             |           |               |               |                    |     |        |     |
(2.7)
| The | three-parameter |        | models  | of the | process model |        | are     |     |
| --- | --------------- | ------ | ------- | ------ | ------------- | ------ | ------- | --- |
|     |                 | 1      |         |        |               |        | 1       |     |
|     | G (s)=          |        | e −4.3s |        | G (s)=        |        | e −4.3s |     |
|     | 3a              | 1+6.7s |         |        | 3b            | 1+4.3s |         |     |
where the time constant T is determined from the point C in model
G , and from the point B in the model G . Figure 2.9 shows the
| 3a  |     |     |     |     | 3b  |     |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
step responses of the true process and the models, as well as the
Nyquist curves of the transfer functions. The figure shows that the
time constant T is overestimated in the model G 3a . This overesti-
mation is unfortunately common in this method, since most process
control plants have an S-shaped step response similar to the model
(2.7).
Notice that the true step response and the step response of the
| model | G coincide | at  | the 63% | point. |     |     |     |     |
| ----- | ---------- | --- | ------- | ------ | --- | --- | --- | --- |
3b
| Another | Model | Structure |     |     |     |     |     |     |
| ------- | ----- | --------- | --- | --- | --- | --- | --- | --- |
Themodel(2.8)isbyfarthemostcommonlyusedmodelinthepapers
of PID controller tuning. In spite of this, it is not a representative
model. In fact, the conclusions drawn based on this model may often
bemisleading when applied toreal processes. This will beillustrated
| byseveral | examplesinChapter |     |     | 4.Onereasonfor |     | thisisthatthestep |     |     |
| --------- | ----------------- | --- | --- | -------------- | --- | ----------------- | --- | --- |
response of the model (2.8) is not S-shaped, or equivalently, that the
frequency response of the model does not decay fast enough for high
frequencies.

| 18 Chapter |     | 2 Process | Models |     |     |     |     |     |     |
| ---------- | --- | --------- | ------ | --- | --- | --- | --- | --- | --- |
| 1          |     |           |        |     | 1   |     |     |     |     |
x
x x
Im0
x
x x
x xx
| 0   |     |     |     |     | –1    |     |     |     |     |
| --- | --- | --- | --- | --- | ----- | --- | --- | --- | --- |
| 0   |     | 10  |     |     | 20 –1 |     | 0   |     | 1   |
Re
| Figure                                               | 2.9 | Step | responses | and | Nyquist | curves | of the | process |     |
| ---------------------------------------------------- | --- | ---- | --------- | --- | ------- | ------ | ------ | ------- | --- |
| G(s)=1/(s+1)8(solidline)andthethree-parametermodelsG |     |      |           |     |         |        |        | (s)     |     |
3a
| (dashed | line)           |     | (s)(dotted | line). |     |     |     |     |     |
| ------- | --------------- | --- | ---------- | ------ | --- | --- | --- | --- | --- |
|         |                 | and | G 3b       |        |     |     |     |     |     |
| Another | three-parameter |     | model      | is     |     |     |     |     |     |
K
|     |     |     | G(s)= |     | e −sL |     |     | (2.10) |     |
| --- | --- | --- | ----- | --- | ----- | --- | --- | ------ | --- |
(1+sT)2
| The step | response | of  | this model | is      |         |     |         |     |     |
| -------- | -------- | --- | ---------- | ------- | ------- | --- | ------- | --- | --- |
|          |          |     | (cid:5)    | (cid:5) | (cid:6) |     | (cid:6) |     |     |
t−
|     |     | s(t)= | 1−  | 1+  | L   | −(t−L)/T |     | (2.11) |     |
| --- | --- | ----- | --- | --- | --- | -------- | --- | ------ | --- |
|     |     |       | K   |     | e   |          |     |        |     |
T
This model has an S-shaped step response and often gives a better
(2.8).Static
| approximation |          | thanthefirst-order |     |        | plus dead-time | model  |      |     |     |
| ------------- | -------- | ------------------ | --- | ------ | -------------- | ------ | ---- | --- | --- |
| gain K        | and dead | time               | L   | can be | determined     | in the | same | way | as  |
for the model (2.8). Time constant T can then be determined from
Equation 2.11 if the value of the step response at one time is known.
| The equation |           | obtained | must | be solved   | numerically. |       |       |     |     |
| ------------ | --------- | -------- | ---- | ----------- | ------------ | ----- | ----- | --- | --- |
| EXAMPLE      | 2.3       |          |      |             |              |       |       |     |     |
|              |           | (2.10)   |      |             |              | (2.7) |       |     |     |
| Fitting      | the model |          | to   | the process | model        |       | gives |     |     |
|              |           |          | (s)= |             | 1 −4.3s      |       |       |     |     |
|              |           |          | G    |             | e            |       |       |     |     |
|              |           |          | 3c   | (1+2.0s)2   |              |       |       |     |     |
The gain K =1 is obtained from the steady-state value of the signal,
=
and the dead time L 4.3 is obtained from the intersection of the
tangent with the largest slope and the horizontal axis as in the
previous examples. The two time constants T = 2.0 are obtained
|              |     |          |             |     | (2.11). |       | s(8.6) | =    |     |
| ------------ | --- | -------- | ----------- | --- | ------- | ----- | ------ | ---- | --- |
| by numerical |     | solution | of Equation |     | The     | point |        | 0.63 | is  |
used to obtain the additional condition. Figure 2.10 shows the step

|     |     |     |     | 2.4 | StepResponse | Methods |     | 19  |
| --- | --- | --- | --- | --- | ------------ | ------- | --- | --- |
| 1   |     |     |     |     | 1            |         |     |     |
x x
Im0
xx
xx
| 0   |     |     |     | –1  |     |     |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| 0   | 10  |     |     | 20  | –1  | 0   |     | 1   |
Re
| Figure 2.10                                         | Step | responses | and | Nyquist | curves | of the | process |     |
| --------------------------------------------------- | ---- | --------- | --- | ------- | ------ | ------ | ------- | --- |
| G(s)=1/(s+1)8(solidline)andthethree-parametermodelG |      |           |     |         |        |        |         | (s) |
3c
| (dashed line). |     |     |     |     |     |     |     |     |
| -------------- | --- | --- | --- | --- | --- | --- | --- | --- |
(s),aswellastheNyquist
| responsesofthetrueprocessmodeland |     |     |     | G   |     |     |     |     |
| --------------------------------- | --- | --- | --- | --- | --- | --- | --- | --- |
3c
curves of the two transfer functions. The two step responses coincide
at the 63% point. The model now has the S-shaped form because of
the second-order model, and the fit is much better than the previous
| first-order models. |     |     |     |     |     |     |     |     |
| ------------------- | --- | --- | --- | --- | --- | --- | --- | --- |
Four-ParameterModels
An even better approximation may be obtained by the transfer func-
tion
|     |       |       |     | K      | −sL |     |     |        |
| --- | ----- | ----- | --- | ------ | --- | --- | --- | ------ |
|     | G(s)= |       |     |        | e   |     |     | (2.12) |
|     |       | (1+sT |     | )(1+sT | )   |     |     |        |
|     |       |       | 1   |        | 2   |     |     |        |
This model has four parameters: the gain K, the time constants T
1
| and T ,andthedeadtime |     | L.Thegain |     | K   | canbedetermined |     | fromthe |     |
| --------------------- | --- | --------- | --- | --- | --------------- | --- | ------- | --- |
2
steady-state value of the step response. The dead time L can also be
obtained in the same way as for the three-parameter models either
by drawing the tangent of maximum slope of s(t) or by determining
s(t)
the time between the onset of the step and the time has reached
afew percent of its final value. The step response of the model (2.12)
is
|       | (cid:5) |           |     |             | (cid:6) |           |     |        |
| ----- | ------- | --------- | --- | ----------- | ------- | --------- | --- | ------ |
|       | T e     | −(t−L)/T2 | −T  | e −(t−L)/T1 |         |           |     |        |
| s(t)= | 1+ 2    |           | 1   |             |         | (cid:6)=T |     | (2.13) |
| K     |         |           |     |             |         | T         |     |        |
|       |         | T         | −T  |             |         | 1         | 2   |        |
1 2
The time constants (T ) and (T ) can be calculated from this expres-
|     | 1   |     | 2   |     |     |     |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
sion by determining two points of the step response. The calculation
does involve solution of transcendental equations. This must be done
numerically.

| 20 Chapter | 2   | ProcessModels |     |     |     |     |     |     |
| ---------- | --- | ------------- | --- | --- | --- | --- | --- | --- |
| 1          |     |               |     |     | 1   |     |     |     |
x x
Im0
xx
xx
| 0   |     |     |     |     | –1  |     |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| 0   |     | 10  |     | 20  | –1  |     | 0   | 1   |
Re
| Figure | 2.11 | Step | responses | and | Nyquist | curves | of the process |     |
| ------ | ---- | ---- | --------- | --- | ------- | ------ | -------------- | --- |
G(s)=1/(s+1)8 (solid line) and the four-parameter model G (s)
4a
| (dashed | line). |     |     |     |     |     |     |     |
| ------- | ------ | --- | --- | --- | --- | --- | --- | --- |
2.4
EXAMPLE
A four-parameter model (2.12) of the process model (2.7) has been
=
obtained in the following way. The gain K 1 is determined from
the steady-state values, and the dead time L = 4.3 is obtained from
the largest slope, as in the previous examples. The time constants T 1
and T are then obtained by numerically fitting the equation for the
2
stepresponse(2.13)tothevaluesofthetruestepresponseatthe33%
|           |         |        |      | s(6.5) | =    | s(8.9) | =   |           |
| --------- | ------- | ------ | ---- | ------ | ---- | ------ | --- | --------- |
| point and | the 67% | point. | With |        | 0.33 | and    |     | 0.67, the |
time constants become T =0.93 and T =3.2. The transfer function
|     |     |     | 1   |     | 2   |     |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
is thus
1
|     |     | G (s)= |                   |     |     | e −4.3s |     |     |
| --- | --- | ------ | ----------------- | --- | --- | ------- | --- | --- |
|     |     | 4a     | (1+0.93s)(1+3.2s) |     |     |         |     |     |
Figure 2.11 shows the step responses of the true process model and
G (s), as well as the Nyquist curves of the two transfer functions.
4a
Notice that the two step responses coincide at the 33% point and at
the 67% point.
| In the | previous | example, |     | gain K | and dead | time | L were | deter- |
| ------ | -------- | -------- | --- | ------ | -------- | ---- | ------ | ------ |
minedgraphically fromthestepresponse, whereas timeconstants T
1
and T weredetermined bynumerical solution oftheequation forthe
2
stepresponse.Thereareseveralmethodspresentedforagraphicalde-
terminationofallfourparametersofthemodel(2.12).Thesemethods
are useful when no computers are available for numerical solutions.
Using computer optimization programs, however, often gives a better
approximation than the graphical methods. This is illustrated in the
| following example. |     |     |     |     |     |     |     |     |
| ------------------ | --- | --- | --- | --- | --- | --- | --- | --- |

|     |     |     |     | 2.4 | StepResponse | Methods | 21  |
| --- | --- | --- | --- | --- | ------------ | ------- | --- |
1
1
xx
Im0
xx
x x
| 0   |     |     |     |     | –1  |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- |
| 0   |     | 10  |     | 20  | –1  | 0   | 1   |
Re
| Figure | 2.12       | Step responses |       | and Nyquist | curves         | of the process |     |
| ------ | ---------- | -------------- | ----- | ----------- | -------------- | -------------- | --- |
| G(s)   | = 1/(s+1)8 | (solid         | line) | and the     | four-parameter | model G        |     |
4b
| (dashed | line). |     |     |     |     |     |     |
| ------- | ------ | --- | --- | --- | --- | --- | --- |
| EXAMPLE | 2.5    |     |     |     |     |     |     |
model(2.12)hasbeenfittedtotheprocess
| Thefour-parameter |     |     |     |     |     |     | model |
| ----------------- | --- | --- | --- | --- | --- | --- | ----- |
(2.7) using least squares optimization, where the aim was to obtain
an accurate model in the third quadrant, i.e., where the phase shift
|            |     | ○        | ○     |           |           |           |     |
| ---------- | --- | -------- | ----- | --------- | --------- | --------- | --- |
| is between | −90 | and −180 | . The | following | model was | obtained. |     |
1.05
|     |     | G   | (s)=       |     | e −3.75s |     |     |
| --- | --- | --- | ---------- | --- | -------- | --- | --- |
|     |     | 4b  | (1+2.39s)2 |     |          |     |     |
Figure 2.12 shows the step responses of the true process model and
(s),
| G   | as well | as the Nyquist | curves | of  | the transfer | functions. |     |
| --- | ------- | -------------- | ------ | --- | ------------ | ---------- | --- |
4b
| Modelsfor | IntegratingSystems |     |     |     |     |     |     |
| --------- | ------------------ | --- | --- | --- | --- | --- | --- |
There are some process control systems where the dynamics contain
integration or very long time constants. Such systems will not reach
asteady state under open-loop conditions. They aresometimes called
systems without self regulation. For PID tuning it is useful to treat
| such systems |           | separately. |     |     |     |     |     |
| ------------ | --------- | ----------- | --- | --- | --- | --- | --- |
| Impulse      | Responses |             |     |     |     |     |     |
For a system with integral action a steady state will not be achieved
when the input signal is a step, since the output will asymptotically
changeataconstantrate.Therewillbe,however,asteadystatewhen
theinputisanimpulse.Todeterminethedynamicswecan,therefore,
apply a short pulse tothe process. After normalizing the response by
dividing with the pulse area, we then get a step response that can

22 Chapter 2 ProcessModels
be modeled using the methods we have just discussed. The transfer
function of a system with integral action is then obtained simply by
multiplying the transfer function by 1/s. We illustrate the procedure
with an example.
EXAMPLE 2.6
Assumethatasquarepulsewithunitheightanddurationτhasbeen
applied to a process and that the model
K
G (s)= e −sL
1 1+sT
has been fitted to the response as described in Example 2.2. The
transfer function of the process is then
1 K
G(s)= G (s)= e −sL
sτ 1 sτ(1+sT)
Step Responses
Models based on step responses canalso beapplied toprocesses with
integral action. One possibility is to calculate the derivative of the
step response and apply the impulse response method that was just
discussed.
The two-parameter model
a
G(s)= e −sL
sL
that was used to model stable processes previously in this section
can also be applied to integrating processes. This model gives a bad
description ofstableprocessesathighfrequencies, butforintegrating
processes the low frequency behavior is well captured by the model.
A more sophisticated model that gives a better approximation at
higher frequencies is given by the transfer function
K
G(s)= e −sL (2.14)
s(1+sT)
The model is characterized by three parameters: the velocity gain K,
the time constant T, and the dead time L. The step response of the
model (2.14) is
(cid:2) (cid:2) (cid:3)(cid:3)
s(t)= K t− L−T 1−e −(t−L)/T (2.15)
The gain K and the average residence time T = L + T can be
ar
determined graphically as shown in Figure 2.13.

|     |     |     | 2.4 | StepResponse | Methods | 23  |
| --- | --- | --- | --- | ------------ | ------- | --- |
K(L+T)
L+T
| Figure   | 2.13 Graphicaldeterminationofathree-parametermodel |              |          |       |               |     |
| -------- | -------------------------------------------------- | ------------ | -------- | ----- | ------------- | --- |
| for an   | integratingprocess.                                |              |          |       |               |     |
| The dead | time L                                             | and the time | constant | T can | be determined | by  |
fitting Equation (2.15) to one point of the step response. A suitable
point is
|     |     | s(L+T)= | KTe | −1  |     |     |
| --- | --- | ------- | --- | --- | --- | --- |
which gives
s(L+T)
|     |     | T = |     | e1  |     |     |
| --- | --- | --- | --- | --- | --- | --- |
K
| Modelsfor | OscillatorySystems |     |     |     |     |     |
| --------- | ------------------ | --- | --- | --- | --- | --- |
Oscillatory systems with step responses, as shown in Figures 2.5B
and D, can be crudely approximated by the two-parameter model
(2.6),
but this model will not capture the oscillations. None of the
three- or four-parameter models presented above is suitable either. A
three-parameter model that describes the oscillations is given by the
transfer function
Kω2
|     |     | G(s)= |     |     |     | (2.16) |
| --- | --- | ----- | --- | --- | --- | ------ |
s2+2ζωs+ω2
This model has three parameters: the static gain K, the natural
|           | ω,      |                  |     | ζ.               |     |        |
| --------- | ------- | ---------------- | --- | ---------------- | --- | ------ |
| frequency | and the | relative damping |     | These parameters |     | can be |
determined approximately from the step response as indicated in
Figure 2.14. The period of the oscillation T p and the decay ratio d
are first determined. Parametersωandζare related to T and d as
p
follows.
√
2π
|     | d= −2ζπ/ | 1−ζ2 |     | = (cid:7) |     |     |
| --- | -------- | ---- | --- | --------- | --- | --- |
|     | e        |      | T   | p         |     |     |
|     |          |      |     | ω 1−ζ2    |     |     |

24 Chapter 2 Process Models
T
p
a ad
K
Figure 2.14 Graphicaldeterminationofmathematicalmodelsfor
systemswithan oscillatory step response.
or
1 2π
ζ= (cid:7) ω= (cid:7) (2.17)
1+(2π/log d)2 T 1−ζ2
p
Atimedelaycanalsobeaddedtothemodel (2.16)anddetermined in
thesamewayasfortheprevious models, e.g.,bydrawing thetangent
of maximum slope or determining the time between the onset of the
step and the time the step response has reached a few percent of its
final value.
2.5 Methods of Moments
All average residence time was determined based on calculation of
an area. All other methods discussed in Section 2.4 were based on
evaluationofthestepresponseatsinglepointsonly.Suchmethodsare
quite sensitive to measurement noise. In this section we will discuss
methods that are based on integrals of the step response.
AreaMethods
We will first discuss a method that is based on area calculations.
Static gain K and average residence time T arefirst determined as
ar
in Figure 2.6. The area A under the step response up to time T is
1 ar
then determined. For a system having the transfer function
K
G(s)= e −sL
1+sT

2.5 Methods of Moments 25
we have
(cid:1)Tar (cid:1)T
A = s(t)dt= K(1−e −t/T)dt= KTe −1
1
0 0
The time constant is thus given by
eA
T = 1 (2.18)
K
The dead time is then given by
A eA
L=T −T = 0 − 1 (2.19)
ar K K
With this method parameters L and T are both determined from
computations of areas. The method is illustrated by the following
example.
EXAMPLE 2.7
The method based on area determination has been applied to the
process model (2.7). Static gain K is first determined from the sta-
tionary values to K =1. Area A is then determined to8.0 providing
0
the average residence time T = 8. Area A can be determined by
ar 1
integrating thestep response uptotime T to A =1.1.From Equa-
ar 1
tion (2.18),time T canbecalculated to T =3.0,and finally Equation
(2.19) gives L=5.0. To summarize, the method based on area deter-
mination gives the following three-parameter model
1
G (s)= e −5.0s
3d 1+3.0s
Figure 2.15 shows the step responses of the true process model and
G (s), as well as the Nyquist curves of the two transfer functions.
3d
Thesameidea caneasilybeapplied toasystem withthetransfer
function
K
G(s)= e −sL (2.20)
(1+sT)2
Parameters K and residence time T are determined as before. In
ar
this case we have
T = L+2T
ar
The area A under the step response up to time T is then
1 ar
determined. For a system having transfer function (2.20) we have
(cid:1)Tar (cid:1)2T (cid:5) (cid:6)
t
A = s(t)dt= K 1−e −t/T − e −t/T dt=4KTe −2
1
T
0 0

| 26 Chapter |     | 2 ProcessModels |     |     |     |     |     |     |
| ---------- | --- | --------------- | --- | --- | --- | --- | --- | --- |
| 1          |     |                 |     |     | 1   |     |     |     |
x
x
Im0
x
x
xx
| 0   |     |     |     |     | –1  |     |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| 0   |     | 10  |     | 20  | –1  |     | 0   | 1   |
Re
| Figure                                              | 2.15 | Step responses |     | and Nyquist | curves | of  | the process |     |
| --------------------------------------------------- | ---- | -------------- | --- | ----------- | ------ | --- | ----------- | --- |
| G(s)=1/(s+1)8(solidline)andthethree-parametermodelG |      |                |     |             |        |     | (s)         |     |
3d
| (dashed  | line).   |         |       |      |     |     |     |        |
| -------- | -------- | ------- | ----- | ---- | --- | --- | --- | ------ |
| The time | constant | is thus | given | by   |     |     |     |        |
|          |          |         |       | A e2 |     |     |     |        |
|          |          |         |       | = 1  |     |     |     | (2.21) |
T
4K
| and the | dead | time is |     |     |       |     |     |        |
| ------- | ---- | ------- | --- | --- | ----- | --- | --- | ------ |
|         |      |         |     | A   | A e2  |     |     |        |
|         |      | L =T    | −2T | =   | 0 − 1 |     |     | (2.22) |
ar
|     |     |     |     | K   | 2K  |     |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
The following example illustrates the properties of the method.
| EXAMPLE | 2.8 |     |     |     |     |     |     |     |
| ------- | --- | --- | --- | --- | --- | --- | --- | --- |
The three-parameter model (2.20) has been fitted to the process
(2.7)
| model | using | the method |     | of area | determination. |     | Static gain | K   |
| ----- | ----- | ---------- | --- | ------- | -------------- | --- | ----------- | --- |
is determined from the stationary values to K = 1. The area A is
0
8.0, which gives the average residence time T = 8.0. Furthermore
ar
|          |      |                  |     | (2.21) |            | =   |               |     |
| -------- | ---- | ---------------- | --- | ------ | ---------- | --- | ------------- | --- |
| the area | A is | 1.1 and Equation |     |        | then gives | T   | 2.0. Equation |     |
1
| (2.22) finally |     | gives L=4.0 | and  | the model | becomes |     |     |     |
| -------------- | --- | ----------- | ---- | --------- | ------- | --- | --- | --- |
|                |     |             | (s)= | 1         | −4.0s   |     |     |     |
|                |     | G           |      |           | e       |     |     |     |
|                |     |             | 3e   | (1+2.0s)2 |         |     |     |     |
Figure 2.16 shows the step responses of the true process model and
(s),
G as well as the Nyquist curves of the two transfer functions.
3e
The methods based on area determination are less sensitive to
high-frequency disturbances than the previous methods, where the
model is determined from only a few values of the step response. On
theotherhand,theyaremoresensitive tolow-frequencydisturbances
| such as | a change | in static | load. |     |     |     |     |     |
| ------- | -------- | --------- | ----- | --- | --- | --- | --- | --- |

|     |     |     |     |     | 2.5 Methods | of  | Moments | 27  |
| --- | --- | --- | --- | --- | ----------- | --- | ------- | --- |
| 1   |     |     |     |     | 1           |     |         |     |
x x
Im0
xx
xx
| 0   |     |     |     |     | –1  |     |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| 0   |     | 10  |     | 20  | –1  |     | 0   | 1   |
Re
| Figure  | 2.16   | Step responses |              | and Nyquist | curves              | of  | the process |     |
| ------- | ------ | -------------- | ------------ | ----------- | ------------------- | --- | ----------- | --- |
| G(s) =  | 1/(s   | + 1)8          | (solid line) | and         | the three-parameter |     | model       |     |
| (dashed | line). |                |              |             |                     |     |             |     |
G 3e
TheMethodofMoments
A drawback with the area methods is that they require a storage
of the step response. Area A cannot be computed until area A is
|     |     |     | 1   |     |     |     |     | 0   |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
determined. Therefore, some alternative methods that arealso based
| on integration     | will | be considered. |          |             |         |     |               |     |
| ------------------ | ---- | -------------- | -------- | ----------- | ------- | --- | ------------- | --- |
| h(t)               |      |                |          |             | G(s)    |     |               |     |
| Let                | be   | an impulse     | response |             | and     | the | corresponding |     |
| transfer function. |      | The functions  |          | are related | through |     |               |     |
(cid:1)∞
|     |     |     | G(s)= | −sth(t)dt |     |     |     |     |
| --- | --- | --- | ----- | --------- | --- | --- | --- | --- |
e
0
| Taking derivatives |     | with | respect | to s gives |     |     |     |     |
| ------------------ | --- | ---- | ------- | ---------- | --- | --- | --- | --- |
(cid:1)∞
dnG(s)
|     |     | =   | G (n)(s)=(−1)n |     | e −sttnh(t)dt |     |     |     |
| --- | --- | --- | -------------- | --- | ------------- | --- | --- | --- |
dsn
0
Hence,
(cid:1)∞
|     |     | G   | (n)(0)=(−1)n |     | tnh(t)dt |     |     | (2.23) |
| --- | --- | --- | ------------ | --- | -------- | --- | --- | ------ |
0
The values of the transfer function and its derivatives at s = 0 can
| thus be determined |           | from | integrals | of the | impulse | response. |     |     |
| ------------------ | --------- | ---- | --------- | ------ | ------- | --------- | --- | --- |
| The Average        | Residence |      | Time      |        |         |           |     |     |
The impulse response is positive for systems with monotone step re-
sponses. Itcan beinterpreted asthe density function of a probability

| 28 Chapter   |     | 2 ProcessModels  |     |     |          |     |     |
| ------------ | --- | ---------------- | --- | --- | -------- | --- | --- |
| distribution | if  | it is normalized |     | as  | follows: |     |     |
h(t)
f(t)=
(cid:4)∞
h(t)dt
0
f(t)dt
| The quantity |     |     | can then | be  | interpreted | as the probability | that |
| ------------ | --- | --- | -------- | --- | ----------- | ------------------ | ---- |
an impulse entering the system at time 0 will leave at time t. The
| average | residence | time | is then |     |     |     |     |
| ------- | --------- | ---- | ------- | --- | --- | --- | --- |
(cid:4)∞
|     |     |     | (cid:1)∞ |          |     | th(t)dt  |        |
| --- | --- | --- | -------- | -------- | --- | -------- | ------ |
|     |     |     | T =      | tf(t)dt= |     | 0        | (2.24) |
|     |     |     | ar       |          |     | (cid:4)∞ |        |
h(t)dt
0
0
Introduce
(cid:3)(t)=s(∞)−s(t)
s(t)
| where | is  | the unit | step | response. | Then |     |     |
| ----- | --- | -------- | ---- | --------- | ---- | --- | --- |
d(cid:3)(t)
=−h(t)
dt
| It follows | that |          |     |         |         |          |     |
| ---------- | ---- | -------- | --- | ------- | ------- | -------- | --- |
|            |      | (cid:1)∞ |     | (cid:8) | (cid:9) | (cid:1)∞ |     |
∞
|     |     | th(t)dt= |     | −t(cid:3)(t) |     | + (cid:3)(t)dt |     |
| --- | --- | -------- | --- | ------------ | --- | -------------- | --- |
0
|     |     | 0   |     |     |     | 0   |     |
| --- | --- | --- | --- | --- | --- | --- | --- |
The first term of the right-hand side is zero if (cid:3)(t) goes to zero at
t1+(cid:1)
least as fast as for large t. The average residence time can thus
| also be | written | as  |     |     |     |     |     |
| ------- | ------- | --- | --- | --- | --- | --- | --- |
(cid:4)∞
(s(∞)−s(t))dt
|          |                |     | T =  | 0           |      |     |     |
| -------- | -------------- | --- | ---- | ----------- | ---- | --- | --- |
|          |                |     | ar   |             | s(∞) |     |     |
| which is | the definition |     | used | previously. |      |     |     |
Equation (2.23) gives a convenient way to determine parameters
ofdifferentmodelsbycomputingthemoments.Thiswillbeillustrated
by some examples.
| A Three-Parameter |     |          | Model    |     |     |     |        |
| ----------------- | --- | -------- | -------- | --- | --- | --- | ------ |
| Consider          | the | transfer | function |     |     |     |        |
|                   |     |          |          |     | K   | −sL |        |
|                   |     |          | G(s)=    |     |     | e   | (2.25) |
1+sT
| It follows | that |     |     |     |     |     |     |
| ---------- | ---- | --- | --- | --- | --- | --- | --- |
(cid:1)∞
|     |     |     | =   | G(0)= |     | h(t)dt | (2.26) |
| --- | --- | --- | --- | ----- | --- | ------ | ------ |
K
0

|                   |     |                 |          |               | 2.5   | Methods of Moments | 29  |
| ----------------- | --- | --------------- | -------- | ------------- | ----- | ------------------ | --- |
| Taking logarithms |     | of              | Equation | (2.25)        | gives |                    |     |
|                   |     | logG(s)=logK    |          | −sL−log(1+sT) |       |                    |     |
| Differentiating   |     | this expression |          | gives         |       |                    |     |
|                   |     | G (cid:8)(s)    |          |               | T     |                    |     |
=−L−
|     |     | G(s)              |     | 1+sT       |         |     |     |
| --- | --- | ----------------- | --- | ---------- | ------- | --- | --- |
|     |     |                   |     | (cid:5)    | (cid:6) |     |     |
|     |     | (cid:8)(cid:8)(s) |     | (cid:8)(s) | 2       | T2  |     |
|     |     | G                 |     | G          |         |     |     |
|     |     |                   | −   |            | =       |     |     |
|     |     | G(s)              |     | G(s)       | (1+sT)2 |     |     |
Hence
(cid:4)∞
th(t)dt
(cid:8)(0)
G
|     |     | T =− |      | = L+T | = 0      |     |     |
| --- | --- | ---- | ---- | ----- | -------- | --- | --- |
|     |     | ar   | G(0) |       | (cid:4)∞ |     |     |
h(t)dt
|     |     |     |     |     | 0   |     | (2.27) |
| --- | --- | --- | --- | --- | --- | --- | ------ |
(cid:4)∞
t2h(t)dt
(cid:8)(cid:8)(0)
|     |     | =   | G    | −T  | = 0      | −T  |     |
| --- | --- | --- | ---- | --- | -------- | --- | --- |
|     |     | T2  |      | 2   | (cid:4)∞ | 2   |     |
|     |     |     | G(0) | a r |          | a r |     |
h(t)dt
0
Gain K is thus given by Equation (2.26) and average residence time
(2.27).
| T and | time constant |     | T by | Equation |     | The dead time | L can |
| ----- | ------------- | --- | ---- | -------- | --- | ------------- | ----- |
ar
| then be | computed | to  |     |     |     |     |     |
| ------- | -------- | --- | --- | --- | --- | --- | --- |
|         |          |     |     | L=  | −T  |     |     |
|         |          |     |     | T   | ar  |     |     |
It has thus been shown that the parameters of the model can be
obtained from the first two moments of the impulse response. We
| illustrate | the procedure |     | with  | an example. |     |     |     |
| ---------- | ------------- | --- | ----- | ----------- | --- | --- | --- |
| EXAMPLE    | 2.9           |     |       |             |     |     |     |
| Consider   | the process   |     | model |             |     |     |     |
|            |               |     | G(s)= |             | 1   |     |     |
(s+1)8
| The first  | two derivatives |              | with   | respect | to s               | become               |     |
| ---------- | --------------- | ------------ | ------ | ------- | ------------------ | -------------------- | --- |
|            |                 | (cid:8)(s)=− |        | 8       | (cid:8)(cid:8)(s)= | 72                   |     |
|            | G               |              |        |         | G                  |                      |     |
|            |                 |              | (s+1)9 |         |                    | (s+1)10              |     |
|            |                 | (cid:8)(0)   |        |         | (cid:8)(cid:8)(0)  |                      |     |
| Hence G(0) | =               | 1, G         | = −8,  | and     | G =                | 72. Equations (2.26) | and |
| (2.27) now | give            |              |        |         |                    |                      |     |
=1
K
|     |     |     | T   | =8  |     |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- |
ar
|     |     |     | T2  | =72−64=8 |     |     |     |
| --- | --- | --- | --- | -------- | --- | --- | --- |

| 30 Chapter |     | 2 ProcessModels |     |     |     |     |     |     |
| ---------- | --- | --------------- | --- | --- | --- | --- | --- | --- |
|            |     | √               |     |     |     | √   |     |     |
We thus find T =2 2(cid:9)2.8 and L =8−2 2(cid:9)5.2. This result can
| becomparedwiththeprevious |                 |         |          | methods   | inExamples |             | 2.2and2.7. |     |
| ------------------------- | --------------- | ------- | -------- | --------- | ---------- | ----------- | ---------- | --- |
| Another                   | Three-Parameter |         |          | Model     |            |             |            |     |
| Themethod                 | of              | moments | willnow  | beapplied |            | todetermine | theparam-  |     |
| eters of                  | the transfer    |         | function |           |            |             |            |     |
K
|     |     |     | G(s)= |         | −sL |     |     |     |
| --- | --- | --- | ----- | ------- | --- | --- | --- | --- |
|     |     |     |       | (1+sT)2 | e   |     |     |     |
We have
|     |     | logG(s)=logK |     | −sL−2log(1+sT) |     |     |     |     |
| --- | --- | ------------ | --- | -------------- | --- | --- | --- | --- |
Hence
|     |     | G   | (cid:8)(s) |     | 2T  |     |     |     |
| --- | --- | --- | ---------- | --- | --- | --- | --- | --- |
=−L−
|     |     | G(s) |                   | 1+sT            |         |     |     |     |
| --- | --- | ---- | ----------------- | --------------- | ------- | --- | --- | --- |
|     |     |      |                   | (cid:5) (cid:6) |         |     |     |     |
|     |     |      | (cid:8)(cid:8)(s) | (cid:8)(s)      | 2 2T2   |     |     |     |
|     |     | G    |                   | G               |         |     |     |     |
|     |     |      | −                 |                 | =       |     |     |     |
|     |     | G(s) |                   | G(s)            | (1+sT)2 |     |     |     |
Hence
(cid:1)∞
|     |     | = G(0)= |     | h(t)dt |     |     |     |     |
| --- | --- | ------- | --- | ------ | --- | --- | --- | --- |
K
0
(cid:4)∞
th(t)dt
(cid:8)(0)
G
|     |     | T =− |      | = L+2T | = 0      |     |     |        |
| --- | --- | ---- | ---- | ------ | -------- | --- | --- | ------ |
|     |     | ar   | G(0) |        | (cid:4)∞ |     |     | (2.28) |
h(t)dt
0
(cid:4)∞
t2h(t)dt
(cid:8)(cid:8)(0)
|     |     | G     |     | 1       |          | 1   |     |     |
| --- | --- | ----- | --- | ------- | -------- | --- | --- | --- |
|     |     | T2 =  |     | − T 2 = | 0        | − T | 2   |     |
|     |     | 2G(0) |     | 2 a r   | (cid:4)∞ | 2   | a r |     |
h(t)dt
2
0
| We illustrate |     | the method | with | an example. |     |     |     |     |
| ------------- | --- | ---------- | ---- | ----------- | --- | --- | --- | --- |
2.10
EXAMPLE
Considertheprocessmodel(2.7).Itfollowsfromthepreviousexample
| G(0)   | =     | (cid:8)(0)                             | = −8, |       | (cid:8)(cid:8)(0) = |             |      | =    |
| ------ | ----- | -------------------------------------- | ----- | ----- | ------------------- | ----------- | ---- | ---- |
| that   | 1,    | G                                      |       | and G |                     | 72. We thus | find | K 1, |
| T =8,T | =2and | L=4.Thisisthesamemodelastheoneobtained |       |       |                     |             |      |      |
ar
| in Example  | 2.8. |         |     |     |     |     |     |     |
| ----------- | ---- | ------- | --- | --- | --- | --- | --- | --- |
| Other Input |      | Signals |     |     |     |     |     |     |
From a practical point of view it is a drawback to have methods that
require special input signals. The method of moments can be applied
| to any signal |     | provided | that | the system | is initially | at  | rest. |     |
| ------------- | --- | -------- | ---- | ---------- | ------------ | --- | ----- | --- |

|     |     |     | 2.5 | Methods of | Moments | 31  |
| --- | --- | --- | --- | ---------- | ------- | --- |
LetU(s)andY(s)betheLaplacetransformsofanarbitraryinput
andthecorresponding output, respectively. Takingderivatives weget
|     | Y(s)= G(s)U(s)                              |     |                              |                   |     |     |
| --- | ------------------------------------------- | --- | ---------------------------- | ----------------- | --- | --- |
|     | (cid:8)(s)= (cid:8)(s)U(s)+G(s)U            |     | (cid:8)(s)                   |                   |     |     |
|     | Y G                                         |     |                              |                   |     |     |
|     | (cid:8)(cid:8)(s)= (cid:8)(cid:8)(s)U(s)+2G |     | (cid:8)(s)U (cid:8)(s)+G(s)U | (cid:8)(cid:8)(s) |     |     |
|     | Y G                                         |     |                              |                   |     |     |
etc.
Hence,
|     | Y(0)= G(0)U(0)                   |     |            |     |     |     |
| --- | -------------------------------- | --- | ---------- | --- | --- | --- |
|     | (cid:8)(0)= (cid:8)(0)U(0)+G(0)U |     | (cid:8)(0) |     |     |     |
|     | Y G                              |     |            |     |     |     |
(2.29)
|     | Y (cid:8)(cid:8)(0)= G (cid:8)(cid:8)(0)U(0)+2G |     | (cid:8)(0)U (cid:8)(0)+G(0)U | (cid:8)(cid:8)(0) |     |     |
| --- | ----------------------------------------------- | --- | ---------------------------- | ----------------- | --- | --- |
etc.
G(0)and
| Thetransfer | function |     | its derivatives | can thus | be calculated |     |
| ----------- | -------- | --- | --------------- | -------- | ------------- | --- |
from experiments with arbitrary inputs by calculating the following
| moments | of the input and | output |     |     |     |     |
| ------- | ---------------- | ------ | --- | --- | --- | --- |
(cid:1)∞
(n)(0)=(−1)n
|     | U   |     | tnu(t)dt |     |     |     |
| --- | --- | --- | -------- | --- | --- | --- |
0
(cid:1)∞
|     |     | (n)(0)=(−1)n | tny(t)dt |     |     |     |
| --- | --- | ------------ | -------- | --- | --- | --- |
Y
0
(2.29).
| and | using Equation |     |     |     |     |     |
| --- | -------------- | --- | --- | --- | --- | --- |
By using these formulas it is possible to calculate G (n)(0) for any
| signals | for which the moments |     |     |     |     |     |
| ------- | --------------------- | --- | --- | --- | --- | --- |
(cid:1)∞
u = tnu(t)dt
n
0
and
(cid:1)∞
y = tny(t)dt
n
0
exist. This means that the signals must decay sufficiently fast.
A typical case where the method can be used is when an exper-
iment is performed in a closed loop with a pulse-like perturbation
| signal | on the process input. |     |     |     |     |     |
| ------ | --------------------- | --- | --- | --- | --- | --- |

| 32 Chapter |     | 2 ProcessModels |     |     |     |     |     |
| ---------- | --- | --------------- | --- | --- | --- | --- | --- |
WeightedMoments
The method just discussed cannot be used if the signals do not go
to zero or, equivalently, to a priori known mean values that can be
subtracted in the calculations of moments, because the moments will
then be infinite. There is, however, a simple modification that can
be used in this case. It follows from the definition of the Laplace
| transform | that |     |     |     |     |     |     |
| --------- | ---- | --- | --- | --- | --- | --- | --- |
(cid:1)∞
dnY(s)
|     |     | (n)(s)= |     | =(−1)n |     | −sttny(t)dt |     |
| --- | --- | ------- | --- | ------ | --- | ----------- | --- |
|     |     | Y       |     |        |     | e           |     |
dsn
0
| The weighted |     | moments |     |     |     |     |     |
| ------------ | --- | ------- | --- | --- | --- | --- | --- |
(cid:1)∞
|     |     | =   |     | −αty(t)dt=(−1)nY |     | (n)(α) |     |
| --- | --- | --- | --- | ---------------- | --- | ------ | --- |
|     |     | y   | tne |                  |     |        |     |
n
0
|     |     |     | y(t) |     |     | αt  |     |
| --- | --- | --- | ---- | --- | --- | --- | --- |
will exist provided that does not grow faster than e for large
t. By computing y and the analogously defined moment u , we can
|                   |          | n    |           |          |          |                | n   |
| ----------------- | -------- | ---- | --------- | -------- | -------- | -------------- | --- |
| compute           | Y (n)(α) | and  | U (n)(α), | and      | thus     | also G (n)(α). |     |
| A Three-Parameter |          |      | Model     |          |          |                |     |
| Consider          | a system | with | the       | transfer | function |                |     |
K
|     |     |     | G(s)= |     |     | −sL | (2.30) |
| --- | --- | --- | ----- | --- | --- | --- | ------ |
e
1+sT
We have
|     |     | logG(s)=logK |     |     | −sL−log(1+sT) |     |     |
| --- | --- | ------------ | --- | --- | ------------- | --- | --- |
Hence
(cid:8)(s)
|     |     | G   |     |     | T   |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- |
=−L−
|         |     | G(s)    |                   |                   | 1+sT    |              |        |
| ------- | --- | ------- | ----------------- | ----------------- | ------- | ------------ | ------ |
|         |     |         |                   | (cid:5)           | (cid:6) |              |        |
|         |     | G       | (cid:8)(cid:8)(s) | G (cid:8)(s)      | 2       | T2           |        |
|         |     |         | −                 |                   | =       |              |        |
|         |     | G(s)    |                   | G(s)              |         | (1+sT)2      |        |
| Thus we | get |         |                   |                   |         |              |        |
|         |     |         |                   |                   | (cid:5) | (cid:6)      |        |
|         |     |         |                   | (cid:8)(cid:8)(α) |         | (cid:8)(α) 2 |        |
|         |     | T2      |                   | G                 |         | G            |        |
|         |     |         |                   | =                 | −       | = a2         | (2.31) |
|         |     | (1+αT)2 |                   | G(α)              |         | G(α)         |        |
Hence,
a
T =
1−αa
(2.32)
(cid:8)(α)
G
|     |     |     |     | L=− | −a  |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- |
G(α)

2.5 Methods of Moments 33
The average residence time thus becomes
G (cid:8)(α) αa2
T = L+T =− +
ar G(α) 1−αa
Furthermore the static gain is given by
K =(1+αT)G(α)e αL (2.33)
The formulas are illustrated by an example.
EXAMPLE 2.11
Consider a system with the transfer function
1
G(s)=
(s+1)8
We have
1 −8 72
G(α)= G (cid:8)(α)= G (cid:8)(cid:8)(α)=
(1+α)8 (1+α)9 (1+α)10
Computing the derivatives at the origin from the first terms in the
Taylor series expansion gives
1 8α 1+9α
G(0)(cid:9) + =
(1+α)8 (1+α)9 (1+α)9
8 72α 8(1+10α)
G (cid:8)(0)(cid:9)− − =−
(1+α)9 (1+α)10 (1+α)10
The estimate of the average residence time becomes
G (cid:8)(0) 8(1+10α) 8(1+10α)
Tˆ =− (cid:9) =
ar G(0) (1+α)(1+9α) 1+10α+9α2
From these expressions it follows that αmust be small in order to
give reasonably good approximations. To discuss the values ofα,it is
reasonabletonormalizeandconsiderαT .Inthiscase,T =8.With
ar ar
αT = 1 we get G(0) = 0.74, G (cid:8)(0) = −5.54, and Tˆ = 7.53. With
ar ar
αT = 0.5 we get G(0)= 0.91, G (cid:8)(0)= −7.1, and Tˆ = 7.83, giving
ar ar
errors in the range of 10%. With αT = 0.2 we get G(0) = 0.98,
ar
G (cid:8)(0)=−7.81, and Tˆ =7.96.
ar
It follows from Equation (2.31) that
(cid:10) √
72 64 2 2
a= − =
(1+α)2 (1+α)2 1+α

| 34         | Chapter 2 | Process   | Models |            |      |     |     |
| ---------- | --------- | --------- | ------ | ---------- | ---- | --- | --- |
| It follows | from      | Equations | (2.32) | and (2.33) | that |     |     |
√
2 2
|     | T = |        | √   |     |     |     |     |
| --- | --- | ------ | --- | --- | --- | --- | --- |
|     |     | 1+(1−2 | 2)α |     |     |     |     |
√
8−2
2
L=
1+α
|             |           |               | 1       |      |      | √         |     |
| ----------- | --------- | ------------- | ------- | ---- | ---- | --------- | --- |
|             | =         |               |         | √    | (8−2 | 2)α/(1+α) |     |
|             | K         |               |         |      | e    |           |     |
|             |           | (1+α)7(1+(1−2 |         | 2)α) |      |           |     |
| The average | residence | time          | becomes |      |      |           |     |
√
|         |           |             |                     | 1+(2−2 |          | 2)α       |             |
| ------- | --------- | ----------- | ------------------- | ------ | -------- | --------- | ----------- |
|         | Tˆ =      | T + L=8     |                     | √      |          | √         |             |
|         | ar        |             | 1+(2−2              |        | 2)α+(1−2 |           | 2)α2        |
| With αT | =         | 1, 0.5, and | 0.2,                | we get | the      | estimates | Tˆ = 8.26,  |
|         | ar        |             |                     |        |          |           | ar          |
| Tˆ =    |           | Tˆ =        |                     |        |          |           |             |
| ar      | 8.06, and | ar          | 8.01, respectively. |        | This     | method    | of estimat- |
ing the average residence time gives slightly better results than the
| extrapolation | method. |     |     |     |     |     |     |
| ------------- | ------- | --- | --- | --- | --- | --- | --- |
Theexampleshowsthatwecanobtainreasonableestimatesofthe
model parameters and the average residence time by using weighted
moments. It also seems reasonable to choose parameter α so that
αT
ar is in the range of 0.2 to 1. The best results are obtained for
α.
a small value of There is, however, an advantage in using larger
values ofαbecause there isthen aless risk for disturbances to enter
the system.
| 2.6 | Frequency |     | Responses |     |     |     |     |
| --- | --------- | --- | --------- | --- | --- | --- | --- |
Twomethods fordetermining interesting points ontheNyquist curve
are presented below. Both are based on the idea of using feedback to
| generate | sinusoids | having | the appropriate |     | frequency. |     |     |
| -------- | --------- | ------ | --------------- | --- | ---------- | --- | --- |
TheZiegler-NicholsFrequencyResponseMethod
Ziegler and Nichols have provided a method for determining the ulti-
| matepointontheNyquistcurveexperimentally. |     |     |     |     |     | Themethodisbased |     |
| ----------------------------------------- | --- | --- | --- | --- | --- | ---------------- | --- |
on the observation that many systems can be made unstable under
proportionalfeedbackbychoosingsufficientlyhighgaininthepropor-
| tionalfeedback |     | (seeFigure2.17).Assumethatthegainisadjustedso |     |     |     |     |     |
| -------------- | --- | --------------------------------------------- | --- | --- | --- | --- | --- |
that the process is at the stability boundary. The control signal and
| theprocessoutputarethensinusoidswithaphaseshiftof−180 |     |     |     |     |     |     | ○ (see |
| ----------------------------------------------------- | --- | --- | --- | --- | --- | --- | ------ |

|     |     |     |     |     | 2.6 | Frequency | Responses | 35  |
| --- | --- | --- | --- | --- | --- | --------- | --------- | --- |
=0.5
K
|     | y   |     |     | y   |     |     |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
sp
1
0
| 0   |     | 5   |     | 10  |     | 15  |     | 20  |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
=2.0
K
y
y
sp
1
0
| 0   |     | 5   |     | 10  |     | 15  |     | 20  |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
=2.5
K
y
y
sp
1
−1
| 0   |     | 5   |     | 10  |     | 15  |     | 20  |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
Figure 2.17 Setpoint y and process output y for a closed-loop
sp
systemwithproportional feedback.The figure showsresponses for
| three | valuesof | controller | gain | K.  |     |     |     |     |
| ----- | -------- | ---------- | ---- | --- | --- | --- | --- | --- |
Figure 2.18). Because of the proportional feedback they are related
by
u=−Ky
For simplicity it has been assumed that the setpoint is y =0. Since
sp
| thegainaroundtheloopmustbeunity |     |     |     |     | tomaintain |     | anoscillation, | we  |
| ------------------------------- | --- | --- | --- | --- | ---------- | --- | -------------- | --- |
have
|     |     |     |     | G(iω | )=−1 |     |     |     |
| --- | --- | --- | --- | ---- | ---- | --- | --- | --- |
|     |     |     | K   | u u  |      |     |     |     |
wherethegain,whichbringsthesystemtothestabilitylimit,iscalled
|     |     |     |     | Controller |     | Process |     |     |
| --- | --- | --- | --- | ---------- | --- | ------- | --- | --- |
|     | y   |     | e   |            | u   |         | y   |     |
  sp Σ
|     |     |     |     | K   |     |   G   (s) |     |     |
| --- | --- | --- | --- | --- | --- | --------- | --- | --- |
−
1
| Figure | 2.18      | Blockdiagramofaclosed-loopsystemunderpropor- |     |     |     |     |     |     |
| ------ | --------- | -------------------------------------------- | --- | --- | --- | --- | --- | --- |
| tional | feedback. |                                              |     |     |     |     |     |     |

| 36 Chapter | 2   | ProcessModels |     |     |     |     |     |     |     |
| ---------- | --- | ------------- | --- | --- | --- | --- | --- | --- | --- |
κand
| Table | 2.1 | Relations | between | gain | ratio |     | normalized | dead |     |
| ----- | --- | --------- | ------- | ---- | ----- | --- | ---------- | ---- | --- |
timeτfor processes with the transfer functions G(s)=1/(s+1)n.
|     |     | n   | 2    | 3    |      | 4   | 8    |     |     |
| --- | --- | --- | ---- | ---- | ---- | --- | ---- | --- | --- |
|     |     | τ   | 0.15 | 0.25 | 0.35 |     | 0.55 |     |     |
κ
|              |      |     | 0          | 0.125 | 0.25 |       | 0.53     |      |     |
| ------------ | ---- | --- | ---------- | ----- | ---- | ----- | -------- | ---- | --- |
|              |      | (K  | ).         |       |      |       |          |      |     |
| the ultimate | gain |     | It follows | from  | the  | above | equation | that |     |
u
1
|     |     |     |     | G(iω )=− |     |     |     |     | (2.34) |
| --- | --- | --- | --- | -------- | --- | --- | --- | --- | ------ |
u
K
u
Several design methods based only on the knowledge of G(iω ) are
u
given in Chapter 4. It is convenient to introduce the gain ratio,
|     |     |     |     | (cid:11)      | (cid:11)   |     |     |     |        |
| --- | --- | --- | --- | ------------- | ---------- | --- | --- | --- | ------ |
|     |     |     |     | (cid:11) G(iω | )(cid:11)  |     |     |     |        |
|     |     |     |     | κ= (cid:11)   | u (cid:11) |     |     |     | (2.35) |
|     |     |     |     | (cid:11)      | (cid:11)   |     |     |     |        |
G(0)
i.e.,thegainattheultimatefrequencydividedbythestaticgain.This
parameter is an indicator of how difficult it is to control the process.
Processes with a smallκare easy to control. The difficulty increases
κ.
with increasing
| Parameterκis |     | also | related | tothe | normalized |     | dead | timeτ, | which |
| ------------ | --- | ---- | ------- | ----- | ---------- | --- | ---- | ------ | ----- |
wasdefinedinEquation(2.9).Forprocessesdescribedbythetransfer
(2.8) parametersτandκare
| function |     |     |     |     | related | in  | the following |     | way: |
| -------- | --- | --- | --- | --- | ------- | --- | ------------- | --- | ---- |
(cid:7)
|               |     |          | π−arctan               |          | 1/κ2−1 |         |               |        |     |
| ------------- | --- | -------- | ---------------------- | -------- | ------ | ------- | ------------- | ------ | --- |
|               |     | τ=       |                        | (cid:7)  |        | (cid:7) |               |        |     |
|               |     | π−arctan |                        | 1/κ2−1+  |        | 1/κ2−1  |               |        |     |
|               |     |          |                        | givesτ=0 |        |         | κ=            | andτ=1 |     |
| This relation | is  | close    | to linear,             | it       |        | for     | 0             |        | for |
| κ=1.Forsmall  |     |          | ofκitcanbeapproximated |          |        |         | byτ=1.6κ.This |        |     |
values
| is illustrated | in   | the following |     | example. |     |     |     |     |     |
| -------------- | ---- | ------------- | --- | -------- | --- | --- | --- | --- | --- |
| EXAMPLE        | 2.12 |               |     |          |     |     |     |     |     |
To illustrate the relation between the parameters κ and τ, we give
| their values | for | systems | with | the transfer |     | functions |     |     |     |
| ------------ | --- | ------- | ---- | ------------ | --- | --------- | --- | --- | --- |
1
G(s)=
(s+1)n
The results are presented in Table 2.1. For small values of n, bothκ
andτaresmall.
|     |     | These | processes | areeasy |     | tocontrol. | Forlargevalues |     |     |
| --- | --- | ----- | --------- | ------- | --- | ---------- | -------------- | --- | --- |
n,bothκandτapproach1.Theseprocesses
| of  |     |     |     |     |     | aredifficulttocontrol. |     |     |     |
| --- | --- | --- | --- | --- | --- | ---------------------- | --- | --- | --- |
The Ziegler-Nichols frequency response method has some advan-
tages. It is based on a simple experiment, and the process itself is

|     |     |     |     |       | 2.6 | Frequency | Responses | 37  |
| --- | --- | --- | --- | ----- | --- | --------- | --------- | --- |
|     |     |     |     | Relay |     | Process   |           |     |
y
|     | sp  |     | e   |     |     | u         | y   |     |
| --- | --- | --- | --- | --- | --- | --------- | --- | --- |
|     |     | Σ   |     |     |     |   G   (s) |     |     |
−
1
| Figure | 2.19 | Block | diagram | of  | aprocessunder |     | relay feedback. |     |
| ------ | ---- | ----- | ------- | --- | ------------- | --- | --------------- | --- |
used to find the ultimate frequency. It is, however, difficult to auto-
mate this experiment or perform it in such a way that the amplitude
oftheoscillation iskeptundercontrol. Operating theprocessnearin-
stability is also dangerous and may need management authorization
in an industrial plant. It is difficult to use this method for automatic
tuning.Analternativemethodforautomaticdetermination ofspecific
| points on | the | Nyquist | curve | is suggested |     | below. |     |     |
| --------- | --- | ------- | ----- | ------------ | --- | ------ | --- | --- |
RelayFeedback
| Analternativemethodtodetermineinteresting |     |     |     |     |     | pointsontheNyquist |     |     |
| ----------------------------------------- | --- | --- | --- | --- | --- | ------------------ | --- | --- |
curve is based on the observation that the appropriate oscillation
can be generated by relay feedback. The system is thus connected
as shown in Figure 2.19. For many systems there will then be an
oscillation (as shown in Figure 2.20) where the control signal is a
squarewaveandtheprocess output isclose toasinusoid. Notice that
| the process | input | and | output | have | opposite | phase. |     |     |
| ----------- | ----- | --- | ------ | ---- | -------- | ------ | --- | --- |
Toexplainhowthesystemworks,assumethattherelayoutputis
expanded in a Fourier series and that the process attenuates higher
0 y
−2
| 0   |     | 10  |     | 20  |     | 30  |     | 40  |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
1
u
−1
| 0      |       | 10        |        | 20    |         | 30     |         | 40     |
| ------ | ----- | --------- | ------ | ----- | ------- | ------ | ------- | ------ |
| Figure | 2.20  | Relay     | output | u and | process | output | y for a | system |
| under  | relay | feedback. |        |       |         |        |         |        |

| 38 Chapter |     | 2 ProcessModels |     |     |     |     |     |
| ---------- | --- | --------------- | --- | --- | --- | --- | --- |
harmonics effectively. It is then sufficient to consider the first har-
monic component of the input only. The input and the output then
have opposite phase, which means that the frequency of the oscilla-
tion is the ultimate frequency. If d is the relay amplitude, the first
4d/π.
| harmonic   | of the | square      | wave   | has amplitude |         | Let a be | the am- |
| ---------- | ------ | ----------- | ------ | ------------- | ------- | -------- | ------- |
| plitude of | the    | oscillation | in the | process       | output. | Then,    |         |
πa
|     |     |     | G(iω | )=− |     |     | (2.36) |
| --- | --- | --- | ---- | --- | --- | --- | ------ |
u
4d
Notice that the relay experiment is easily automated. Since the am-
plitude of the oscillation isproportional tothe relayoutput, it is easy
to control it by adjusting the relay output. Also notice in Figure 2.20
that a stable oscillation is established very quickly. The amplitude
and the period can be determined after about 20 s only, in spite of
the fact that the system is started so far from the equilibrium that it
takes about 8 storeach the correctlevel. Theaverage residence time
of the system is 12 s, which means that it would take about 40 s for
| a step response |          | to reach | steady   | state. |     |     |     |
| --------------- | -------- | -------- | -------- | ------ | --- | --- | --- |
| Describing      | Function |          | Analysis |        |     |     |     |
The intuitive discussion about relay oscillations can be dealt with
more quantitatively using a technique called the describing function
method. This is an approximate method that can be used to deter-
mine if there will be an oscillation in a nonlinear feedback system
that is composed of a linear element and a static nonlinearity. To
determine conditions for oscillation, the nonlinear block is described
N(a),
| by a gain, |     | which | depends | on  | signal amplitude | a at | the in- |
| ---------- | --- | ----- | ------- | --- | ---------------- | ---- | ------- |
put of the nonlinearity. This gain, which describes how a sinusoid of
amplitude a propagates through the system, is called the describing
G(iω),thecondition
| function. | Iftheprocess |     | hasthetransfer |     | function |     |     |
| --------- | ------------ | --- | -------------- | --- | -------- | --- | --- |
 I m G(iω)
Re G(iω)
ω
Nyquist curve G(iω)
1
| Describing function |     |     | −   |     |     |     |     |
| ------------------- | --- | --- | --- | --- | --- | --- | --- |
N (a)
Figure 2.21 Determination of possible oscillations using the de-
| scribing | functionmethod. |     |     |     |     |     |     |
| -------- | --------------- | --- | --- | --- | --- | --- | --- |

|                 |     |        |              |     | 2.6 Frequency | Responses |     | 39     |
| --------------- | --- | ------ | ------------ | --- | ------------- | --------- | --- | ------ |
| for oscillation | is  | simply | given by     |     |               |           |     |        |
|                 |     |        | N(a)G(iω)=−1 |     |               |           |     | (2.37) |
Thisequationisobtainedbyrequiringthatasinewavewithfrequency
ωshould propagate around the feedback loop with the same ampli-
tude and phase. The equation gives two equations for determining a
andω,since
|     | N   | and G maybecomplex |     |     | numbers. Theequation |     |     | canbe |
| --- | --- | ------------------ | --- | --- | -------------------- | --- | --- | ----- |
solvedgraphically byplotting −1/N(a)intheNyquistdiagram (asin
| 2.21)together |     |      |             |     | G(iω)of |     |        |      |
| ------------- | --- | ---- | ----------- | --- | ------- | --- | ------ | ---- |
| Figure        |     | with | the Nyquist |     | curve   | the | linear | sys- |
tem. An oscillation may occur if there is an intersection between the
twocurves.Theamplitudeandthefrequencyoftheoscillationarethe
same as the parameters of the two curves at the intersection point.
Therefore, measuring theamplitude andtheperiod of theoscillation,
the position of one point of the Nyquist curve can be determined.
| The describing |     | function, | N(a), | for | a relay is given |     | by  |     |
| -------------- | --- | --------- | ----- | --- | ---------------- | --- | --- | --- |
4d
|     |     |     | N(a)= |     |     |     |     | (2.38) |
| --- | --- | --- | ----- | --- | --- | --- | --- | ------ |
πa
Since this function is real, an oscillation may occur if the Nyquist
curve intersects the negative real axis. This explains why the exper-
iment with relay feedback gives the point where the Nyquist curve
| intersects | the negative | real       | axis. |     |     |     |     |     |
| ---------- | ------------ | ---------- | ----- | --- | --- | --- | --- | --- |
| A Relay    | with         | Hysteresis |       |     |     |     |     |     |
There are advantages in having a relay with hysteresis instead of a
| purerelay.Withanordinary |     |     | relay,asmall |     | amountofnoise |     | canmake |     |
| ------------------------ | --- | --- | ------------ | --- | ------------- | --- | ------- | --- |
the relay switch randomly. By introducing hysteresis, the noise must
| belargerthanthehysteresis |     |     | widthtomaketherelayswitch.SeeFig- |     |     |     |     |     |
| ------------------------- | --- | --- | --------------------------------- | --- | --- | --- | --- | --- |
ure2.22.Thedescribing function approachwillbeusedtoinvestigate
theoscillations obtained. Thenegative inverse of thedescribing func-
y
d
u
ε
| Figure | 2.22 | Output | yfromarelay | withhysteresiswith |     |     | input | u.  |
| ------ | ---- | ------ | ----------- | ------------------ | --- | --- | ----- | --- |

| 40 Chapter | 2 ProcessModels |     |     |     |
| ---------- | --------------- | --- | --- | --- |
1
−
N(a)
Figure 2.23 The negative reciprocal of the describing function
N(a)for
a relay withhysteresis.
| tion of such | a relay is |      |               |        |
| ------------ | ---------- | ---- | ------------- | ------ |
|              |            | π√   | π(cid:1)      |        |
|              | −          | 1 =− | a2−(cid:1)2−i | (2.39) |
|              | N(a)       | 4d   | 4d            |        |
where d is the relay amplitude and (cid:1) is the hysteresis width. This
function can be represented as a straight line parallel to the real
| axis, in | the complex plane | (see Figure | 2.23). |     |
| -------- | ----------------- | ----------- | ------ | --- |
(cid:1)
By choosing the relation between and d, it is therefore possible
todetermine apoint ontheNyquist curvewithaspecified imaginary
part.SeveralpointsontheNyquistcurvecanbeobtainedbyrepeating
(cid:1)
the experiment with different relations between and d. It is easy to
control the amplitude of the limit cycle to a desired level by a proper
| choice of | the relay amplitude. |     |     |     |
| --------- | -------------------- | --- | --- | --- |
OtherUsesofRelayFeedback
A slight modification of the experiment shown in Figure 2.19 gives
other frequencies of interest. Figure 2.24 shows an experiment that
gives the frequency ω , i.e. the frequency where the process has a
90
○
phase lag of 90 . Notice that there are two different versions of the
experiment depending on the order in which the integrator and the
| relay are | connected.       |     |     |     |
| --------- | ---------------- | --- | --- | --- |
| Closed    | Loop Experiments |     |     |     |
Relayfeedbackcanalsobeappliedtoclosed-loop systems.Figure2.25
shows an experiment that can be used to determine the amplitude
marginon-line.LetG(cid:10)bethelooptransferfunction,i.e.,thecombined
transfer function of the controller and the process. The closed-loop

|     |     |     | 2.6 Frequency | Responses | 41  |
| --- | --- | --- | ------------- | --------- | --- |
|     | Σ   |     | 1             |           |     |
Process
s
−1
1
|     | Σ   |     |     | Process |     |
| --- | --- | --- | --- | ------- | --- |
s
−1
| Figure | 2.24 Usingrelayfeedbacktodeterminethefrequencyω |     |     |     | .   |
| ------ | ----------------------------------------------- | --- | --- | --- | --- |
90
| transfer function | is then |     |     |     |     |
| ----------------- | ------- | --- | --- | --- | --- |
G(cid:10) (s)
|     |     | (s)= |     |     | (2.40) |
| --- | --- | ---- | --- | --- | ------ |
G
|                                                      |     | cl 1+G(cid:10) | (s)  |     |         |
| ---------------------------------------------------- | --- | -------------- | ---- | --- | ------- |
| Theexperimentwithrelayfeedbackthengivesanoscillation |     |                |      |     | withthe |
|                                                      |     |                | (iω) | ○   |         |
frequency such that the phase lag of G cl is 180 . It then follows
fromEquation(2.40)thatthisisalsothefrequencywhere G(cid:10) (iω)has
○
| aphaselagof180 | ,i.e.,theultimatefrequency.Ifmisthemagnitude |     |     |     |     |
| -------------- | -------------------------------------------- | --- | --- | --- | --- |
of G at that frequency, we find that an estimate of the amplitude
cl
| margin of | the closed-loop | system is | given by |     |     |
| --------- | --------------- | --------- | -------- | --- | --- |
m
Aˆ =
m 1−m
Iftherelayhashysteresis,aconformalmappingargumentshowsthat
the experiment gives the frequency, where the loop transfer function
| Σ   |     | Σ   |            |         |     |
| --- | --- | --- | ---------- | ------- | --- |
|     |     |     | Controller | Process |     |

−1
−1
| Figure   | 2.25 Using     | relay feedback | to determine | the amplitude |     |
| -------- | -------------- | -------------- | ------------ | ------------- | --- |
| marginof | theclosed-loop | system.        |              |               |     |

| 42 Chapter |     | 2 ProcessModels |     |     |     |     |     |     |
| ---------- | --- | --------------- | --- | --- | --- | --- | --- | --- |
(iω)
   I    mG
l
−1
(iω)
   R    eG
|     |     |     | B   |     |     | l   |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
A
|            |          |             | G                           | (iω) |          |            |          |        |
| ---------- | -------- | ----------- | --------------------------- | ---- | -------- | ---------- | -------- | ------ |
|            |          |             |                             | l    |          |            |          |        |
| Figure     | 2.26     | Experiments |                             | with | relay    | feedback   | give the | points |
| where      | thecurve |             | G(cid:10) (iω)intersectsthe |      | circles. |            |          |        |
| intersects | part     | of the      | circle,                     |      |          |            |          |        |
|            |          |             | (cid:11)                    |      |          | (cid:11)   |          |        |
|            |          |             | (cid:11)                    |      |          | (cid:11)   |          |        |
|            |          |             | (cid:11)                    |      | 1        | (cid:11) 1 |          |        |
|            |          |             | (cid:11)G(cid:10) (iω)−1+i  |      |          | (cid:11) = |          |        |
|            |          |             |                             |      | 2a       | 2a         |          |        |
which is shown as curve A in in Figure 2.26. By introducing an
integrator in series with the relay, the frequency where G (iω) has
cl
a phase lag of 90 ○ is obtained. This occurs for loop transfer functions
| G(cid:10) with | the property |     |               |     |                  |     |     |     |
| -------------- | ------------ | --- | ------------- | --- | ---------------- | --- | --- | --- |
|                |              |     | G(cid:10)     |     |                  |     | π   |     |
|                |              |     | =argG(cid:10) |     | −arg(1+G(cid:10) |     | )=  |     |
arg 1+
|                  |     |     | G(cid:10)         |       |           |     | 2   |        |
| ---------------- | --- | --- | ----------------- | ----- | --------- | --- | --- | ------ |
| This corresponds |     | to  | the circle,       |       |           |     |     |        |
|                  |     |     | (cid:11)          |       | (cid:11)  |     |     |        |
|                  |     |     | (cid:11)          |       | (cid:11)  |     |     |        |
|                  |     |     |                   |       | 1(cid:11) | 1   |     |        |
|                  |     |     | (cid:11)          | (iω)+ | =         |     |     | (2.41) |
|                  |     |     | (cid:11)G(cid:10) |       | (cid:11)  |     |     |        |
|                  |     |     |                   |       | 2         | 2   |     |        |
which is shown as curve B in Figure 2.26. The experiment will thus
give the point where the loop transfer function G(cid:10) of the closed-loop
system intersects the circle given byEquation (2.41).Combining this
result with the result from the experiment in Figure 2.24, it is also
possible to approximately determine the maximum sensitivity M .
s
Many controllers use a two-degree-of-freedom configuration in-
stead of pure error feedback. This is discussed in Chapter 3. This
| means that     | the | control | law | is given | by    |         |                  |     |
| -------------- | --- | ------- | --- | -------- | ----- | ------- | ---------------- | --- |
|                |     | U(s)=   |     | (s)Y     | (s)−G | (s)Y(s) |                  |     |
|                |     |         | G   | ff sp    |       | fb      |                  |     |
| The experiment |     | shown   | in  | Figure   | 2.25  | must    | then be modified | by  |
/G
introducing a block withthe transfer function G fb ff in series with
the relay.
| It has | thus | been | demonstrated |     | that | several | of the | quantities |
| ------ | ---- | ---- | ------------ | --- | ---- | ------- | ------ | ---------- |
neededtomakeanassessmentofcontrolperformancecanbeobtained
| from experiments |     | with | relay | feedback. |     |     |     |     |
| ---------------- | --- | ---- | ----- | --------- | --- | --- | --- | --- |

|     |           |     |            | 2.7 | Parameter | Estimation | 43  |
| --- | --------- | --- | ---------- | --- | --------- | ---------- | --- |
| 2.7 | Parameter |     | Estimation |     |           |            |     |
A mathematical model of the process can also be obtained by fitting
theparametersofamodeltoexperimentaldata.Forexample,amodel
of the type given by Equation 2.8 can be obtained by adjusting the
parameters so that they match observed input/output data. The ad-
vantageofsuchanapproachisthatanytypeofinput/outputdatacan
be used. However, parameter estimation requires more computations
| than | the methods | discussed | previously. |     |     |     |     |
| ---- | ----------- | --------- | ----------- | --- | --- | --- | --- |
ParametricModels
Sincethecalculationswilltypicallybemadeusingadigitalcomputer,
theinput/output
|     |     | data | willtypically | besampled. |     | Itisthen convenient |     |
| --- | --- | ---- | ------------- | ---------- | --- | ------------------- | --- |
to operate with a discrete time model based on signals that are sam-
pledperiodically. Moreover, iftheexperimentaldataisalsocomputer-
generated, it is reasonable to assume that the input to the process is
constant between the sampling instants. Let the sampling period be
(2.8)canthen
| h.Assume |           | that time delay | L is less | than | h.Themodel |     |        |
| -------- | --------- | --------------- | --------- | ---- | ---------- | --- | ------ |
| be       | described | as              |           |      |            |     |        |
|          | y(kh)=    | ay(kh−h)+b      | u(kh−h)+b |      | u(kh−2h)   |     | (2.42) |
|          |           |                 | 1         |      | 2          |     |        |
where
|     |     |     | a= −h/T |     |     |     |     |
| --- | --- | --- | ------- | --- | --- | --- | --- |
e
|     |     |     | (cid:2)   |          | (cid:3) |     |     |
| --- | --- | --- | --------- | -------- | ------- | --- | --- |
|     |     |     | b = K 1−e | −(h−L)/T |         |     |     |
1
(cid:2) (cid:3)
|     |     |     | b = Ke −h/T | eL/T | −1  |     |     |
| --- | --- | --- | ----------- | ---- | --- | --- | --- |
2
|     | For arbitrary | time       | delays L,  | the model | becomes    | instead |        |
| --- | ------------- | ---------- | ---------- | --------- | ---------- | ------- | ------ |
|     | y(kh)=        | ay(kh−h)+b | u(kh−nh)+b |           | u(kh−nh−h) |         | (2.43) |
|     |               |            | 1          |           | 2          |         |        |
=
where parameters a, b 1 , and b 2 are given as above with n Ldivh
and τ= Lmodh replacing L. The model can be given a convenient
| representation |     | by introducing | a   | shift operator | q,  | defined by |     |
| -------------- | --- | -------------- | --- | -------------- | --- | ---------- | --- |
qy(kh)= y(kh+h)
(2.43)
| The | model | can             | then be written | as  |        |     |     |
| --- | ----- | --------------- | --------------- | --- | ------ | --- | --- |
|     |       | qn(q−a)y(kh)=(b |                 | q+b | )u(kh) |     |     |
1 2
Ifthecomplexvariable z(similartotheLaplacetransformvariables)
is introduced, the process can also be described by the pulse transfer
function:
z+b
b
|     |     |     | H(z)= | 1   | 2   |     | (2.44) |
| --- | --- | --- | ----- | --- | --- | --- | ------ |
zn(z−a)

| 44 Chapter | 2   | Process | Models |     |     |     |     |     |
| ---------- | --- | ------- | ------ | --- | --- | --- | --- | --- |
Notice that the transfer function is a ratio of two polynomials even if
| the corresponding |     | physical |     | process | has time | delays. |     |     |
| ----------------- | --- | -------- | --- | ------- | -------- | ------- | --- | --- |
The discussion can be extended to systems of higher order, and
input/output
| the result        | is then | an       |                  |            | relation   | of the   | form: |        |
| ----------------- | ------- | -------- | ---------------- | ---------- | ---------- | -------- | ----- | ------ |
|                   |         | y(kh)+a  | y(kh−h)+⋅⋅⋅+a    |            |            | y(kh−nh) |       |        |
|                   |         |          | 1                |            |            | n        |       |        |
|                   |         | = b      | u(kh−h)+⋅⋅⋅+b    |            | u(kh−nh)   |          |       |        |
|                   |         |          | 1                |            | n          |          |       |        |
| This equation     |         | can be   | written          | compactly  | as         |          |       |        |
|                   |         |          | A(q)y(kh)=       |            | B(q)u(kh)  |          |       | (2.45) |
| A(q)              |         | B(q)     |                  |            |            |          |       |        |
| where             | and     |          | are polynomials: |            |            |          |       |        |
|                   |         | A(q)=    | qn+a             | qn−1+⋅⋅⋅+a |            |          |       |        |
|                   |         |          |                  | 1          |            | n        |       |        |
|                   |         | B(q)=b   |                  | qn−1+b     | qn−2+⋅⋅⋅+b |          |       |        |
|                   |         |          | 1                |            | 2          |          | n     |        |
| The corresponding |         | transfer |                  | function   | is then    |          |       |        |
|                   |         |          | B(z)             | b zn−1+b   | zn−2+⋅⋅⋅+b |          |       |        |
|                   | H(z)=   |          | =                | 1          | 2          |          | n     |        |
|                   |         |          | A(z)             | zn+a       | zn−1+⋅⋅⋅+a |          |       |        |
|                   |         |          |                  |            | 1          |          | n     |        |
ParameterEstimation
There aremany waystoestimate theparameters of thediscrete time
| (Equation |     | 2.45). |          |        |     |             |        |        |
| --------- | --- | ------ | -------- | ------ | --- | ----------- | ------ | ------ |
| model     |     |        | A simple | method | is  | as follows. | Assume | that a |
sequence of input/output pairs ({u(kh),y(kh),k = 1,2,...,N}) have
been observed. The parameters can then be determined in such a
(2.45)fitsthe
| waythat | Equation |         |        | data    | as well | aspossible | in  | the least |
| ------- | -------- | ------- | ------ | ------- | ------- | ---------- | --- | --------- |
| squares | sense.   | The sum | of the | squares | of      | the errors | is  |           |
(cid:12)N
|     |     |     | V(θ)= |     | e2(kh) |     |     | (2.46) |
| --- | --- | --- | ----- | --- | ------ | --- | --- | ------ |
k=n+1
where
| e(kh+nh)=                               |     | A(q)y(kh)− |     | B(q)u(kh), |     | k=1,⋅⋅⋅,N−n |                 |     |
| --------------------------------------- | --- | ---------- | --- | ---------- | --- | ----------- | --------------- | --- |
| Noticethattheerrorislinearinparametersa |     |            |     |            |     |             | andb ofthemodel |     |
|                                         |     |            |     |            |     |             | i i             |     |
and that the sum of squares of the errors is a quadratic function.
This means that the minimum of the loss function can be computed
analytically. Rather than showing the solution to the optimization
problem, a convenient way of computing the parameters recursively
| is presented | below. |     |     |     |     |     |     |     |
| ------------ | ------ | --- | --- | --- | --- | --- | --- | --- |

2.7 Parameter Estimation 45
RecursiveComputations
Inatuningexperiment,anewinput/outputpairisnormallyobtained
in each sampling. It is then convenient to compute the parameter
estimates recursively. All parameters are grouped together in the
vector:
θ=(a a ...a b b ...b )T
1 2 n 1 2 n
Introduce the regression vector defined by
ϕ
k−1
=(−y(kh−h)...−y(kh−nh)u(kh−h)...u(kh−nh))T
The estimate can then be calculated recursively by
e k = y(kh)−ϕ k T −1 θ k−1 (2.47A)
P k = P k−1 − P 1 k + −1 ϕ ϕ k T k − − 1 1 ϕ P k k T − − 1 1 ϕ P k k − − 1 1 (2.47B)
θ k =θ k−1 +P k ϕ k−1 e k (2.47C)
Theseequationshavegoodphysicalinterpretations. Thenewestimate
θ is obtained by adding a correction term Pϕe to the old estimate
k
θ k−1 . The correction term is a product of three quantities: P,ϕ, and
e. The error e is the difference between the last measurement y(kh)
and the prediction ϕTθof this measurement based on old estimates.
Regression vector ϕcan be interpreted as the gradient of the error
with respect to the parameters. This vector tells how the scalar error
is distributed to give corrections in all parameters.
Equation (2.47B) may be interpreted as follows. Matrix P is
k
proportional to the covariance matrix of the estimates; the last term
in Equation (2.47B) is the reduction in uncertainty due to the last
measurement.
The equations have to be initialized. The initial value of parame-
ter vector θcan be chosen as the best initial guesses of the parame-
ters. The initial value of matrix P is typically chosen as the identity
matrix multiplied by a large number.
ComputerCode
Recursive least squares estimation is an essential part of many
schemes for automatic tuning. The following is a computer code that
implements the algorithm.
{The recursive least squares algorithm}
e=y
for i=1 to 2*n do e=e-ϕ[i]*θ[i]
{Compute estimator gain}
for i=1 to 2*n do

| 46  | Chapter 2 | ProcessModels |     |     |
| --- | --------- | ------------- | --- | --- |
begin
s=0
d=1
|     | for j=1 | to 2*n do |     |     |
| --- | ------- | --------- | --- | --- |
begin
s=s+P[i,j]*ϕ[j]
d=d+s*ϕ[j]
end
r[i]=s
end
| {Update | estimates} |                           |     |     |
| ------- | ---------- | ------------------------- | --- | --- |
|         | for i=1 to | 2*n do θ[i]=θ[i]+r[i]*e/d |     |     |
| {Update | matrix}    |                           |     |     |
P
|     | for i=1 to | 2*n do |     |     |
| --- | ---------- | ------ | --- | --- |
begin
|     | for j=i   | to 2*n do | P[i,j]=P[i,j]-r[i]*r[j]/d |     |
| --- | --------- | --------- | ------------------------- | --- |
|     | for j=i+1 | to 2*n    | do P[j,i]=P[i,j]          |     |
end
| {Update | ϕ-vector} |             |                     |     |
| ------- | --------- | ----------- | ------------------- | --- |
|         | for i=1   | to 2*n-1 do | ϕ[2*n-i+1]=ϕ[2*n-i] |     |
ϕ[1]=-y
ϕ[n+1]=u
The code description is given in “pidgin” Pascal, and it is assumed
that the variables have been properly declared. There are many re-
finements tothealgorithm; forinstance, itsnumericalproperties can
beimprovedbyusingaso-calledsquarerootalgorithm.Itisalsocom-
mon practice to bandpass filter the signals before introducing them
intothealgorithmtogetridofstaticlevelsandhighfrequencydistur-
bances. There are also many variations of the algorithm to discount
past data. The code gives anindication of the type of algorithms that
| are used | in recursive | parameter | estimation. |     |
| -------- | ------------ | --------- | ----------- | --- |
| 2.8      | Disturbance  |           | Models      |     |
So far, we have only discussed modeling of process dynamics. Dis-
turbances is another important side of the control problem. In fact,
| withoutdisturbances |     | andprocessuncertainty |     | therewouldbenoneed |
| ------------------- | --- | --------------------- | --- | ------------------ |
for feedback. There is a special branch of control, stochastic control
theory, that deals explicitly with disturbances. This has had little
impact on tuning and design of PID controllers. For PID control, dis-
turbanceshave mostlybeenconsidered indirectly, e.g.,byintroducing
integral action. As our ambitions increase and we strive for control
systems withimproved performances it will beuseful toconsider dis-
turbances explicitly. In this section, therefore, we will present some
| models | that can | be used for | this purpose. |     |
| ------ | -------- | ----------- | ------------- | --- |

|     |     |     |     |     | 2.8 | Disturbance | Models | 47  |
| --- | --- | --- | --- | --- | --- | ----------- | ------ | --- |
| A   |     |     |     |     | B   |             |        |     |
0.8
1
0.4
| 0   |     |     |     |     | 0   |     |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| 0 1 | 2   | 3 4 | 5   |     | 0   | 1 2 | 3   | 4 5 |
| C   |     |     |     |     | D   |     |     |     |
4
0
2
| 0   |     |     |     |     | −2  |     |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| 0 1 | 2   | 3 4 | 5   |     | 0   | 1 2 | 3   | 4 5 |
Figure 2.27 Prototype disturbances, A impulse, B step, C ramp,
| and D | sinusoid. |                  |     |          |     |            |      |         |
| ----- | --------- | ---------------- | --- | -------- | --- | ---------- | ---- | ------- |
| There | are       | some fundamental |     | problems |     | in dealing | with | distur- |
bances. An inherent property of disturbances is that they cannot be
predicted exactly. Most mathematical models, however, do have the
property that they give signals that can be predicted exactly. Some
| care must | be exercised | when | interpreting |     | models | and | results. |     |
| --------- | ------------ | ---- | ------------ | --- | ------ | --- | -------- | --- |
SimpleModels
| Simplemathematical |     | models | werefoundtobeveryuseful |     |     |     |     | whendeal- |
| ------------------ | --- | ------ | ----------------------- | --- | --- | --- | --- | --------- |
ing with process dynamics in the previous sections. We will now try
to make models that also can be used to characterize disturbances.
| Examples | ofsomesimple |     | disturbances—impulse, |     |     |     | step, | ramp,and |
| -------- | ------------ | --- | --------------------- | --- | --- | --- | ----- | -------- |
sinusoid—are given in Figure 2.27. The impulse is a mathematical
idealization of a pulse whose duration is short in comparison with
the time scale. The signals are essentially deterministic. The only
uncertain elements in the impulse, step, and ramp are the times
when they start and the signal amplitude. The uncertain elements
| of the sinusoid |         | are frequency, | amplitude, |     | and         | phase. |              |     |
| --------------- | ------- | -------------- | ---------- | --- | ----------- | ------ | ------------ | --- |
| More            | complex | disturbances   |            | can | be obtained |        | by combining | the |
simpledisturbances, asshowninFigure2.28.Thesedisturbances are
obtained by repeating a number of impulses, by combining steps and
ramps, and by changing the amplitude and phase of the sinusoid.
Noise
There are also other types of disturbances that are much more ir-
regular than the signals shown in Figure 2.28. Some examples are
given in Figure 2.29. To characterize signals like the ones shown

| 48 Chapter | 2 ProcessModels |     |     |     |     |     |     |
| ---------- | --------------- | --- | --- | --- | --- | --- | --- |
| A          |                 |     |     | B   |     |     |     |
| 0          |                 |     |     | 0   |     |     |     |
−4
−4
| 0 5    | 10                      | 15  | 20       | 0        | 5   | 10        | 15 20 |
| ------ | ----------------------- | --- | -------- | -------- | --- | --------- | ----- |
| C      |                         |     |          | D        |     |           |       |
| 10     |                         |     |          | 0        |     |           |       |
| 0      |                         |     |          | −1       |     |           |       |
| 0 5    | 10                      | 15  | 20       | 0        | 5   | 10        | 15 20 |
| Figure | 2.28 Disturbances       |     | that are | obtained | by  | combining | the   |
| simple | prototype disturbances. |     |          |          |     |           |       |
in Figure 2.29, it is necessary to describe both the amplitude and
the time characteristics. A distinction between stationary and non-
stationary behavior must first be made. A signal is stationary if its
behavior is essentially the same for all times. The amplitude prop-
erties of a stationary signal can be described by giving a histogram
that tells the fraction of time when the signal has a given ampli-
tude.
The mean value, the standard deviation or the variance, and the
peak-to-peak values are simple ways to characterize the amplitude
distribution. If the amplitude distribution is normal, the distribution
is uniquely given by the mean value m and the standard deviation
σ. The probability for the signal to be outside the 3σlimits is about
0.0026.
| The time | behavior | of  | a stationary | signal | can | be described | by  |
| -------- | -------- | --- | ------------ | ------ | --- | ------------ | --- |
the spectral density function φ(ω). This function characterizes the
| frequency content | of  | a signal. | The value |     |     |     |     |
| ----------------- | --- | --------- | --------- | --- | --- | --- | --- |
1 φ(ω)∆ω
2π
∆ω
| is the average | energy | of  | a signal | in a narrow | band | of  | width |
| -------------- | ------ | --- | -------- | ----------- | ---- | --- | ----- |
aroundω.
| centered |     | The average | energy | is then |     |     |     |
| -------- | --- | ----------- | ------ | ------- | --- | --- | --- |
(cid:1)∞
1
|     |     | σ2  | =   | φ(ω)dω |     |     |     |
| --- | --- | --- | --- | ------ | --- | --- | --- |
2π
−∞
φ(ω)
A signal where is constant is called white noise. Such a signal
| has its energy | equally | distributed | among | all | frequencies. |     |     |
| -------------- | ------- | ----------- | ----- | --- | ------------ | --- | --- |

|     |     |     | 2.8 Disturbance | Models | 49  |
| --- | --- | --- | --------------- | ------ | --- |
| A   |     |     | B               |        |     |
0
0
| −0.4 |       |     | −2   |       |     |
| ---- | ----- | --- | ---- | ----- | --- |
| 0 10 | 20 30 | 40  | 0 10 | 20 30 | 40  |
| C    |       |     | D    |       |     |
| 0    |       |     | 1    |       |     |
−1
−1
| 0 10 | 20 30  | 40              | 0 10           | 20 30 | 40  |
| ---- | ------ | --------------- | -------------- | ----- | --- |
|      | Figure | 2.29 Examplesof | noise signals. |       |     |
MeasuringNoiseCharacteristics
Thenoisecharacteristics canbedetermined inseveral differentways.
There are simple methods that can be used for crude estimates and
more sophisticated methods that give more precise descriptions.
| Asimplewaytoestimate |     | theamplitude | characteristics | istomea- |     |
| -------------------- | --- | ------------ | --------------- | -------- | --- |
sure the average
(cid:1)T
1
|     |     | =   | y(t)dt |     |     |
| --- | --- | --- | ------ | --- | --- |
m¯
T
0
| and the mean | square error |     |     |     |     |
| ------------ | ------------ | --- | --- | --- | --- |
(cid:1)T
1
|     | σ¯2 | = (y(t)−m¯)2dt |     |     |     |
| --- | --- | -------------- | --- | --- | --- |
T
0
To evaluate the integrals it is necessary to know a reasonable value
of T, which requires knowledge about the time scale. An alternative
is to compute the peak-to-peak value y . The standard deviation can
pp
| then be estimated | as  |     |     |     |     |
| ----------------- | --- | --- | --- | --- | --- |
σ¯ = 1
y
|     |     | 6   | pp  |     |     |
| --- | --- | --- | --- | --- | --- |
Notice that it is also necessary to know the time scales in order to
determine the time interval over which the peak-to-peak value is
computed.
| The energy | in a given | frequency | band can | be determined | by  |
| ---------- | ---------- | --------- | -------- | ------------- | --- |
computing the mean square average or the peak-to-peak value of a
filtered signal.
Useful information about the frequency content in a signal can
also be determined from the zero crossings. For a stationary signal

50 Chapter 2 ProcessModels
the average number of zero crossings per second can be determined
from
 
(cid:4)∞ 1/2
ω2φ(ω)dω
 
N = π 1   −∞ (cid:4)∞  
φ(ω)dω
−∞
whereφ(ω)isthe spectral density. Notice thatthis formula has simi-
larities with the formula for determining the average residence time,
Equation (2.24).
For a spectral density that is uniform over the interval (ω,ω),
1 2
we get
1 (cid:5) ω3−ω3 (cid:6) 1/2 1 (cid:2) ω2+ωω +ω2 (cid:3) 1/2
N = 2 1 = 1 1 2 2
π 3(ω −ω) π 3
2 1
For an ideal low-pass filter we have ω = 0 and ω =ω, where ω
1 2 b b
is the band width. In this case we get
ω 2πf
N = √b = √b (cid:9)1.16f
π 3 π 3 b
The average rate of zero crossings per second is thus approximately
equal to the bandwidth measured in Hz. Measurement of zero cross-
ings can easily be combined with computation of the peak-to-peak
value.Moreaccuratedeterminationofthespectralcharacteristicscan
be done by using a spectral analyzer or by recording a data set and
computing the spectrum numerically.
RepresentationofDisturbances
It is often very convenient to consider signals as generated from a
dynamic system with simple inputs as shown in Figure 2.30. For
example, the signals shown in Figure 2.27 can be represented by
sending animpulse through a dynamic system. The transfer function
of the systems for the different signals are
Impulse G(s)=1
1
Step G(s)=
s
1
Ramp G(s)=
s2
ω2
Sinusoid G(s)=
s2+ω2

|     |     | 2.9 Approximate |     | Models | and | Unmodeled | Dynamics |     | 51  |
| --- | --- | --------------- | --- | ------ | --- | --------- | -------- | --- | --- |
|     |     | simple signal   |     |        |     | signal    |          |     |     |
G(s)
| Figure | 2.30 | Signalsrepresentedasoutputsofdynamic |     |     |     |     |     | systems. |     |
| ------ | ---- | ------------------------------------ | --- | --- | --- | --- | --- | -------- | --- |
Similarly the signals in Figure 2.28 can be generated by sending a
| sequence   | of pulses | through       |        | the same     | systems.   |        |        |      |     |
| ---------- | --------- | ------------- | ------ | ------------ | ---------- | ------ | ------ | ---- | --- |
| The        | sameidea  | canbeextended |        |              | todescribe | noise. | Inthis | case | the |
| generating | signal    | is white      | noise. | We           | illustrate | the    | idea.  |      |     |
| EXAMPLE    | 2.13      |               |        |              |            |        |        |      |     |
| The so     | called    | RC noise      | has    | the spectral | density    |        |        |      |     |
a2
φ(ω)=
ω2+a2
It can be represented by sending white noise through a system with
| the transfer | function |     |     |     |     |     |     |     |     |
| ------------ | -------- | --- | --- | --- | --- | --- | --- | --- | --- |
a
G(s)=
s+a
Thepossibilityofrepresentingsignalsinthiswayalsogivesapos-
sibilityofdealingwithnonstationary signals.Theprocessobtainedby
sending white noise through an integrator, for example, is a drifting
| process | that is | called | a random | walk | or a | Wiener | process. |     |     |
| ------- | ------- | ------ | -------- | ---- | ---- | ------ | -------- | --- | --- |
The representation of signals in this way also makes it possible
to see similarities between signals of different type. It turns out
that signals that are generated from the same system have many
similarities. For example, a step signal (Figure 2.27B), a piece-wise
|          |        | (Figure | 2.28B), |     |          |      |         |           |     |
| -------- | ------ | ------- | ------- | --- | -------- | ---- | ------- | --------- | --- |
| constant | signal |         |         | and | a random | walk | are all | generated |     |
by sending primitive signals through an integrator. The primitive
signals are an impulse, a sequence of impulses for the piece-wise
constant signals, or white noise for a random walk. A consequence of
this is that a controller that is designed to work well for one of these
signals will work well for all of them. A step disturbance is thus not
| as special | as          | it may first | appear. |        |     |           |     |     |     |
| ---------- | ----------- | ------------ | ------- | ------ | --- | --------- | --- | --- | --- |
| 2.9        | Approximate |              |         | Models | and | Unmodeled |     |     |     |
Dynamics
In this chapter, we have discussed various ways to model the process
to be controlled. We end the chapter with a discussion about what is
not captured by the models. Typical examples are nonlinearities and

52 Chapter 2 ProcessModels
process variations. Furthermore, the parametric low-order models
give a satisfactory description of the behavior of the true system for
signals with a limited frequency range only.
The process models describe the relation between the process in-
put signal and the process output signal only, but the control system
consists of other signals that influence the control performance. The
characteristics of the setpoint changes, load disturbances, and mea-
surement noise must also be taken into account in the design of the
control system.
Manydesignmethods forPIDcontrollers requirethattheprocess
modelbeofloworder.Somemethodstoapproximatehigher-orderpro-
cess models with low-order models are also presented in this section.
Nonlinearities
All dynamic models presented in this chapter are linear, whereas
most processes in practice are nonlinear. Nonlinear valves, actuators
orsensorsresultintheprocesshavingdifferentdynamicsatdifferent
operating points. A linear model, obtained by transient or frequency
response analysis of a nonlinear process, is only valid at the actual
operating point. This means that a controller that is tuned based on
this model may work well only at this operating point.
There are several ways to overcome the problem. A simple way
is to tune the controller for the worst case and accept degraded per-
formance at other operating conditions. If the characteristics of the
nonlinearity are known, it can be compensated by feeding signals
through a function module thatforms the inverse of thenonlinearity.
Anexampleisaflowmeter basedonmeasurement ofdifference pres-
sure.Theflowisproportionaltothesquareofthedifferencepressure.
A linear relation between the flow and the output signal from the
flow meter can be obtained by feeding the measured signal through
a square root function.
Another way to compensate for nonlinearities is to divide the op-
erating range into several smaller ranges where the process can be
well approximated by linear models. A controller with satisfactory
behavior for the full operating range can be obtained by determining
one model for each operating range and changing the controller pa-
rameters with the operating condition. This approach is called gain
scheduling.
ParametricModels
If the process is linear, a step response reveals all information about
the process dynamics. Inthe same way, a Nyquist curve or frequency

2.9 Approximate Modelsand Unmodeled Dynamics 53
response gives a complete description of the process dynamics. In-
formation is lost when going from these graphical descriptions to
parametric models. Theparametric models derived forPIDcontroller
tuning are normally of low order. This means that quite a lot of in-
formation is lost. It is, therefore, particularly important that these
simple models are derived properly and that their limitations are
kept in mind when using them for controller tuning.
The parametric models based onstep response analysis areoften
accurate at low frequencies, whereas they become more uncertain at
higher frequencies. The simple models based on frequency response
analysis, described in Section 2.6, are accurate at the frequencies of
theinputsignals,butnotatotherfrequencies.Thebasicrelaymethod
thusisaccuratearound theultimate frequencyω ,butnotfor higher
u
and lower frequencies.
ProcessVariations
The model is valid at the time the experiment is performed. If the
processdynamicschangewithtime,itmaynotbevalidatalatertime.
This problem can be handled in the same way as the nonlinearities
described above.
A simple solution is to base the controller tuning on the model
thatdescribestheworstcase.Gainscheduling canbeusedifthetime
variations canberelated tosome measurable variable. Adaptive con-
trolcanbeusediftheprocessvariationsarerandominthesensethat
they cannot be related to any measurable variable. Such a controller
will adapt itself automatically to the actual process dynamics.
Disturbances
There are always disturbances acting on a control system. We distin-
guish between three types of disturbances, namely, setpoint changes
(y ), load disturbances (l), and measurement noise (n) (see Figure
sp
2.31).
Setpoint Changes
In process control, most control loops have a constant setpoint. (An
exception is the controller sitting in the inner loop in cascade con-
trol.) The setpoint may change at certain time instances because of
desires to change operating conditions such as production rates. The
setpoint is, asaresult, typically piece-wise constant with changes oc-
curringrarely.Itis,therefore, suitabletomodelthesetpoint asastep
function.

| 54  | Chapter 2 Process Models |     |     |
| --- | ------------------------ | --- | --- |
Since the setpoint is a disturbance that we have access to, it is
possibletofeeditthroughalow-passfilterorarampingmodulebefore
itentersthePIDcontroller.Inthisway,thestepfunctioncanbemade
smoother. This property isuseful, since manycontrol design methods
giving a good rejection of load disturbances give too large overshoots
| after | a sudden change in | the setpoint. |     |
| ----- | ------------------ | ------------- | --- |
Load Disturbances
Loaddisturbancesaredisturbancesthatentersthecontrolloopsome-
whereintheprocessanddrivethesystemawayfromitsdesiredoper-
ating point. They may be caused by quality variations in a feed flow
or variations in the demand flow, for example. These disturbances
are the most common and the most important disturbances in pro-
cesscontrol. When discussing controller design inChapter 4,wewill,
therefore, focus on the behavior with respect to these disturbances.
The load disturbance is typically a low-frequency disturbance,
and it will, furthermore, be more or less low-pass filtered by the
process depending on where in the process it enters. Consequently, it
usually results in a low-frequency disturbance in the process output.
To obtain this characteristic in the process output, we model the
load disturbance as a step function added to the control signal at
| the process | input (see Figure | 2.31). |     |
| ----------- | ----------------- | ------ | --- |
| Measurement | Noise             |        |     |
Measurement noise represents disturbances thatdistort theinforma-
tion about the process variables obtained from the sensors. Measure-
ment noise may be of different character. It may be high-frequency
fluctuations anditmaybelow-frequencycalibration errors.Withsev-
eral sensors it is possible to reduce calibration errors. With only one
sensor nothing can be done about calibration errors; we, therefore,
|     |     | l   | n   |
| --- | --- | --- | --- |
| y   | e   | u   | x y |
sp
|     | Σ Controller | Σ Process | Σ   |
| --- | ------------ | --------- | --- |
–1
Figure 2.31 Block diagram of a simple feedback loop with three
typesofdisturbances: Setpointchanges(y ),loaddisturbances (l)
sp
| and | measurement noise | (n). |     |
| --- | ----------------- | ---- | --- |

|     |     | 2.9 | Approximate | Modelsand |     | Unmodeled | Dynamics | 55  |
| --- | --- | --- | ----------- | --------- | --- | --------- | -------- | --- |
will model measurement noise as a high-frequency signal added to
| the | process          | output. |       |         |     |         |                |       |
| --- | ---------------- | ------- | ----- | ------- | --- | ------- | -------------- | ----- |
|     | Sincemeasurement |         | noise | doesnot |     | contain | anyinformation | about |
thestatusoftheprocess,itshouldbefilteredout.Furthermore,high-
frequency components in themeasurement signal might beamplified
bythecontroller andcausewearontheactuator.Filteringdoesintro-
duce additional dynamics. It is therefore important to take the filter
dynamics into account in the controlling design. We will model the
| measurement |     | noise | as an | impulse | function. |     |     |     |
| ----------- | --- | ----- | ----- | ------- | --------- | --- | --- | --- |
ApproximatingComplexModels
Inmodelingitisoftenconvenienttosplitasystemintointerconnected
subsystems.Anexamplecouldbetodivideasystemintoactuator,pro-
cess, and sensor. Another example occurs when general control loops
arecascaded.Wemaybeinterested theninobtaining asimplified de-
scription of the closed loop. Even if the model for each partis simple,
the complete model may then be quite complex. Since many of the
design methods for PID controllers are based on simple models, we
need a procedure to simplify a complex model. Some ways to make
| such | approximations |     | are discussed |     | below. |     |     |     |
| ---- | -------------- | --- | ------------- | --- | ------ | --- | --- | --- |
To perform the approximations it is necessary to determine the
frequency rangewheretheapproximation should bevalid. Wedothis
simply by saying that the models should describe the system well
ω.
around the frequency 0 This frequency should be approximately
the same as the frequency of the dominant closed-loop poles of the
desired system or the desired bandwidth of the closed-loop system.
| (The |        |             |     |       |              |     |            | 4.)    |
| ---- | ------ | ----------- | --- | ----- | ------------ | --- | ---------- | ------ |
|      | notion | of dominant |     | poles | is discussed |     | in Chapter | Having |
restrictedthemodelingtoarathernarrowfrequencyrange,low-order
models can now be determined by fitting them to experimental data,
| as  | described | previously | in  | this | section. |     |     |     |
| --- | --------- | ---------- | --- | ---- | -------- | --- | --- | --- |
Another possibility is to start with a complex model of the form
|     |     |      | 1+b | s+b | s2+⋅⋅⋅+b |     | sn    |     |
| --- | --- | ---- | --- | --- | -------- | --- | ----- | --- |
|     |     | (s)= |     | 1   | 2        |     | n −sL |     |
|     |     | G p  | K   |     |          |     | e     |     |
|     |     |      | 1+a | s+a | s2+⋅⋅⋅+a |     | sn    |     |
|     |     |      |     | 1   | 2        |     | n     |     |
and approximate it. The approximation is done in the following way.
ω
Poles and zeros that are much slower than are approximated by
0
integrators, poles, and zeros of the same order as ω are retained,
0
ω
and poles and zeros that are much faster than 0 are neglected or
approximated by a small time lag. A dead time such that ω L ≪ 1
0
is neglected or approximated by a time constant. The approximation
of fast poles and zeros by a first order system is illustrated by an
example.

| 56       | Chapter | 2 ProcessModels   |        |        |            |        |       |     |
| -------- | ------- | ----------------- | ------ | ------ | ---------- | ------ | ----- | --- |
| EXAMPLE  | 2.14    | Approximation     |        | of     | fast modes |        |       |     |
| Consider | the     | transfer function |        |        |            |        |       |     |
|          |         |                   | K(1+sT | )(1+sT |            | )      |       |     |
|          | G(s)=   |                   |        | 1      |            | 2      | e −sL |     |
|          |         | (1+sT             | )(1+sT | )(1+sT |            | )(1+sT | )     |     |
|          |         |                   | 3      | 4      | 5          |        | 6     |     |
where
|              |            | =T +T | +T  | +T −T  | −T       | − L>0    |     |          |
| ------------ | ---------- | ----- | --- | ------ | -------- | -------- | --- | -------- |
|              |            | T 3   | 4 5 | 6      | 1        | 2        |     |          |
| and it       | is assumed | that  | L ≪ | T. The | transfer | function |     | G can be |
| approximated |            | by    |     |        |          |          |     |          |
K
G(s)=
1+sT
| EXAMPLE  | 2.15 | Approximation |       | of      | fast and | slow   | modes |     |
| -------- | ---- | ------------- | ----- | ------- | -------- | ------ | ----- | --- |
| Consider | the  | same system   | as in | Example | 2.14.    | Assume | that  |     |
|          |      |               | T >T  | >T      | >T       |        |       |     |
|          |      |               | 3     | 4 5     | 6        |        |       |     |
and that
|     |     |     | T >max | (T  | ,T ,L) |     |     |     |
| --- | --- | --- | ------ | --- | ------ | --- | --- | --- |
|     |     |     | 5      | 1   | 2      |     |     |     |
Furthermore, let it be desired to obtain a model that describes the
| process | well | in the frequency | range |      |     |     |     |     |
| ------- | ---- | ---------------- | ----- | ---- | --- | --- | --- | --- |
|         |      |                  | 1     |      | 1   |     |     |     |
|         |      |                  |       | <ω < |     |     |     |     |
0
|     |     |     | T   |     | T   |     |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
|     |     |     | 4   |     | 5   |     |     |     |
The time constant T 3 is slower than T 4 and T 5 , and it will therefore
| be approximated |     | by an | integrator, | i.e., |     |     |     |     |
| --------------- | --- | ----- | ----------- | ----- | --- | --- | --- | --- |
|                 |     |       | 1           |       | 1   |     |     |     |
(cid:9)
|     |     |     | 1+sT |     | sT  |     |     |     |
| --- | --- | --- | ---- | --- | --- | --- | --- | --- |
|     |     |     |      | 3   | 3   |     |     |     |
The time constants T , T , T , and the time delay L are all smaller
|        |        | 1                    | 2 6 |     |          |      |          |     |
| ------ | ------ | -------------------- | --- | --- | -------- | ---- | -------- | --- |
| than T | . They | will be approximated |     | by  | a single | time | constant |     |
5
|         |          |            | =       | −T −T        | −   |     |     |     |
| ------- | -------- | ---------- | ------- | ------------ | --- | --- | --- | --- |
|         |          |            | T T 6   | 1            | 2   | L   |     |     |
| If T is | positive | the system | is then | approximated |     | by  |     |     |
K
G(s)=
|     |     |     | sT (1+st | )(1+sT |     | )(1+sT) |     |     |
| --- | --- | --- | -------- | ------ | --- | ------- | --- | --- |
|     |     |     | 3        | 4      | 5   |         |     |     |
If T is negative the transfer function is instead approximated by
K(1+sT)
G(s)=
|     |     |     |      | (1+sT | )(1+sT | )   |     |     |
| --- | --- | --- | ---- | ----- | ------ | --- | --- | --- |
|     |     |     | sT 3 |       | 4      | 5   |     |     |

2.10 Conclusions 57
Summary
To summarize: When deriving a simple model to be used for PID
controller tuning, it is important to ensure that the model describes
the process well for the typical input signals obtained during the
process operations. The amplitude and frequency distribution of the
signal is of importance. Model accuracy may be poor if the process is
nonlinear or time varying. Control quality can be improved by gain
schedulingoradaptivecontrol.Itisalsoimportanttoknowwhatkind
of disturbances are acting on the system and which limitation they
impose.
2.10 Conclusions
Modeling is an important aspect of controller tuning. The models we
need should describe how the process reacts to control signals. They
should also describe the properties of thedisturbances that enter the
system. Most work on tuning of PID controllers have focused on the
process dynamics, which is also reflected in the presentation in this
chapter.
A number of methods for determining the dynamics of a process
have been presented in this chapter. Some are very simple: they
are based on a direct measurement of the step response and simple
graphical constructions. Others are based on the frequency response.
Ithasbeenshownthatveryusefulinformationcanbegeneratedfrom
relayfeedbackexperiments. Suchexperiments areparticularly useful
because the process is brought into self-oscillation at the ultimate
frequency, which is of considerable interest for design of controllers.
The simple methods are useful in field work when a controller
has to be tuned and few tools are available. The methods are also
useful to provide understanding as well as being references when
morecomplicatedmethodsareassessed.Wehavealsopresentedmore
complicated methods that require significant computations.
Modelsofdifferentcomplexityhavebeenpresented. Manymodels
were characterized by a few parameters. Such models are useful for
many purposes and are discussed in Chapter 4. When using such
models it should be kept in mind that they are approximations.
When deriving the models we also introduced two dimension-
free quantities, the normalized dead time τ and the gain ratio κ.
These parameters make it possible to make a crude assessment of
the difficulty of controlling the process. Processes with small values
areeasy tocontrol. The difficulty increases asthe values approach 1.
Tuning rules based onτandκare provided in Chapter 5.

58 Chapter 2 ProcessModels
2.11 References
Processmodelingisakeyelementinunderstandingandsolvingacon-
trol problem. Good presentations of modeling are found in standard
textbooks on control, such as (Buckley, 1964), (Smith, 1972), (Se-
borget al.,1989), and (Luyben, 1990). These books have much mate-
rialonmanydifferentmodelingtechniques.Similarpresentations are
given in (Gille et al., 1959), (Harriott, 1964), (Oppelt, 1964), (Taka-
hashi et al., 1972), (Deshpande and Ash, 1981), (Shinskey, 1988),
(Stephanopoulos, 1984), and (Hägglund, 1991). There are also books
that specialize in modeling for control system design, see (Wellstead,
1979), (Nicholson, 1980), (Nicholson, 1981), and (Close and Freder-
ick, 1993).
Intheearlyworkmucheffortwasdevoted tocharacterizedynam-
ics by the step response, which at that time was called the response
curve. See (Ziegler et al., 1943) and the books (Tucker and Wills,
1960) and (Lloyd and Anderson, 1971), which were written by prac-
titioners in control companies. A nice overview of step and frequency
response methods is given in the paper (Rake, 1980). Additional de-
tails are given in (Strejc, 1959) and (Anderssen and White, 1971).
Frequencyresponsemethodsarepresentedin(Anderssen andWhite,
1970).
The relay method is treated in (Åström and Hägglund, 1984),
(HägglundandÅström,1991),and(Schei,1992).Thedescribingfunc-
tion method is well documented in (Atherton, 1975) and (Gelb and
Velde, 1968). There are many books on parameter estimation, the
book (Johansson, 1993) is quite accessible. More mathematical de-
tails are found in (Ljung, 1987), (Ljung and Söderström, 1983), and
(Söderström and Stoica, 1988). Many useful practical aspects on sys-
tem identification are given in (Isermann, 1980).

| PID | Control |     |     |     |     |
| --- | ------- | --- | --- | --- | --- |
3.1 Introduction
| ThePIDcontroller | isbyfarthemostcommoncontrolalgorithm.Most |     |     |     |     |
| ---------------- | ----------------------------------------- | --- | --- | --- | --- |
feedback loops are controlled by this algorithm or minor variations
of it. It is implemented in many different forms, as a stand-alone
|            |              | (Direct  |         | Control) |     |
| ---------- | ------------ | -------- | ------- | -------- | --- |
| controller | or as a part | of a DDC | Digital | package  | or  |
a hierarchical distributed process control system. Many thousands
of instrument and control engineers worldwide are using such con-
trollers in their daily work. The PID algorithm can be approached
from many different directions. It can be viewed as a device that can
be operated with a few rules of thumb, but it can also be approached
analytically.
This chapter gives an introduction to PID control. The basic al-
gorithm and various representations are presented in detail. A de-
scription of the properties of the controller in a closed loop based on
intuitiveargumentsisgiven.Thephenomenonofresetwindup,which
occurswhenacontrollerwithintegralactionisconnectedtoaprocess
withasaturating actuator, isdiscussed, including several methods to
avoid it.
| Some | important | aspects of digital | computer | implementation | of  |
| ---- | --------- | ------------------ | -------- | -------------- | --- |
PID controllers are given: issues such as prefiltering, different digi-
talapproximations, noise filtering,andcomputercodeforgoodimple-
mentation. Operational aspects, such as bumpless transfer between
manual and automatic mode and between different parameter sets,
are also presented. The chapter ends with some aspects on the use
and misuse of PID control with examples of systems where PID con-
| trol works | well and where | it does not. |     |     |     |
| ---------- | -------------- | ------------ | --- | --- | --- |
59

60 Chapter 3 PID Control
3.2 The Feedback Principle
The idea of feedback is deceptively simple and, yet, extremely pow-
erful. It has had a profound influence on technology. Application of
the feedback principle has resulted in major breakthroughs in con-
trol, communication, and instrumentation. Many patents have been
granted on the idea. Assume for simplicity that the process is such
thatthe process variable increases when the manipulated variable is
increased. Theprinciple offeedback canthenbeexpressed asfollows:
Increase the manipulated variable when the process variable
is smaller than the setpoint and decrease the manipulated
variablewhentheprocessvariableislargerthanthesetpoint.
This type of feedback is called negative feedback because the ma-
nipulatedvariablemovesinoppositedirectiontotheprocessvariable.
Thefeedback principle canbeillustrated bytheblockdiagram shown
inFigure3.1.Inthisdiagramtheprocessandthecontrollerarerepre-
sented asboxes witharrowsdenoting inputs andoutputs. Notice also
that there is a special symbol to denote the summation of signals.
Theblock diagram shows that the process andthe controller arecon-
nected in a closed feedback loop. The presence of the sign-reversing
block indicates that the feedback is negative.
The reason whyfeedback systems are of interest is that feedback
makes the process variable close to the setpoint in spite of distur-
bances and variation of the process characteristics.
On-OffControl
The feedback can be arranged in many different ways. Asimple feed-
back mechanism can be described mathematically as follows:
(cid:19)
u if e>0
u= max (3.1)
u if e<0
min
where e = y − y is the control error. This control law implies that
sp
maximumcorrectiveactionisalwaysused.Themanipulatedvariable,
y e u y
sp Σ
Controller Process
−1
Figure 3.1 Blockdiagramofaprocesswithafeedbackcontroller.

|     |     |     |     | 3.2 | TheFeedback | Principle |     | 61  |
| --- | --- | --- | --- | --- | ----------- | --------- | --- | --- |
| A   | u   |     | B   | u   | C           |           | u   |     |
|     |     | e   |     |     | e           |           |     | e   |
Figure 3.2 Controller characteristicsfor ideal on-offcontrol(A),
|                   |     |      |           | (B) | hysteresis(C). |     |     |     |
| ----------------- | --- | ---- | --------- | --- | -------------- | --- | --- | --- |
| and modifications |     | with | dead zone |     | and            |     |     |     |
thus,hasitslargestvalue when theerrorispositive, anditssmallest
value when the error is negative. This type of feedback is called
on-off control. It is simple and there are no parameters to choose.
On-off control often succeeds in keeping the process variable close
to the setpoint, but it will typically result in a system where the
(3.1)
variables oscillate. Notice that in Equation the control variable
is not defined when the error is zero. It is common to have some
(see
modifications either by introducing hysteresis or a dead zone
Figure 3.2).
ProportionalControl
Thereasonwhyon-offcontroloftengivesrisetooscillationsisthatthe
system overreacts because a small change in the error will make the
manipulatedvariablechangeoverthefullrange.Thiseffectisavoided
in proportional control where the characteristic of the controller is
proportional to the control error for small errors. Figure 3.3 shows
the characteristic of a proportional controller. The controller is thus
characterizedbythenonlinear functionu= f (e)showninthefigure.
c
Todescribethecharacteristicofaproportionalcontrollerwemust
| ofcoursegivethelimitsu |     |     | andu | ofthecontrolvariable.Thelin- |     |     |     |     |
| ---------------------- | --- | --- | ---- | ---------------------------- | --- | --- | --- | --- |
|                        |     |     | max  | min                          |     |     |     |     |
ear range canbe specified either bygiving the slope of the character-
| (controller |      | K)  |              |     |             |     |            |     |
| ----------- | ---- | --- | ------------ | --- | ----------- | --- | ---------- | --- |
| istic       | gain |     | or by giving | the | range where | the | character- |     |
isticislinear (proportional band P ).Thisrangeisnormally centered
b
around the setpoint. The proportional band and the controller gain
| are related    | through |     |            |     |      |       |         |       |
| -------------- | ------- | --- | ---------- | --- | ---- | ----- | ------- | ----- |
|                |         |     | u −u       | =   | K P  |       |         | (3.2) |
|                |         |     | max        | min | b    |       |         |       |
|                |         |     |            | −u  | =100 |       |         |       |
| It is normally | assumed |     | that u max | min | %,   | which | implies | that  |
100
|     |     |     | K   | =   |     |     |     | (3.3) |
| --- | --- | --- | --- | --- | --- | --- | --- | ----- |
P b
Notice that a proportional controller acts like an on-off controller for
large errors.

| 62 Chapter | 3 PID | Control |     |     |     |
| ---------- | ----- | ------- | --- | --- | --- |
u
    max u
SlopeK
u
  b
u
    min
e
Proportional band
Figure 3.3 Characteristic of aproportional controller. The input
| is controlerror | eand | the output | is controlsignal | u.  |     |
| --------------- | ---- | ---------- | ---------------- | --- | --- |
StaticAnalysisofFeedbackSystems
Some properties of a control system can be understood by a simple
static analysis. Todothis weintroduce thestatic process characteris-
| tic,whichisacurvethatshowsthestationary |     |     |     | valueofprocessoutput |     |
| --------------------------------------- | --- | --- | --- | -------------------- | --- |
yasafunctionofprocessinputu.SeeFigure3.4.Noticethatthecurve
hasaphysical interpretation only forastable process. Thestatic pro-
cess characteristic is very important. Itcan be used to determine the
range of control signals required to change the process output over
thedesired range,tosizeactuators,andtoselectsensor resolution. It
can also be used to assess whether static gain variations are so large
| that they must | be accounted | for | in the control | design. |     |
| -------------- | ------------ | --- | -------------- | ------- | --- |
| Proportional   | Control      |     |                |         |     |
Consideraprocessunderproportionalcontrol.Letthecontrollerchar-
| acteristic be |     |     |          |     |       |
| ------------- | --- | --- | -------- | --- | ----- |
|               |     | u=  | f (y −y) |     | (3.4) |
|               |     |     | c sp     |     |       |
Introducingtheinversecontroller characteristic f −1,thiscanbewrit-
c
ten as
|                     |     | y −y=      | f −1(u)                 |     |       |
| ------------------- | --- | ---------- | ----------------------- | --- | ----- |
|                     |     | sp         | c                       |     |       |
| Further introducing |     | the static | process characteristic, |     |       |
|                     |     |            | y= (u)                  |     | (3.5) |
f p
we find that the equilibrium value of u satisfies the equation
−1(u)=
|     |     | y − | f f (u) |     | (3.6) |
| --- | --- | --- | ------- | --- | ----- |
|     |     | sp  | c p     |     |       |

|     |     |     |     | 3.2 | The Feedback | Principle |     | 63  |
| --- | --- | --- | --- | --- | ------------ | --------- | --- | --- |
y
u
Figure 3.4 Static process characteristic. Shows process output y
| as afunctionof |     | process | input uunder | static | conditions. |     |     |     |
| -------------- | --- | ------- | ------------ | ------ | ----------- | --- | --- | --- |
This equation can be solved graphically by finding the intersection
|         |            |     |               | (u) |          | − −1(u) |     |       |
| ------- | ---------- | --- | ------------- | --- | -------- | ------- | --- | ----- |
| between | the graphs | of  | the functions | f p | and y sp | f       | as  | shown |
c
in Figure 3.5. The intersection is unique if the static characteristics
are monotone. The equilibrium value of process output yis obtained
simply as the y-coordinate of the intersection. In the graphical con-
struction, it is easy to see how the equilibrium is influenced by the
setpoint andthecontroller gain.Theequilibrium agreeswiththeset-
| point only | if  |     |     |         |     |     |     |       |
| ---------- | --- | --- | --- | ------- | --- | --- | --- | ----- |
|            |     |     | =   | d=ef (u | )   |     |     | (3.7) |
|            |     |     | y y | f       |     |     |     |       |
|            |     |     | sp  | 0 p     | b   |     |     |       |
−1(u)
| y   |     | y sp −f | c   |     |     |     |     |     |
| --- | --- | ------- | --- | --- | --- | --- | --- | --- |
y
1
slope
|     |     |     |     | K   |     | f   p(u) |     |     |
| --- | --- | --- | --- | --- | --- | -------- | --- | --- |
| y   |     |     |     |     |     |          |     |     |
  sp
 y
    0 y
|     |     | u   |   b u } |     | u   |     | u   |     |
| --- | --- | --- | ------- | --- | --- | --- | --- | --- |
|     |     | min |         |     | max |     |     |     |
a
| Figure     | 3.5              | Determinationofequilibriumfromstaticprocessand |     |     |     |     |     |     |
| ---------- | ---------------- | ---------------------------------------------- | --- | --- | --- | --- | --- | --- |
| controller | characteristics. |                                                |     |     |     |     |     |     |

| 64 Chapter |     | 3 PID | Control |     |     |     |     |     |
| ---------- | --- | ----- | ------- | --- | --- | --- | --- | --- |
For all other values of the setpoint there will be a deviation. If the
process characteristic is approximated by a straight line with slope
| K ,andthecontrollergainis |     |     |     | K,thedeviationcaneasilybecomputed. |     |     |     |     |
| ------------------------- | --- | --- | --- | ---------------------------------- | --- | --- | --- | --- |
p
Introducing the parameter a shown in Figure 3.5, we find that
|     |     |     |     |     | (cid:5) | (cid:6) |     |     |
| --- | --- | --- | --- | --- | ------- | ------- | --- | --- |
1
|     |     |     | y   | −y = | K + | a   |     |     |
| --- | --- | --- | --- | ---- | --- | --- | --- | --- |
|     |     |     | sp  | 0    | p   |     |     |     |
K
and
1
|     |     |     |     | y −y= | a   |     |     |     |
| --- | --- | --- | --- | ----- | --- | --- | --- | --- |
sp
K
| This implies |     | that the | steady-state |     | error is | given by |     |       |
| ------------ | --- | -------- | ------------ | --- | -------- | -------- | --- | ----- |
|              |     |          | e= −y=       |     | 1 (y     | −y       | )   | (3.8) |
y
|     |     |     | sp  |     | 1+K K | sp 0 |     |     |
| --- | --- | --- | --- | --- | ----- | ---- | --- | --- |
p
| The smaller |     | the deviation, |     | the larger | is the | loop gain | K K. |     |
| ----------- | --- | -------------- | --- | ---------- | ------ | --------- | ---- | --- |
p
| 3.3 | PID | Control |     |     |     |     |     |     |
| --- | --- | ------- | --- | --- | --- | --- | --- | --- |
Intheprevioussectionwesawthatproportionalcontrolhadthedraw-
backthatitmostlyresultsinastaticorsteadystateerror.Thecontrol
algorithmsusedinpracticeare,therefore, usuallymorecomplexthan
the proportional controller. It has been found empirically that a so-
called PID controller is a useful structure. Inside the proportional
band the behaviour of the “textbook” version of the PID algorithm
| can be | described | as:   |         |     |          |       |         |       |
| ------ | --------- | ----- | ------- | --- | -------- | ----- | ------- | ----- |
|        |           |       | (cid:5) |     | (cid:1)t |       | (cid:6) |       |
|        |           |       |         | 1   |          | de(t) |         |       |
|        |           | u(t)= | K e(t)+ |     | e(τ)dτ+T |       |         | (3.9) |
d
|     |     |     |     | T   |     |     | dt  |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
i
0
|                    |     |     |          |     |               |     | (e=   | −y). |
| ------------------ | --- | --- | -------- | --- | ------------- | --- | ----- | ---- |
| whereuisthecontrol |     |     | variable | and | eisthecontrol |     | error | y sp |
The control variable is thus a sum of three terms: the P-term (which
is proportional to the error), the I-term (which is proportional to the
|          |        | error), |     |     | (which |     |              |        |
| -------- | ------ | ------- | --- | --- | ------ | --- | ------------ | ------ |
| integral | of the |         | and | the | D-term | is  | proportional | to the |
derivative of the error). The controller parameters are proportional
| gain K, | integral | time | T, i and | derivative | time | T d . |     |     |
| ------- | -------- | ---- | -------- | ---------- | ---- | ----- | --- | --- |
ProportionalAction
In the case of pure proportional control, the control law of Equation
| (3.9) reduces |     | to  |     |       |         |     |     |        |
| ------------- | --- | --- | --- | ----- | ------- | --- | --- | ------ |
|               |     |     |     | u(t)= | Ke(t)+u |     |     | (3.10) |
b
The control action is simply proportional to the control error. The
variable u is a bias or a reset. When the control error e is zero, the
b

|     |     |     |     |     |     | 3.3 | PID | Control 65 |
| --- | --- | --- | --- | --- | --- | --- | --- | ---------- |
control variable takes the value u(t) = u . Bias u is often fixed to
|            |         |     |       |           |             | b         | b   |             |
| ---------- | ------- | --- | ----- | --------- | ----------- | --------- | --- | ----------- |
| (u         | +u )/2, |     |       |           |             |           |     |             |
| max        | min     | but | can   | sometimes | be adjusted | manually  |     | so that the |
| stationary | control |     | error | is zero   | at a given  | setpoint. |     |             |
Static Analysis
Severalpropertiesofproportionalcontrolcanbeunderstoodbythefol-
lowing argument, which is based on pure static considerations. Con-
siderthesimplefeedbackloop,showninFigure3.6,andcomposedofa
process and a controller. Assume that the controller has proportional
| action | and that | the | process | is modeled |       | by the static | model |        |
| ------ | -------- | --- | ------- | ---------- | ----- | ------------- | ----- | ------ |
|        |          |     |         | =          | (u+l) |               |       | (3.11) |
|        |          |     |         | x          | K p   |               |       |        |
where x is the process variable, u is the control variable, l is a load
disturbance,and K p isthestaticprocessgain.Thefollowingequations
| are obtained |     | from | the block | diagram. |       |     |     |        |
| ------------ | --- | ---- | --------- | -------- | ----- | --- | --- | ------ |
|              |     |      |           | y= x+n   |       |     |     |        |
|              |     |      |           | x=       | (u+l) |     |     | (3.12) |
|              |     |      |           | K        | p     |     |     |        |
|              |     |      |           | u= K(y   | −y)+u |     |     |        |
|              |     |      |           |          | sp    | b   |     |        |
Elimination of intermediate variables gives the following relation be-
tween process variable x, setpoint y , load disturbance l, and mea-
sp
| surement | noise | n:  |     |      |      |        |     |        |
| -------- | ----- | --- | --- | ---- | ---- | ------ | --- | ------ |
|          |       |     | KK  |      |      | K      |     |        |
|          |       | x=  |     | p (y | −n)+ | p (l+u | )   | (3.13) |
|          |       |     | 1+  | sp   | 1+   |        | b   |        |
|          |       |     | KK  |      |      | KK     |     |        |
|          |       |     |     | p    |      | p      |     |        |
Compare with Equation (3.8) of the previous section. Product KK
p
is a dimensionless number called the loop gain. Several interesting
propertiesoftheclosed-loop systemcanbereadfromEquation(3.13).
First assume that n and u b are zero. Then the loop gain should be
high in order to ensure that process output x is close to setpoint y .
sp
Ahigh value of theloop gainwill also makethe system insensitive to
|     |     |     |            |     | l   |         |     | n   |
| --- | --- | --- | ---------- | --- | --- | ------- | --- | --- |
| y   |     | e   |            | u   |     |         | x   | y   |
| sp  | Σ   |     |            |     | Σ   |         |     | Σ   |
|     |     |     | Controller |     |     | Process |     |     |
–1
|     | Figure | 3.6 | Block | diagram | of asimple | feedback | loop. |     |
| --- | ------ | --- | ----- | ------- | ---------- | -------- | ----- | --- |

| 66  | Chapter | 3   | PID Control |     |     |     |     |     |     |
| --- | ------- | --- | ----------- | --- | --- | --- | --- | --- | --- |
load disturbance l. However, if n is nonzero, it follows from Equation
(3.13)
|     | that | measurement |     | noise | n influences |     | the process | output | in  |
| --- | ---- | ----------- | --- | ----- | ------------ | --- | ----------- | ------ | --- |
the same way as setpoint y . To avoid making the system sensitive
sp
to measurement noise, the loop gain should not be made too large.
Further,thecontroller biasu influences thesystem inthesameway
b
as a load disturbance. It is, therefore, obvious that the design of the
loop gain is a trade-off between different control objectives, and that
there is no simple answer to what loop gain is the best. This will
| depend | on  | which | control | objective | is  | the most | important. |     |     |
| ------ | --- | ----- | ------- | --------- | --- | -------- | ---------- | --- | --- |
(3.13)
|     | It also | follows | from | Equation |     | that | there will | normally | be  |
| --- | ------- | ------- | ---- | -------- | --- | ---- | ---------- | -------- | --- |
a steady-state error with proportional control. This can be deduced
(3.12)
intuitively from the observation following from Equation that
the control error is zero only when u =u in stationarity. The error,
b
| therefore,canbemadezeroatagivenoperatingcondition |     |                |     |      |     |     |     | byaproper |     |
| ------------------------------------------------- | --- | -------------- | --- | ---- | --- | --- | --- | --------- | --- |
| choice                                            | of  | the controller |     | bias | u . |     |     |           |     |
b
The static analysis given above is based on the assumption that
the process can be described by a static model. This leaves out some
important properties of the closed-loop system dynamics. The most
important one is that the closed-loop system will normally be un-
stable for high-loop gains if the process dynamics are considered. In
practice, the maximum loop gain is thus determined by the process
dynamics.Onewaytodescribeprocessdynamicsleadstodescriptions
like Equation (3.11) where the process gain is frequency-dependent.
| (This | was | discussed | in  | Chapter | 2.) |     |     |     |     |
| ----- | --- | --------- | --- | ------- | --- | --- | --- | --- | --- |
A typical example of proportional control is illustrated in Figure
3.7. The figure shows the behaviour of the process output and the
|     |     |     | K =5 |     |     |     |     |     |     |
| --- | --- | --- | ---- | --- | --- | --- | --- | --- | --- |
K =2
1
=1
K
0
|     | 0   |     | 5   |     | 10  |     | 15  |     | 20  |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
=5
K
|     | K   | =2  |     |     |     |     |     |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
|     | K   | =1  |     |     |     |     |     |     |     |
2
−2
|     | 0   |     | 5   |     | 10  |     | 15  |     | 20  |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
Figure 3.7 Simulation of a closed-loop system with proportional
control.TheprocesstransferfunctionisG(s)=(s+1)−3.Theupper
=
diagram shows setpoint y sp 1 and process output y for different
|     | valuesofcontrollergain |           |            | K.Thelowerdiagramshowscontrolsignal |     |     |     |     |     |
| --- | ---------------------- | --------- | ---------- | ----------------------------------- | --- | --- | --- | --- | --- |
|     | u for                  | different | controller | gains.                              |     |     |     |     |     |

|     |     |     | 3.3 PID Control | 67  |
| --- | --- | --- | --------------- | --- |
control signal after a step change in the setpoint. The steady state
(3.13).
| error can         | be computed from                           | Equation | The bias term | u b , the |
| ----------------- | ------------------------------------------ | -------- | ------------- | --------- |
| loadl,andthenoise | nareallzerointhesimulation.Withacontroller |          |               |           |
gain K = 1 and a static process gain K = 1, the error is therefore
p
50%. The figure shows that the steady state error decreases with
increasingcontroller gainaspredictedbyEquation(3.13).Noticealso
thattheresponse becomesmoreoscillatory withincreasing controller
| gain. This | is due to the process | dynamics. |     |     |
| ---------- | --------------------- | --------- | --- | --- |
IntegralAction
The main function of the integral action is to make sure that the
process output agrees with the setpoint in steady state. With propor-
tional control, there is normally a control error in steady state. With
integral action, a small positive error will always lead to an increas-
ing control signal, and a negative error will give a decreasing control
| signal no | matter how small | the error is. |     |     |
| --------- | ---------------- | ------------- | --- | --- |
The following simple argument shows that the steady-state error
| willalwaysbezerowithintegral |     | action.Assumethatthesystemisin |     |     |
| ---------------------------- | --- | ------------------------------ | --- | --- |
steady state with a constant control signal (u ) and a constant error
0
| (e ).    |                       | (3.9)   |                    |         |
| -------- | --------------------- | ------- | ------------------ | ------- |
| 0 It     | follows from Equation | that    | the control signal | is then |
| given by |                       | (cid:5) | (cid:6)            |         |
e
|     |     | = + 0     |     |     |
| --- | --- | --------- | --- | --- |
|     | u   | 0 K e 0 t |     |     |
T
i
As long as e (cid:6)= 0, this clearly contradicts the assumption that the
0
control signal u 0 is constant. A controller with integral action will
| always give | zero steady-state | error. |     |     |
| ----------- | ----------------- | ------ | --- | --- |
Integral action can also be visualized as a device that automati-
callyresets thebiasterm u of aproportional controller. This isillus-
b
tratedintheblockdiagraminFigure3.8,whichshowsaproportional
controller witharesetthatisadjustedautomatically. Theadjustment
is made by feeding back a signal, which is a filtered value of the out-
put, to the summing point of the controller. This was actually one of
the early inventions of integral action, or “automatic reset,” as it was
also called.
|     | e   |     | u   |     |
| --- | --- | --- | --- | --- |
|     | K   | Σ   |     |     |
I
1
1+sT
     i
| Figure | 3.8 Implementationofintegralactionaspositivefeedback |     |     |     |
| ------ | ---------------------------------------------------- | --- | --- | --- |
| around | alag.                                                |     |     |     |

| 68  | Chapter        | 3 PID | Control |     |            |          |      |         |
| --- | -------------- | ----- | ------- | --- | ---------- | -------- | ---- | ------- |
| The | implementation |       | shown   | in  | Figure 3.8 | is still | used | by many |
manufacturers. A simple calculation shows that the controller gives
the desired results. The following equations follow from the block
diagram:
u= Ke+
I
dI
|     |     |     |     | +I  | =u  |     |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
T i
dt
| Elimination |     | of u between | these | equations | gives |     |     |     |
| ----------- | --- | ------------ | ----- | --------- | ----- | --- | --- | --- |
dI
|     |     |     |     | +   | = Ke+I |     |     |     |
| --- | --- | --- | --- | --- | ------ | --- | --- | --- |
T i I
dt
Hence,
dI
|     |     |     |     | T   | = Ke |     |     |     |
| --- | --- | --- | --- | --- | ---- | --- | --- | --- |
i
dt
whichshowsthatthecontrollerinFigure3.8is,infact,aPIcontroller.
The properties of integral action are illustrated in Figure 3.9,
which shows a simulation of a system with PI control. The propor-
=
tional gain is constant, K 1 in all curves, and the integral time is
changed. The case T = ∞ corresponds to pure proportional control.
i
| Thiscaseisidenticaltothecase |     |     |     | K   | =1inFigure3.7,wherethesteady |     |     |     |
| ---------------------------- | --- | --- | --- | --- | ---------------------------- | --- | --- | --- |
state error is 50%. The steady state error is removed when T has fi-
i
nite values. For large values of the integration time, the response
creeps slowly towards the setpoint. The approach is approximately
T/KK
| exponential |        | with time | constant  |      | . The             | approach | is  | faster for |
| ----------- | ------ | --------- | --------- | ---- | ----------------- | -------- | --- | ---------- |
|             |        |           |           |      | i p               |          |     |            |
| smaller     | values | of T;     | and it is | also | more oscillatory. |          |     |            |
i
T =1
|     |     |     | i =2 |     |     |     |     |     |
| --- | --- | --- | ---- | --- | --- | --- | --- | --- |
T
i =5
T
| 1   |     |     | i   |     |     |     |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
=∞
T
| 0   |     | i   |     |     |     |     |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| 0   |     | 5   |     | 10  |     | 15  |     | 20  |
T =1
i
| 2   |     | T =2 |     |     |     |     |     |     |
| --- | --- | ---- | --- | --- | --- | --- | --- | --- |
i
T =5
|     |     | i T =∞ |     |     |     |     |     |     |
| --- | --- | ------ | --- | --- | --- | --- | --- | --- |
| 1   |     | i      |     |     |     |     |     |     |
0
| 0   |     | 5   |     | 10  |     | 15  |     | 20  |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
Figure 3.9 Simulation of a closed-loop system with proportional
|          |          |                      |             |      |                               |          | G(s)    | = (s+ |
| -------- | -------- | -------------------- | ----------- | ---- | ----------------------------- | -------- | ------- | ----- |
| and      | integral | control.             | The process |      | transfer                      | function | is      |       |
| 1)−3,    |          |                      |             |      | =                             |          |         |       |
|          | and      | the controller       | gain        | is K | 1. The                        | upper    | diagram | shows |
| setpoint |          | y =1andprocessoutput |             |      | yfordifferentvaluesofintegral |          |         |       |
sp
time T. The lower diagram shows control signal u for different
i
integraltimes.

|     |     |     | 3.3 PID Control | 69  |
| --- | --- | --- | --------------- | --- |
DerivativeAction
The purpose of the derivative action is to improve the closed-loop
stability. The instability mechanism can be described intuitively as
follows.Becauseoftheprocessdynamics,itwilltakesometimebefore
a change in the control variable is noticeable in the process output.
Thus, the control system will be late in correcting for an error. The
action of a controller with proportional and derivative action may be
interpreted as if the control is made proportional to the predicted
process output, where the prediction is made by extrapolating the
error by the tangent to the error curve (see Figure 3.10 ). The basic
| structure | of a PD controller | is      |         |     |
| --------- | ------------------ | ------- | ------- | --- |
|           |                    | (cid:5) | (cid:6) |     |
de(t)
|     |     | u(t)= e(t)+T |     |     |
| --- | --- | ------------ | --- | --- |
|     |     | K            | d   |     |
dt
| A Taylor | series expansion | of e(t+T | ) gives |     |
| -------- | ---------------- | -------- | ------- | --- |
d
de(t)
|     |     | e(t+T )(cid:9) e(t)+T |     |     |
| --- | --- | --------------------- | --- | --- |
|     |     | d                     | d   |     |
dt
The control signal is thus proportional to an estimate of the control
error at time T ahead, where the estimate is obtained by linear
d
extrapolation.
The properties of derivative action are illustrated in Figure 3.11,
which shows a simulation of a system with PID control. Controller
gain and integration time are kept constant, K = 3 and T = 2, and
i
=0wehavepurePIcontrol.The
| derivativetimeT | ischanged.ForT |     |     |     |
| --------------- | -------------- | --- | --- | --- |
|                 | d              | d   |     |     |
closed-loop system isoscillatory withthechosenparameters. Initially
damping increases with increasing derivative time, but decreases
| again when | derivative | time becomes | too large. |     |
| ---------- | ---------- | ------------ | ---------- | --- |
Summary
The PID controller has three terms. The proportional term P corre-
sponds to proportional control. The integral term I gives a control
1.5
e(t)
1
e(t+T )
|     |     |     | d e(t)+T d e( t) |     |
| --- | --- | --- | ---------------- | --- |
0.5 d
d t
0
| 0      |                                                       | 1   | 2   | 3   |
| ------ | ----------------------------------------------------- | --- | --- | --- |
| Figure | 3.10 Interpretationofderivativeactionaspredictivecon- |     |     |     |
trol, where the prediction is obtained by linear extrapolation.

| 70 Chapter | 3 PID Control |     |     |     |     |
| ---------- | ------------- | --- | --- | --- | --- |
=0.1
T d
T =0.7
d
1
T =4.5
| 0    | d       |      |     |     |     |
| ---- | ------- | ---- | --- | --- | --- |
| 0    | 5       |      | 10  | 15  | 20  |
| =0.7 | =4.5    | =0.1 |     |     |     |
| T d  | T d T d |      |     |     |     |
2
−2
| 0           | 5                                               |     | 10  | 15  | 20  |
| ----------- | ----------------------------------------------- | --- | --- | --- | --- |
| Figure 3.11 | Simulationofaclosed-loopsystemwithproportional, |     |     |     |     |
integral and derivative control. The process transfer function is
G(s) = (s+1)−3, the controller gain is K = 3, and the integral
|                                                   | =              |         |       |               | =         |
| ------------------------------------------------- | -------------- | ------- | ----- | ------------- | --------- |
| time is T                                         | i 2. The upper | diagram | shows | setpoint y sp | 1 and     |
| processoutputyfordifferentvaluesofderivativetimeT |                |         |       |               | .Thelower |
d
| diagram | shows controlsignal | u   | for different | derivativetimes. |     |
| ------- | ------------------- | --- | ------------- | ---------------- | --- |
action that is proportional to the time integral of the error. This en-
| suresthatthesteadystateerrorbecomeszero.Thederivative |     |     |     |     | termD |
| ----------------------------------------------------- | --- | --- | --- | --- | ----- |
is proportional to the time derivative of the control error. This term
allowsprediction ofthefutureerror.Therearemanyvariationsofthe
basic PID algorithm that will substantially improve its performance
| and operability.  | They are | discussed | in the  | next section. |     |
| ----------------- | -------- | --------- | ------- | ------------- | --- |
| 3.4 Modifications |          | of        | the PID | Algorithm     |     |
The PID algorithm was given by Equation (3.9) in the previous sec-
tion. This “textbook” algorithm is seldom used in practice because
much better performance is obtained by the modified algorithm dis-
| cussed in this | section. |     |     |     |     |
| -------------- | -------- | --- | --- | --- | --- |
AlternativeRepresentations
| ThePIDalgorithm | given | by(Equation | 3.9)canberepresented |     | bythe |
| --------------- | ----- | ----------- | -------------------- | --- | ----- |
transfer function
|     |     | (cid:5) |     | (cid:6) |     |
| --- | --- | ------- | --- | ------- | --- |
1
|     | G(s)= |     | 1+  | +sT | (3.14) |
| --- | ----- | --- | --- | --- | ------ |
|     |       | K   |     | d   |        |
sT
i
Aslightlydifferentversionismostcommonincommercialcontrollers.

|     |     |     | 3.4 | Modificationsof |     | the PID Algorithm | 71  |
| --- | --- | --- | --- | --------------- | --- | ----------------- | --- |
P
|     |     | e   |     |     |     | u   |     |
| --- | --- | --- | --- | --- | --- | --- | --- |
Σ
I
D
Non-interacting form
D
I
| e   |     |     | Σ   |     |     |     | u   |
| --- | --- | --- | --- | --- | --- | --- | --- |
|     |     |     |     |     |     | P   | Σ   |
Interacting form
Figure 3.12 Interacting and non-interacting form of the PID al-
gorithm.
| This controller | is  | described   | by      |           |         |          |        |
| --------------- | --- | ----------- | ------- | --------- | ------- | -------- | ------ |
|                 |     |             |         | (cid:5)   | (cid:6) |          |        |
|                 |     | (cid:8)(s)= | (cid:8) | 1+ 1      | (1+sT   | (cid:8)) | (3.15) |
|                 |     | G           | K       |           |         |          |        |
|                 |     |             |         | sT(cid:8) |         | d        |        |
i
The two controller structures are presented in block diagram form
in Figure 3.12. The controller given by Equation (3.14) is called non-
(3.15)
| interacting, | and | the one | given | by Equation |     | interacting. | The |
| ------------ | --- | ------- | ----- | ----------- | --- | ------------ | --- |
reason for this nomenclature is that in the controller (3.14) the inte-
graltime T i doesnotinfluence thederivative part,andthederivative
|        |          |           |     |          |      | (see     | (3.14)). |
| ------ | -------- | --------- | --- | -------- | ---- | -------- | -------- |
| time T | does not | influence | the | integral | part | Equation |          |
d
The parts are thus non-interacting. In the interacting controller, the
(cid:8)
derivative time T does influence the integral part. Therefore, the
d
| parts are | interacting. |     |     |     |     |     |     |
| --------- | ------------ | --- | --- | --- | --- | --- | --- |
The interacting controller (3.15) can always be represented as a
(3.14),
| non-interacting | controller |     |     | whose     | coefficients | are given | by  |
| --------------- | ---------- | --- | --- | --------- | ------------ | --------- | --- |
|                 |            |     |     | (cid:8)+T | (cid:8)      |           |     |
(cid:8) T
|     |     |     | K   | = K i | d   |     |     |
| --- | --- | --- | --- | ----- | --- | --- | --- |
T(cid:8)
i
|     |     |     |     | (cid:8)+T | (cid:8) |     |        |
| --- | --- | --- | --- | --------- | ------- | --- | ------ |
|     |     |     | T   | = T       |         |     | (3.16) |
|     |     |     | i   | i         | d       |     |        |
|     |     |     |     | (cid:8)   | (cid:8) |     |        |
T T
|     |     |     | T   | = i               | d   |     |     |
| --- | --- | --- | --- | ----------------- | --- | --- | --- |
|     |     |     | d   | T(cid:8)+T(cid:8) |     |     |     |
i
d
Aninteracting controller oftheform(3.15)thatcorresponds toanon-

| 72          | Chapter | 3 PID      | Control |     |          |      |     |     |
| ----------- | ------- | ---------- | ------- | --- | -------- | ---- | --- | --- |
| interacting |         | controller | (3.14)  | can | be found | only | if  |     |
|             |         |            |         | T   | ≥4T      |      |     |     |
|             |         |            |         |     | i        | d    |     |     |
Then,
|     |     |     |     | (cid:2) | (cid:7) |     | (cid:3) |     |
| --- | --- | --- | --- | ------- | ------- | --- | ------- | --- |
K
|     |     |     | K (cid:8) = | 1+  | 1−4T |     | /T  |     |
| --- | --- | --- | ----------- | --- | ---- | --- | --- | --- |
|     |     |     |             |     |      | d   | i   |     |
2
|     |     |     |     | (cid:2) |     |     | (cid:3) |     |
| --- | --- | --- | --- | ------- | --- | --- | ------- | --- |
(cid:7)
|     |     |     | (cid:8) = | T i 1+ | 1−4T |     | /T  | (3.17) |
| --- | --- | --- | --------- | ------ | ---- | --- | --- | ------ |
T
|     |     |     | i   | 2       |         | d   | i       |     |
| --- | --- | --- | --- | ------- | ------- | --- | ------- | --- |
|     |     |     |     | (cid:2) | (cid:7) |     | (cid:3) |     |
T
|     |     |     | T (cid:8) = | i 1− | 1−4T |     | /T  |     |
| --- | --- | --- | ----------- | ---- | ---- | --- | --- | --- |
|     |     |     | d           |      |      | d   | i   |     |
2
The non-interacting controller given by Equation (3.14) is more gen-
eral, and we will use that in the future. It is, however, claimed that
| the | interacting | controller |     | is easier | to  | tune manually. |     |     |
| --- | ----------- | ---------- | --- | --------- | --- | -------------- | --- | --- |
There is also an historical reason for preferring the interacting
controller. Early pneumatic controllers were easier to build using
the interacting form. When the controller manufacturers changed
technology from pneumatic to analog electric and, finally, to digital
technique, they kept the interactive form. Therefore, the interacting
| form | is most | common | among | single-loop |     | controllers. |     |     |
| ---- | ------- | ------ | ----- | ----------- | --- | ------------ | --- | --- |
Itisimportanttokeepinmindthatdifferentcontrollersmayhave
different structures. It means that if a controller in a certain control
loop is replaced by another type of controller, the controller parame-
ters may have to be changed. Note, however, that the interacting and
the non-interacting forms are different only when both the I and the
D parts of the controller are used. If we only use the controller as
a P, PI, or PD controller, the two forms are equivalent. Yet another
| representation |     | of the | PID | algorithm |     | is given | by  |     |
| -------------- | --- | ------ | --- | --------- | --- | -------- | --- | --- |
k
|     |     |     |     | (cid:8)(cid:8)(s)= | k+  | i +sk |     | (3.18) |
| --- | --- | --- | --- | ------------------ | --- | ----- | --- | ------ |
|     |     |     |     | G                  |     | d     |     |        |
s
The parameters are related to the parameters of standard form
through
k=
K
= K
k
|     |     |     |     |     | i T |     |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
i
|     |     |     |     | k   | = KT |     |     |     |
| --- | --- | --- | --- | --- | ---- | --- | --- | --- |
|     |     |     |     |     | d    | d   |     |     |
The representation (3.18)is equivalent to the standard form, but the
parametervaluesarequitedifferent.Thismaycausegreatdifficulties
foranyonewhoisnotawareofthedifferences, particularly ifparame-
ter1/k
|     | i iscalledintegraltimeand |     |     |     | k d | derivative | time.Theformgiven |     |
| --- | ------------------------- | --- | --- | --- | --- | ---------- | ----------------- | --- |
by Equation (3.18) is often useful in analytical calculations because
the parameters appear linearly. The representation also has the ad-
vantage that it is possible to obtain pure proportional, integral, or
| derivative |     | action by | finite | values | of the | parameters. |     |     |
| ---------- | --- | --------- | ------ | ------ | ------ | ----------- | --- | --- |

|     |     |     | 3.4 | Modificationsof |     | the PID Algorithm | 73  |
| --- | --- | --- | --- | --------------- | --- | ----------------- | --- |
Summarizing we have thus found that there are three different
| forms of | the PID  | controller.        |       |             |             |             |         |
| -------- | -------- | ------------------ | ----- | ----------- | ----------- | ----------- | ------- |
| •        |          |                    |       |             |             |             | (3.14). |
| The      | standard | or non-interacting |       |             | form given  | by Equation |         |
| •        |          |                    |       |             |             | (3.15).     |         |
| The      | series   | or interacting     |       | form given  | by Equation |             |         |
| •        |          |                    |       |             | (3.18).     |             |         |
| The      | parallel | form               | given | by Equation |             |             |         |
The standard form is sometimes called the ISA algorithm, or the
idealalgorithm.Theproportional,integral,andderivativeactionsare
noninteracting in the time domain. This algorithm admits complex
zeros,whichisusefulwhencontrollingsystemswithoscillatorypoles.
The series form is also called the classical form. This represen-
tation is obtained naturally when a controller is implemented as an
analog device based on a pneumatic force balance system. The name
classicalreflectsthis.Theseriesformhasanattractiveinterpretation
in the frequency domain because the zeros correspond to the inverse
values of the derivative and integral times. All zeros of the controller
arereal.Pureintegralorproportionalactioncannotbeobtainedwith
finite values of the controller parameters. Most controllers use this
form.
The parallel form is the most general form, because pure pro-
portional or integral action can be obtained with finite parameters.
The controller canalso have complex zeros. Inthis way it is the most
flexible form. However, itis alsotheform wherethe parameters have
| little physical |     | interpretation. |     |     |     |     |     |
| --------------- | --- | --------------- | --- | --- | --- | --- | --- |
SetpointWeighting
AcommonformofacontrolsystemisshowninFigure3.6.Thesystem
ischaracterizedbyforminganerrorthatisthedifferencebetweenthe
setpoint and the process output. The controller generates a control
signal by operating on the error. This control signal is then applied
totheprocess. Suchasystem iscalleda“system witherrorfeedback”
because the controller operates on the error signal. A more flexible
structure is obtained by treating the setpoint and the process output
| separately. | A   | PID-controller |         | of this form | is given | by      |        |
| ----------- | --- | -------------- | ------- | ------------ | -------- | ------- | ------ |
|             |     |                | (cid:5) | (cid:1)t     |          | (cid:6) |        |
|             |     |                |         | 1            |          | de      |        |
|             |     | u(t)=          | K e     | + e(s)ds+T   |          | d       | (3.19) |
|             |     |                | p       |              |          | d       |        |
|             |     |                |         | T i          |          | dt      |        |
0
| where the | error | in the            | proportional | part   | is  |     |        |
| --------- | ----- | ----------------- | ------------ | ------ | --- | --- | ------ |
|           |       |                   |              | =by    | −y  |     | (3.20) |
|           |       |                   |              | e p sp |     |     |        |
| and the   | error | in the derivative |              | part   | is  |     |        |
|           |       |                   |              | e =cy  | −y  |     | (3.21) |
|           |       |                   |              | d sp   |     |     |        |

| 74 Chapter | 3   | PID | Control |     |     |     |
| ---------- | --- | --- | ------- | --- | --- | --- |
The error in the integral part must be the true control error
|     |     |     | e= −y |     |     |     |
| --- | --- | --- | ----- | --- | --- | --- |
y
sp
to avoid steady-state control errors. The controllers obtained for dif-
ferent values of b and c will respond to load disturbances and mea-
surementnoiseinthesameway.Theresponsetosetpointchangeswill
depend,however,onthevaluesofbandc.ThisisillustratedinFigure
3.13,whichshowstheresponseofaPIDcontrollertosetpointchanges,
load disturbances, and measurement errors for different values of b.
The figure shows clearly the effect of changing b. The overshoot for
=
setpoint changes is smallest for b 0, which is the case where the
reference is only introduced in the integral term, and increases with
increasing b. Notice that a simulation like the one in Figure 3.13 is
usefulinordertogiveaquickassessmentoftheresponsesofaclosed-
loopsystemtosetpoint changes,loaddisturbances, andmeasurement
errors.
The parameter c is normally chosen equal to zero to avoid large
transientsinthecontrolsignalduetosuddenchangesinthesetpoint.
An exception is when the controller is the secondary controller in a
cascade coupling (see Section 7.2). In this case, the setpoint changes
smoothly, because it is given by the primary controller output. No-
tice that if the integral action is implemented with positive feedback
around a lag as in Figure 3.8, the parameter bis equal to one.
|     |            |      | b=0 c=0 |              |        |         |
| --- | ---------- | ---- | ------- | ------------ | ------ | ------- |
| The | controller | with | and     | is sometimes | called | an I-PD |
controller,andthecontrollerwithb=1andc=0issometimescalled
aPI-Dcontroller.WeprefertosticktothegenericuseofPIDandgive
| theparameters |                 | band | c,therebymakingasmallcontribution |     |     | towards |
| ------------- | --------------- | ---- | --------------------------------- | --- | --- | ------- |
| reduction     | of three-letter |      | abbreviations.                    |     |     |         |
In general, a control system has many different requirements.
It should have good transient response to setpoint changes, and it
| shouldrejectloaddisturbances |     |     | andmeasurementnoise.Forasystem |     |     |     |
| ---------------------------- | --- | --- | ------------------------------ | --- | --- | --- |
with error feedback only, an attempt is made to satisfy all demands
with the same mechanism. Such systems are called one-degree of
freedom systems. By having different signal paths for the setpoint
and the process output (two-degree of freedom systems), there is
moreflexibilitytosatisfythedesigncompromise.Thisiscarriedmuch
| further in        | more | sophisticated | control systems.          |     |        |          |
| ----------------- | ---- | ------------- | ------------------------- | --- | ------ | -------- |
| Intheblockdiagram |      |               | inFigure3.6,thecontroller |     | output | isgener- |
|                   |      | e=            | −y.                       |     |        |          |
ated from the error y sp Notice that this diagram is no longer
valid when the control law given by Equation (3.19) and the error
definitions (3.20) and (3.21) are used. A block diagram for a system
| with PID | control | is now | given by Figure   | 3.14.    |          |          |
| -------- | ------- | ------ | ----------------- | -------- | -------- | -------- |
| Notice   | that    | the    | transfer function | from the | setpoint | y to the |
sp

|          |               | 3.4    | Modifications |     | ofthe PID Algorithm | 75  |
| -------- | ------------- | ------ | ------------- | --- | ------------------- | --- |
| Setpoint | y and process | output | y             |     |                     |     |
sp
1
0.5 b=1
b=0.5
b=0
0
| 0       | 10       |     | 20  |     | 30  | 40  |
| ------- | -------- | --- | --- | --- | --- | --- |
| Control | signal u |     |     |     |     |     |
b=1
2
b=0.5
b=0
0
| 0                | 10  |                   | 20  |       | 30  | 40  |
| ---------------- | --- | ----------------- | --- | ----- | --- | --- |
| Load disturbance |     | l and measurement |     | noise | n   |     |
|                  |     |                   | l   |       | n   |     |
−0.5
−1
| 0   | 10  |     | 20  |     | 30  | 40  |
| --- | --- | --- | --- | --- | --- | --- |
b=1
| Proportional | part | for |     |     |     |     |
| ------------ | ---- | --- | --- | --- | --- | --- |
3
1
−1
| 0            | 10      |     | 20  |     | 30  | 40  |
| ------------ | ------- | --- | --- | --- | --- | --- |
| Integralpart | for b=1 |     |     |     |     |     |
3
1
−1
| 0   | 10  |     | 20  |     | 30  | 40  |
| --- | --- | --- | --- | --- | --- | --- |
b=1
| Derivative | part for |     |     |     |     |     |
| ---------- | -------- | --- | --- | --- | --- | --- |
3
1
−1
| 0           | 10                                             |     | 20  |     | 30  | 40  |
| ----------- | ---------------------------------------------- | --- | --- | --- | --- | --- |
| Figure 3.13 | Theresponsetosetpointchanges,loaddisturbances, |     |     |     |     |     |
and measurement errors for different values of setpoint weighting
| b.Thelowerdiagramsshowtheproportional, |                       |     |     |     | integral,andderiva- |     |
| -------------------------------------- | --------------------- | --- | --- | --- | ------------------- | --- |
| tive parts                             | of the controlsignal. |     |     |     |                     |     |

| 76 Chapter | 3 PID | Control |     |     |     |
| ---------- | ----- | ------- | --- | --- | --- |
y
  sp
G
|     |     |    ff |     |         |     |
| --- | --- | ----- | --- | ------- | --- |
|     |     |       | u   |         | y   |
|     |     | G     | Σ   |         |     |
|     |     |     c |     | Process |     |
−1
| Figure         | 3.14 BlockdiagramofasimplefeedbackloopwhithaPID |         |     |         |     |
| -------------- | ----------------------------------------------- | ------- | --- | ------- | --- |
| controller     | having atwo-degree-of-freedomstructure.         |         |     |         |     |
| control signal | u is given                                      | by      |     |         |     |
|                |                                                 | (cid:5) |     | (cid:6) |     |
1
|     |     | G = K | b+ +csT |     |     |
| --- | --- | ----- | ------- | --- | --- |
|     |     | ff    |         | d   |     |
sT i
and the transfer function from the process variable y to the control
| variable | u is given by |         |     |         |     |
| -------- | ------------- | ------- | --- | ------- | --- |
|          |               | (cid:5) |     | (cid:6) |     |
1
|     |     | G = K | 1+ +sT |     |     |
| --- | --- | ----- | ------ | --- | --- |
|     |     | c     |        | d   |     |
sT i
| and that        | the transfer   | functions | are different. |     |     |
| --------------- | -------------- | --------- | -------------- | --- | --- |
| Limitationofthe | DerivativeGain |           |                |     |     |
The derivative action may result in difficulties, if there is high-
| frequency | measurement | noise. | A sinusoidal | measurement | noise |
| --------- | ----------- | ------ | ------------ | ----------- | ----- |
|           |             | n=     | a sinωt      |             |       |
gives the following contribution to the derivative term of the control
signal:
dn
|     |     | =      | =   | ωcosωt |     |
| --- | --- | ------ | --- | ------ | --- |
|     | u   | n KT d | aKT | d      |     |
dt
The amplitude of the control signal can thus be arbitrarily large if
the noise has a sufficiently high frequency (ω). The high-frequency
gainofthederivative termisthereforelimitedtoavoidthisdifficulty.
| This can | be done by | implementing | the derivative | term | as     |
| -------- | ---------- | ------------ | -------------- | ---- | ------ |
|          |            | T            | dD             | dy   |        |
|          |            | =− d         | −              |      | (3.22) |
|          |            | D            | KT             | d    |        |
|          |            | N            | dt             | dt   |        |
It follows from this equation that the modified derivative term can
| be represented | as follows: |     |     |     |     |
| -------------- | ----------- | --- | --- | --- | --- |
sKT
|     |     | D =− | d       | y   |     |
| --- | --- | ---- | ------- | --- | --- |
|     |     |      | 1+sT /N |     |     |
d

3.4 Modifications of the PID Algorithm 77
Themodificationcanbeinterpreted astheidealderivative filteredby
afirst-ordersystem withthetimeconstant T /N.Theapproximation
d
acts as a derivative for low-frequency signal components. The gain,
however, islimited to KN.Thismeans thathigh-frequency measure-
ment noise is amplified at most by a factor KN. Typical values of N
are 8 to 20.
Error-SquaredControllers
In the standard form of PID control, the control error enters linearly
inthecontrolalgorithm,seeEquation(3.9).Itissometimes desirable
to have higher controller gains when the control error is large, and
smaller gains when the control error is small. One common way of
obtaining this property is to use the square of the control error, i.e.,
the control error is substituted by
e = e(cid:2)e(cid:2)
squared
The square of the error is mostly used only in the proportional term,
sometimes in the integral term, but seldom in the derivative term.
Onereasonforusingerror-squaredcontrollers istoreducetheef-
fectsoflow-frequency disturbances inthemeasurement signal. These
disturbances cannot be filtered out, but the use of error-squared con-
trol gives a small amplification of the noise when the control error is
small, and an effective control when the control error is large.
Another application of error-squared controllers is surge tank
control. Here, the main control objective is to keep the control signal
smooth. Onthe other hand, the level must not deviate toomuch from
the setpoint. This is obtained efficiently by error-squared control.
SpecialControllerOutputs
The inputs and outputs of a controller are normally analog signals,
typically 0–20 mA or 4–20 mA. The main reason for using 4 mA
instead of 0 mA as the lower limit is that many transmitters are
designed for two-wire connection. This means that the same wire is
used for both driving the sensor and transmitting the information
from the sensor. It would not be possible to drive the sensor with
a current of 0 mA. The main reason for using current instead of
voltage is to avoid the influence of voltage drops along the wire due
to resistance in the (perhaps long) wire.
Thyristors and Triacs
In temperature controllers it is common practice to integrate the
power amplifier with the controller. The power amplifier could be a

| 78 Chapter | 3 PID | Control |     |     |
| ---------- | ----- | ------- | --- | --- |
thyristor oratriac. Withathyristor, anACvoltage isswitched tothe
load at a given angle of the AC voltage. Since the relation between
angle and power is nonlinear, it is crucial to use a transformation to
maintain a linear relationship. A triac is also a device that imple-
ments switching of an AC signal, but only at the zero crossing. Such
| a device | is similar to    | a pulse output. |     |     |
| -------- | ---------------- | --------------- | --- | --- |
| Pulse    | Width Modulation |                 |     |     |
Insomecases,suchaswiththetriac,thereisanextremequantization
in the sense that the actuator only accepts two values, on or off. In
such a case, a cycle time T is specified, and the controller gives a
cycle
| pulse with | width |     |     |     |
| ---------- | ----- | --- | --- | --- |
u(t)−u
|     |     | (t)=    | min      | (3.23) |
| --- | --- | ------- | -------- | ------ |
|     |     | T       | T        |        |
|     |     | pulse u | −u cycle |        |
max min
A similar, but slightly different, situation occurs when the actuator
has three levels: max, min, and zero. A typical example is a motor-
T
cycle
u
100%
0%
Time
e
100%
0%
Time
| Figure | 3.15 Illustrationofcontrolleroutputbasedonpulsewidth |     |     |     |
| ------ | ---------------------------------------------------- | --- | --- | --- |
modulation.

|     |     | 3.4 | Modificationsof | the | PID Algorithm | 79  |
| --- | --- | --- | --------------- | --- | ------------- | --- |
driven valve where the motor can stand still, go forward, or go back-
ward.
Figure 3.15 illustrates the pulse width modulation. The figure
showstheoutput fromaPcontroller withpulse widthmodulation for
| different values | of the | control | error. |     |     |     |
| ---------------- | ------ | ------- | ------ | --- | --- | --- |
VelocityAlgorithms
The algorithms described so far are called positional algorithms be-
cause the output of the algorithms is the control variable. In certain
cases the control system is arranged in such a way that the control
signal is driven directly byanintegrator, e.g.,a motor. Itis then nat-
ural to arrange the algorithm in such a way that it gives the velocity
of the control variable. The control variable is then obtained by in-
tegrating its velocity. An algorithm of this type is called a velocity
algorithm. A block diagram of a velocity algorithm for a PID con-
troller is shown in Figure 3.16. Velocity algorithms were commonly
used in many early controllers that were built around motors. In sev-
eral cases, the structure was retained by the manufacturers when
technology waschangedinordertomaintain functional compatibility
with older equipment. Another reason is that many practical issues,
likewind-upprotection andbumpless parameter changes, areeasyto
implement using the velocity algorithm. This is discussed further in
Sections 3.5 and 3.6. In digital implementations velocity algorithms
| are also called | incremental |          | algorithms. |     |     |     |
| --------------- | ----------- | -------- | ----------- | --- | --- | --- |
| A Difficulty    | with        | Velocity | Algorithms  |     |     |     |
A velocity algorithm cannot be used directly for a controller without
integral action, because such a controller cannot keep the stationary
s2KT
|  e d |     |         | d   |     |     |     |
| ---- | --- | ------- | --- | --- | --- | --- |
|      |     | +sT d/N |     |     |     |     |
 1
External
|     |     |     |     | du  | integrator |     |
| --- | --- | --- | --- | --- | ---------- | --- |
d  t
| e   |     | sK  |     | Σ   | 1   | u   |
| --- | --- | --- | --- | --- | --- | --- |
  p
s
| e   |     | K   |     |     |     |     |
| --- | --- | --- | --- | --- | --- | --- |
T
i

Figure 3.16 Block diagram of a PID algorithmin velocity form.

| 80 Chapter | 3   | PID | Control |     |     |
| ---------- | --- | --- | ------- | --- | --- |
A
e u
|     |     | K   |     | s   | 1   |
| --- | --- | --- | --- | --- | --- |
s
B
e u
|     |     |     |     | s Σ | 1   |
| --- | --- | --- | --- | --- | --- |
K
s
a
−
+
Σ
+
u
  b
Figure 3.17 Illustrates the difficulty with a proportional con-
|         |             |      | (A) |                  | (B). |
| ------- | ----------- | ---- | --- | ---------------- | ---- |
| troller | in velocity | form |     | and away toavoid | it   |
value.ThiscanbeunderstoodfromtheblockdiagraminFigure3.17A,
which shows a proportional controller in velocity form. Stationarity
can be obtained for any value of the control error e, since the output
from the derivation block is zero for any constant input. The problem
can be avoided with the modification shown in Figure 3.17B. Here,
u= Ke+u
| stationarity | is  | only obtained |     | when | .   |
| ------------ | --- | ------------- | --- | ---- | --- |
b
IfasampledPIDcontrollerisused,asimpleversionofthemethod
illustrated in figure 3.17B is obtained by implementing the P con-
troller as
|     | ∆u(t)=u(t)−u(t−h)= |     |     | Ke(t)+u | −u(t−h) |
| --- | ------------------ | --- | --- | ------- | ------- |
b
| where h | is the     | sampling | period. |     |     |
| ------- | ---------- | -------- | ------- | --- | --- |
| 3.5     | Integrator |          | Windup  |     |     |
Although many aspects of a control system can be understood based
on linear theory, some nonlinear effects must be accounted for. All
actuators have limitations: a motor has limited speed, a valve cannot
be more than fully opened or fully closed, etc. For a control system
with a wide range of operating conditions, it may happen that the
control variable reaches the actuator limits. When this happens the
feedback loop is broken and the system runs asan open loop because
the actuator will remain at its limit independently of the process

|     |     |     | 3.5 Integrator | Windup | 81  |
| --- | --- | --- | -------------- | ------ | --- |
output. If a controller with integrating action is used, the error will
continue to be integrated. This means that the integral term may
become very large or, colloquially, it “winds up”. It is then required
thattheerrorhasopposite signforalong periodbefore things return
tonormal.Theconsequenceisthatanycontrollerwithintegralaction
| may give | large transients | when the actuator | saturates. |     |     |
| -------- | ---------------- | ----------------- | ---------- | --- | --- |
| EXAMPLE  | 3.1 Illustration | of integrator     | windup     |     |     |
The wind-up phenomenon is illustrated in Figure 3.18, which shows
control of an integrating process with a PI controller. The initial set-
point change is solargethat the actuator saturates atthe high limit.
The integral term increases initially because the error is positive; it
reaches its largest value at time t=10 when the error goes through
zero. The output remains saturated atthis point because of the large
value of theintegral term.Itdoes not leave thesaturation limit until
the error has been negative for a sufficiently long time to let the in-
tegral part come down to a small level. Notice that the control signal
bouncesbetweenitslimitsseveraltimes.Theneteffectisalargeover-
shootandadampedoscillationwherethecontrolsignalflipsfromone
extreme to the other as in relay oscillation. The output finally comes
so close to the setpoint that the actuator does not saturate. The sys-
| tem then | behaves linearly | and settles. |     |     |     |
| -------- | ---------------- | ------------ | --- | --- | --- |
| 2        | y                |              |     |     |     |
1
y
sp
0
| 0   | 20  | 40  | 60  |     | 80  |
| --- | --- | --- | --- | --- | --- |
0.1
u
−0.1
| 0   | 20  | 40  | 60  |     | 80  |
| --- | --- | --- | --- | --- | --- |
I
2
−2
| 0          | 20                                             | 40  | 60  |     | 80  |
| ---------- | ---------------------------------------------- | --- | --- | --- | --- |
| Figure3.18 | Illustrationofintegratorwindup.Thediagramsshow |     |     |     |     |
processoutput y,setpoint y ,controlsignalu,andintegralpart I.
sp

82 Chapter 3 PID Control
Integrator windup may occur in connection with large setpoint
changes orit maybecaused bylargedisturbances or equipment mal-
functions. Windupcanalsooccurwhenselectors areusedsothatsev-
eral controllers are driving one actuator. In cascade control, windup
may occur in the primary controller when the secondary controller
is switched to manual mode, uses its local setpoint, or if its control
signal saturates. See Section 7.2.
The phenomenon of windup was well known to manufacturers
of analog controllers who invented several tricks to avoid it. They
weredescribedunder labelslikepreloading, batchunit,etc.Although
the problem was well understood, there were often limits imposed
because of the analog implementations. The ideas were often kept
as trade secrets and not much spoken about. The problem of windup
was rediscovered when controllers were implemented digitally and
several methods to avoid windup were presented in the literature. In
the following section we describe several of the ideas.
SetpointLimitation
One way to try to avoid integrator windup is to introduce limiters
on the setpoint variations so that the controller output will never
reach the actuator bounds. This often leads to conservative bounds
and limitations on controller performance. Further, it does not avoid
windup caused by disturbances.
IncrementalAlgorithms
Intheearlyphasesoffeedbackcontrol,integralactionwasintegrated
with the actuator by having a motor drive the valve directly. In this
casewindupishandledautomaticallybecauseintegrationstopswhen
the valve stops. When controllers were implemented by analog tech-
niques, and later with computers, many manufacturers used a con-
figuration that was an analog of the old mechanical design. This led
to the so-called velocity algorithms discussed in Section 3.4. In this
algorithm the rate of change of the control signal is first computed
and then fed to an integrator. In some cases this integrator is a mo-
tor directly connected to the actuator. In other cases the integrator
is implemented internally in the controller. With this approach it is
easy to handle mode changes and windup. Windup is avoided by in-
hibiting the integration whenever the output saturates. This method
is equivalent to back-calculation, which is described below. If the ac-
tuator output is not measured, a model that computes the saturated
output can be used. It is also easy to limit the rate of change of the
control signal.

|     |     |     |     | 3.5 | Integrator | Windup | 83  |
| --- | --- | --- | --- | --- | ---------- | ------ | --- |
Back-CalculationandTracking
Back-calculation works as follows: When the output saturates, the
integral is recomputed so that its new value gives an output at the
saturationlimit.Itisadvantageous nottoresettheintegratorinstan-
| taneously | but dynamically | with | a time | constant | T.  |     |     |
| --------- | --------------- | ---- | ------ | -------- | --- | --- | --- |
t
Figure 3.19 shows a block diagram of a PID controller with anti-
windup based on back-calculation. The system has an extra feedback
path that is generated by measuring the actual actuator output and
forming an error signal (e ) as the difference between the output of
s
the controller (v) and the actuator output (u). Signal e is fed to the
s
1/T.
| input of | the integrator | through | gain |     | The signal | is  | zero when |
| -------- | -------------- | ------- | ---- | --- | ---------- | --- | --------- |
t
A
–y
 K T d s
Actuator
|  e =r−y |     |     |     |     | v   |     | u   |
| ------- | --- | --- | --- | --- | --- | --- | --- |
|         |     | K   |     |     | Σ   |     |     |
|         |     |     |     |     |     | –   | +   |
|         | K   | Σ   |     |     |     | Σ   |     |
1
|     | T    |     |   s |     |     |     |     |
| --- | ---- | --- | --- | --- | --- | --- | --- |
|     |    i |     |     |     |     |     |     |
e
  s
1
    t T
B
–y
|     | KT  | s   |     |     |     |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- |
d
Actuator
|     |     |     |     |     | model | Actuator |     |
| --- | --- | --- | --- | --- | ----- | -------- | --- |
 e =r−y
Σ
K
|     |     |     |     |     | – + |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- |
|     | K   |     | 1   |     |     |     |     |
|     |     | Σ   |     |     | Σ   |     |     |
|     | T   |     |   s |     |     |     |     |
|     | i   |     |     |     |     |     |     |
e
|     |     |     | 1   |     |   s |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- |
T
    t
| Figure | 3.19 Controller | with | anti-windup. |     | A system | where | the |
| ------ | --------------- | ---- | ------------ | --- | -------- | ----- | --- |
actuatoroutputismeasuredisshowninAandasystemwherethe
actuator output is estimated from a mathematicalmodel is shown
in B.

| 84 Chapter | 3 PID | Control |     |     |     |
| ---------- | ----- | ------- | --- | --- | --- |
thereisnosaturation. Thus, itwill not have anyeffect onthenormal
operation when the actuator does not saturate. When the actuator
saturates, the signal e is different from zero. The normal feedback
s
path around the process is broken because the process input remains
constant. There is, however, a feedback path around the integrator.
Because of this, the integrator output is driven towards a value such
that the integrator input becomes zero. The integrator input is
|     |     |     | 1 K |     |     |
| --- | --- | --- | --- | --- | --- |
+
|           |             |               | e s | e   |     |
| --------- | ----------- | ------------- | --- | --- | --- |
|           |             |               | T T |     |     |
|           |             |               | t i |     |     |
| where eis | the control | error. Hence, |     |     |     |
KT t
|     |     | e   | =−  | e   |     |
| --- | --- | --- | --- | --- | --- |
|     |     |     | s T |     |     |
i
=u−v,
| in steady state. | Since | e s | it follows | that |     |
| ---------------- | ----- | --- | ---------- | ---- | --- |
KT
|     |     | v=u | +   | t   |     |
| --- | --- | --- | --- | --- | --- |
|     |     |     | lim | e   |     |
T
i
where u is the saturating value of the control variable. Since the
lim
signals eandu lim havethesamesign,itfollowsthatvisalwayslarger
| thanu inmagnitude.Thispreventstheintegratorfromwindingup. |     |     |     |     |     |
| --------------------------------------------------------- | --- | --- | --- | --- | --- |
lim
y
sp
1
y
0.5
0
| 0   |     | 10  |     | 20  | 30  |
| --- | --- | --- | --- | --- | --- |
0.15
u
0.05
−0.05
| 0   |     | 10  |     | 20  | 30  |
| --- | --- | --- | --- | --- | --- |
0
I
−0.4
−0.8
| 0   |     | 10  |     | 20  | 30  |
| --- | --- | --- | --- | --- | --- |
Figure 3.20 Controller with anti-windup applied to the system
of Figure 3.18. The diagrams show process output y, setpoint y ,
sp
| controlsignal | u,  | and integralpart | I.  |     |     |
| ------------- | --- | ---------------- | --- | --- | --- |

|     |     |     |     | 3.5 | Integrator | Windup | 85  |
| --- | --- | --- | --- | --- | ---------- | ------ | --- |
The rate at which the controller output is reset is governed by the
| feedbackgain,1/T,whereT |     |     | canbeinterpreted |     | asthetimeconstant, |     |     |
| ----------------------- | --- | --- | ---------------- | --- | ------------------ | --- | --- |
|                         | t   |     | t                |     |                    |     |     |
which determines how quickly the integral is reset. We call this the
| tracking | time constant. |     |     |     |     |     |     |
| -------- | -------------- | --- | --- | --- | --- | --- | --- |
It frequently happens that the actuator output cannot be mea-
sured. The anti-windup scheme just described can be applied by in-
corporating a mathematical model of the saturating actuator, as is
| illustrated | in Figure  | 3.19B. |         |      |              |      |       |
| ----------- | ---------- | ------ | ------- | ---- | ------------ | ---- | ----- |
| Figure      | 3.20 shows | what   | happens | when | a controller | with | anti- |
windup isapplied tothesystem simulated inFigure3.18.Notice that
the output of the integrator is quickly reset to a value such that the
controller output is at the saturation limit, and the integral has a
negative value during the initial phase when the actuator is satu-
rated. This behavior is drastically different from that in Figure 3.18,
where the integral has a positive value during the initial transient.
Also notice the drastic improvement in performance compared to the
| ordinary | PI controller | used | in Figure | 3.18. |     |     |     |
| -------- | ------------- | ---- | --------- | ----- | --- | --- | --- |
The effect of changing the values of the tracking time constant
is illustrated in Figure 3.21. From this figure, it may thus seem ad-
vantageous to always choose a very small value of the time constant
becausetheintegrator isthenresetquickly.However, somecaremust
be exercised when introducing anti-windup in systems with deriva-
tive action. If the time constant is chosen too small, spurious errors
can cause saturation of the output, which accidentally resets the in-
tegrator. The tracking time constant T should be larger than T and
|          |                                          |     |     | t   |     |            | d   |
| -------- | ---------------------------------------- | --- | --- | --- | --- | ---------- | --- |
| smalle√r | than T .Aruleofthumbthathasbeensuggested |     |     |     |     | istochoose |     |
i
=
| T TT | .   |     |     |     |     |     |     |
| ---- | --- | --- | --- | --- | --- | --- | --- |
| t    | i d |     |     |     |     |     |     |
=
|     | y   |     | T t 3 |     |     |     |     |
| --- | --- | --- | ----- | --- | --- | --- | --- |
|     | sp  |     | =     |     |     |     |     |
|     |     |     | T t   | 2   |     |     |     |
1
|     |     |     | =0.1,T | =1  |     |     |     |
| --- | --- | --- | ------ | --- | --- | --- | --- |
T
|     |     |     | t   | t   |     |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- |
0
| 0   |     | 10  |     | 20  |     |     | 30  |
| --- | --- | --- | --- | --- | --- | --- | --- |
=3
| 0.1 |        |     | T    |     |     |     |     |
| --- | ------ | --- | ---- | --- | --- | --- | --- |
|     |        |     | t =2 |     |     |     |     |
|     | T =0.1 |     | T t  |     |     |     |     |
t
| 0   | T   | =1  |     |     |     |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- |
t
−0.1
| 0   |     | 10  |     | 20  |     |     | 30  |
| --- | --- | --- | --- | --- | --- | --- | --- |
Figure 3.21 The step response of the system in Figure 3.18 for
different values of the tracking time constant T. t The upper curve
shows process ouput yand setpoint y , and the lower curveshows
sp
| controlsignal | u.  |     |     |     |     |     |     |
| ------------- | --- | --- | --- | --- | --- | --- | --- |

| 86  | Chapter | 3 PID | Control |     |     |     |     |     |
| --- | ------- | ----- | ------- | --- | --- | --- | --- | --- |
y
|     |    sp |     |     |     |     | P   |     |     |
| --- | ----- | --- | --- | --- | --- | --- | --- | --- |
|     |       | b   |     | Σ   | K   |     |     |     |
|     | y     |     |     |     | sKT | D   |     |     |
|     |       |     |     |     |     | d   | Σ   |     |
−1
|     |     |     |     |     |   1 +sT d/N |     |     |     |
| --- | --- | --- | --- | --- | ----------- | --- | --- | --- |

|     | e   | K   |     |     | 1      |     | I   | v   |
| --- | --- | --- | --- | --- | ------ | --- | --- | --- |
|     |     |     |     | Σ   |        |     | Σ   |     |
|     |     | T   |     |     |   s    |     |     |     |
i
1
T
t
+ –
w
Σ
y
|     |     | sp  |     | SP  |     |     |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
v
y
|     |     |     |     | MV PID |     |     |     |     |
| --- | --- | --- | --- | ------ | --- | --- | --- | --- |
w
TR
|                 | Figure 3.22 | Blockdiagramandsimplified |                |         |     | representationofPID |     |     |
| --------------- | ----------- | ------------------------- | -------------- | ------- | --- | ------------------- | --- | --- |
|                 | module with | tracking                  |                | signal. |     |                     |     |     |
| Controllerswith |             |                           | a TrackingMode |         |     |                     |     |     |
A controller with back-calculation can be interpreted as having two
modes: the normal control mode, when it operates like an ordinary
controller, and a tracking mode, when the integrator is tracking so
that it matches given inputs and outputs. Since a controller with
tracking can operate in two modes, we may expect that it is nec-
essary to have a logical signal for mode switching. However, this is
not necessary, because tracking is automatically inhibited when the
tracking signal w is equal to the controller output. This can be used
with great advantage when building up complex systems with selec-
| tors | and cascade | control. |     |              |      |            |     |             |
| ---- | ----------- | -------- | --- | ------------ | ---- | ---------- | --- | ----------- |
|      | Figure 3.22 | shows    |     | a PID module | with | a tracking |     | signal. The |
module has three inputs: the setpoint, the measured output, and a
tracking signal. The new input TRiscalled a tracking signal because
the controller output will follow this signal. Notice that tracking is
w=v.
| inhibited | when             |     | Using | the module      | the | system | shown | in Figure |
| --------- | ---------------- | --- | ----- | --------------- | --- | ------ | ----- | --------- |
| 3.19      | can be presented |     | as    | shown in Figure |     | 3.23.  |       |           |

|     |     |     |     |     | 3.5 Integrator | Windup | 87  |
| --- | --- | --- | --- | --- | -------------- | ------ | --- |
A
SP
MV
|     |     |     | PID |     | Actuator |     |     |
| --- | --- | --- | --- | --- | -------- | --- | --- |
TR
B
Actuator model
SP
|     |     |     | v   |     | u        |     |     |
| --- | --- | --- | --- | --- | -------- | --- | --- |
|     | MV  |     |     |     | Actuator |     |     |
PID
TR
Figure 3.23 Representation of the controllers with anti-windup
inFigure 3.19using the basic controlmodule with trackingshown
| in Figure | 3.22. |     |     |     |     |     |     |
| --------- | ----- | --- | --- | --- | --- | --- | --- |
TheProportionalBand
The notion of proportional band is useful in order to understand the
wind-up effect and to explain schemes for anti-windup. The propor-
tional band is an interval such that the actuator does not saturate if
the instantaneous value of the process output or its predicted value
is in the interval. For PID control without derivative gain limitation,
| the control | signal | is given | by  |     |     |     |     |
| ----------- | ------ | -------- | --- | --- | --- | --- | --- |
dy
|     |     | u=  | K(by | −y)+ | I− KT |     | (3.24) |
| --- | --- | --- | ---- | ---- | ----- | --- | ------ |
|     |     |     | sp   |      | d     |     |        |
dt
| Solving | for the | predicted | process | output |     |     |     |
| ------- | ------- | --------- | ------- | ------ | --- | --- | --- |
dy
|           |              |     | y         | = y+T |      |     |     |
| --------- | ------------ | --- | --------- | ----- | ---- | --- | --- |
|           |              |     | p         |       | d dt |     |     |
| gives the | proportional |     | band (y,y | ) as  |      |     |     |
l h
I−u
|     |     |     | y = by | +   | max |     |        |
| --- | --- | --- | ------ | --- | --- | --- | ------ |
|     |     |     | l      | sp  |     |     |        |
|     |     |     |        |     | K   |     | (3.25) |
I−u
|       |     |         | y = by | +      | min            |     |           |
| ----- | --- | ------- | ------ | ------ | -------------- | --- | --------- |
|       |     |         | h      | sp     | K              |     |           |
| and u | , u | are the | values | of the | control signal | for | which the |
| min   | max |         |        |        |                |     |           |
actuator saturates. The controller operates in the linear mode, if
the predicted output is in the proportional band. The control signal
saturateswhenthepredictedoutputisoutsidetheproportional band.
Notice that the proportional band can be shifted by changing the
integral term.

| 88 Chapter | 3 PID Control |     |     |     |
| ---------- | ------------- | --- | --- | --- |
y
| 2   | sp  |     |     |     |
| --- | --- | --- | --- | --- |
−2 y
| 0   | 20  | 40  | 60  | 80  |
| --- | --- | --- | --- | --- |
0.1
u
0
−0.1
| 0      | 20       | 40                    | 60                    | 80  |
| ------ | -------- | --------------------- | --------------------- | --- |
| Figure | 3.24 The | proportional band for | the system in Example |     |
3.1.Theupperdiagramshowsprocessoutputyandtheproportional
| band. | The lower diagram | shows controlsignal | u.  |     |
| ----- | ----------------- | ------------------- | --- | --- |
To illustrate that the proportional band is useful in understand-
| ingwindup,weshowtheproportional |     | bandinFigure3.24forthesys- |     |     |
| ------------------------------- | --- | -------------------------- | --- | --- |
temdiscussedinExample3.1.(ComparewithFigure3.18.)Thefigure
| showsthattheproportional |     | bandstartstomoveupwardsbecausethe |     |     |
| ------------------------ | --- | --------------------------------- | --- | --- |
integral term increases. This implies that the output does not reach
theproportional banduntil itismuchlargerthanthesetpoint. When
the proportional band isreached the control signal decreases rapidly.
The proportional band changes so rapidly, however, that the output
veryquicklymovesthroughtheband,andthisprocessrepeatsseveral
times.
| The | notion of proportional | band helps | to understand | several |
| --- | ---------------------- | ---------- | ------------- | ------- |
schemes for anti-windup. Figure 3.25 shows the proportional band
for the system with tracking for different values of the tracking time
constant T. The figure shows that the tracking time constant has a
t
significant influence on the proportional band. Because of the track-
ing,theproportional bandismoved closer totheprocess output. How
rapidly it does this is governed by the tracking time constant T. No-
t
tice that there may be a disadvantage in moving it too rapidly, since
the predicted output may then move into the proportional band be-
causeofnoise,andcausethecontrolsignaltodecreaseunnecessarily.
ConditionalIntegration
Conditional integration is analternative toback-calculation or track-
ing. In this method integration is switched off when the control is
far from steady state. Integral action is thus only used when certain
conditions are fulfilled, otherwise the integral term is kept constant.
| The method | is also called | integrator clamping. |     |     |
| ---------- | -------------- | -------------------- | --- | --- |

|      |     |     |     | 3.5  | Integrator | Windup | 89  |
| ---- | --- | --- | --- | ---- | ---------- | ------ | --- |
| =0.1 |     |     |     | =0.3 |            |        |     |
| T t  |     |     |     | T t  |            |        |     |
| 1    |     |     |     | 1    |            |        |     |
|      | y   |     |     |      | y          |        |     |
| 0    |     |     |     | 0    |            |        |     |
| 0 5  | 10  | 15  | 20  | 0    | 5 10       | 15     | 20  |
| =1.0 |     |     |     | =1.4 |            |        |     |
| T t  |     |     |     | T t  |            |        |     |
| 1    |     |     |     | 1    |            |        |     |
|      | y   |     |     |      | y          |        |     |
| 0    |     |     |     | 0    |            |        |     |
| 0 5  | 10  | 15  | 20  | 0    | 5 10       | 15     | 20  |
Figure 3.25 The proportional band and the process output yfor
a system with conditional integration and tracking with different
| tracking | time | constants | T.  |     |     |     |     |
| -------- | ---- | --------- | --- | --- | --- | --- | --- |
t
The conditions when integration is inhibited can be expressed in
many different ways. Figure 3.26 shows a simulation of the system
in Example 3.1 with conditional integration such that the integral
term is kept constant during saturation. A comparison with Figure
3.25 shows that, in this particular case, there is very little difference
in performance between conditional integration and tracking. The
different wind-up schemes do, however, move the proportional bands
differently.
| A few | different | switching | conditions | are | now | considered. | One |
| ----- | --------- | --------- | ---------- | --- | --- | ----------- | --- |
simple approach is to switch off integration when the control error is
large.Anotherapproachistoswitchoffintegrationduringsaturation.
Boththesemethodshavethedisadvantagethatthecontrollermayget
stuckatanon-zerocontrolerroriftheintegraltermhasalargevalue
| at the time | of switch | off. |     |     |     |     |     |
| ----------- | --------- | ---- | --- | --- | --- | --- | --- |
A method without this disadvantage is the following. Integration
is switched off when the controller is saturated and the integrator
update is such that it causes the control signal to become more satu-
rated. Suppose, for example, that thecontroller becomes saturated at
the upper saturation. Integration is then switched off if the control
| error is positive, |             | but not     | if it is negative. |     |              |        |     |
| ------------------ | ----------- | ----------- | ------------------ | --- | ------------ | ------ | --- |
| Some               | conditional | integration | methods            |     | are intended | mainly | for |
startup of batch processes, when there may be large changes in the
setpoint.Oneparticularversion,usedintemperaturecontrol,setsthe
proportional band outside the setpoint when there are large control
deviations. Theoffsetcanbeusedtoadjustthetransientresponse ob-
tained duringstartupoftheprocess. Theparameters usedarecalled
|                   |     | (seeFigure | 3.27).Inthissystem |     |     |                 |     |
| ----------------- | --- | ---------- | ------------------ | --- | --- | --------------- | --- |
| cut-backorpreload |     |            |                    |     |     | theproportional |     |
band is positioned with one end at the setpoint and the other end

| 90 Chapter | 3 PID Control |     |     |     |
| ---------- | ------------- | --- | --- | --- |
1
0.5
y
0
| 0   | 10  |     | 20  | 30  |
| --- | --- | --- | --- | --- |
0.1
u
0
| 0   | 10  |     | 20  | 30  |
| --- | --- | --- | --- | --- |
I
0.02
−0.02
| 0      | 10                                               |     | 20  | 30  |
| ------ | ------------------------------------------------ | --- | --- | --- |
| Figure | 3.26 SimulationofthesysteminExample3.1withcondi- |     |     |     |
tional integration. The diagrams show the proportional band, pro-
| cessoutput | y, controlsignal | u, and integralpart | I.  |     |
| ---------- | ---------------- | ------------------- | --- | --- |
y sp
1
0.5
y
0
| 0   | 10  |     | 20  | 30  |
| --- | --- | --- | --- | --- |
0.1
u
0
| 0   | 10  |     | 20  | 30  |
| --- | --- | --- | --- | --- |
0
I
−0.2
| 0                                                      | 10                                                |     | 20  | 30  |
| ------------------------------------------------------ | ------------------------------------------------- | --- | --- | --- |
| Figure                                                 | 3.27 Adjustmentoftheproportionalbandusingcut-back |     |     |     |
| parameters.Thediagramsshowtheproportionalband,setpoint |                                                   |     |     | y , |
sp
| process | output y, controlsignal | u, and | integralpart I. |     |
| ------- | ----------------------- | ------ | --------------- | --- |

|     |     |     | 3.5 Integrator | Windup | 91  |
| --- | --- | --- | -------------- | ------ | --- |
towards the measured value when there are large variations. These
| methods may | give wind-up | during | disturbances. |     |     |
| ----------- | ------------ | ------ | ------------- | --- | --- |
SeriesImplementation
In Figure 3.8, we showed a special implementation of a controller
in interacting form. To avoid windup in this controller we can incor-
porate a model of the saturation in the system as shown in Figure
3.28A. Notice that in this implementation the tracking time constant
T is the same as the integration time T. This value of the tracking
| t                                     |          |            | i                   |     |     |
| ------------------------------------- | -------- | ---------- | ------------------- | --- | --- |
| time constant                         | is often | too large. |                     |     |     |
| InFigure3.28A,themodelofthesaturation |          |            | willlimitthecontrol |     |     |
signal directly. It is important, therefore, to have a good model of the
physical saturation. Too hard a limitation will cause an unnecessary
limitation of the control action. Too weak a limitation will cause
windup.
More flexibility is provided if the saturation is positioned accord-
ing to Figure 3.28B. In this case, the saturation will not influence
the proportional part of the controller. With this structure it is also
possibletoforcetheintegralparttoassumeotherpreloadvaluesdur-
ing saturation. This is achieved by replacing the saturation function
by the nonlinearity shown in Figure 3.29. This anti-windup proce-
dure is sometimes called a “batch unit” and may be regarded as a
type of conditional integration. It is mainly used for adjusting the
A
|     | e   |     |     | u   |     |
| --- | --- | --- | --- | --- | --- |
Σ
K
I
1
  1 +sT
|     |     |     |    i |     |     |
| --- | --- | --- | ---- | --- | --- |
B
Σ
| e   | K   |     |     |     | u   |
| --- | --- | --- | --- | --- | --- |
I
1
1+sT
i
| Figure | 3.28 Twowaystoprovideanti-windupinthecontrollerin |     |                      |        |     |
| ------ | ------------------------------------------------- | --- | -------------------- | ------ | --- |
| Figure | 3.8where integralactionis                         |     | generatedasautomatic | reset. |     |

92 Chapter 3 PID Control
u
max
preload
max
u u
min max
u
preload
min
u
min
Figure 3.29 A “batch unit” used to provide anti-windup in the
controller in Figure 3.8.
overshoot during startup when there is a large setpoint change. In
early single-loop controllers the batch unit was supplied as a special
add-on hardware.
CombinedSchemes
Trackingandconditionalintegrationcanalsobecombined.In(Howes,
1986) it is suggested to manipulate the proportional band explic-
itly for batch control. This is done by introducing so-called cutback
points. The high cutback is above the setpoint and the low cutback
is below. The integrator is clamped when the predicted process out-
put is outside the cutback interval. Integration is performed with a
specified tracking time constant when the process output is between
the cutback points. The cutback points are considered as controller
parameters that are adjusted to influence the response to large set-
point changes. A similar method is proposed in (Dreinhofer, 1988),
where conditional integration is combined with back-calculation. In
(Shinskey,1988),theintegratorisgivenaprescribedvaluei=i dur-
0
ing saturation. The value of i is tuned to give satisfactory overshoot
0
at startup. This approach is also called preloading.

|     |                        |     | 3.6 DigitalImplementation |     | 93  |
| --- | ---------------------- | --- | ------------------------- | --- | --- |
| 3.6 | Digital Implementation |     |                           |     |     |
PIDcontrollerswereoriginallyimplementedusinganalogtechniques.
Early systems used pneumatic relays, bellows, and needle-valve con-
strictions. Electric motors with relays and feedback circuits and op-
erational amplifiers were used later. Many of the features like anti-
windupandderivation ofprocess output instead ofcontrol errorwere
incorporated as “tricks” in the implementation. It is now common
practice to implement PID controllers using microprocessors, and
some of the old tricks have been rediscovered. Several issues must
be considered in connection with digital implementations. The most
important ones have to do with sampling, discretization, and quanti-
zation.
Sampling
Whenadigitalcomputerisusedtoimplementacontrollaw,allsignal
processing is done at discrete instances of time. The sequence of
| operations | is as follows: |     |     |     |     |
| ---------- | -------------- | --- | --- | --- | --- |
(1)
|     | Wait for clock interrupt |     |     |     |     |
| --- | ------------------------ | --- | --- | --- | --- |
(2)
|     | Read analog input |        |     |     |     |
| --- | ----------------- | ------ | --- | --- | --- |
| (3) | Compute control   | signal |     |     |     |
(4)
|     | Set analog output |           |     |     |     |
| --- | ----------------- | --------- | --- | --- | --- |
| (5) | Update controller | variables |     |     |     |
| (6) | Go to 1           |           |     |     |     |
The control actions are based on the values of the process output at
samplin(cid:3).
| discrete | times only. This | procedure | is called |     | The normal |
| -------- | ---------------- | --------- | --------- | --- | ---------- |
case is that the signals are sampled periodically with period h. The
sampling mechanism introduces some unexpected phenomena, which
mustbetaken intoaccount inagood digital implementation ofaPID
| controller. | To explain these, | consider | the | signals |     |
| ----------- | ----------------- | -------- | --- | ------- | --- |
s(t)=cos(nωt±ωt)
s
and
(t)=cos(ωt)
s
a
|       | ω = 2π/h [rad/s] |        |          |            |            |
| ----- | ---------------- | ------ | -------- | ---------- | ---------- |
| where | s                | is the | sampling | frequency. | Well-known |
formulas for the cosine function imply that the values of the signals
| at the | sampling instants | [kh,k=0,1,2,...] |     | have the property |       |
| ------ | ----------------- | ---------------- | --- | ----------------- | ----- |
|        | s(kh)=cos(nkhω    | ±ωkh)=cos(ωkh)=s |     |                   | (ωkh) |
|        |                   | s                |     | a                 |       |
The signals s and s thus have the same values at the sampling
a
instants. This means that there is no way to separate the signals
if only their values at the sampling instants are known. Signal s
a

| 94 Chapter | 3 PID | Control |     |     |     |
| ---------- | ----- | ------- | --- | --- | --- |
s
| 1   | a   |     |     |     |     |
| --- | --- | --- | --- | --- | --- |
| 0   | s   |     |     |     |     |
−1
| 0      | 1                                                    | 2   | 3   | 4   | 5   |
| ------ | ---------------------------------------------------- | --- | --- | --- | --- |
| Figure | 3.30 Illustrationofthealiasingeffect.Thediagramshows |     |     |     |     |
| signal | sand its alias                                       | s . |     |     |     |
a
is, therefore, called an alias of signal s. This is illustrated in Figure
3.30. A consequence of the aliasing effect is that a high-frequency
disturbance after sampling may appear as a low-frequency signal. In
| Figure3.30thesampling |     | periodis1sandthesinusoidal |     | disturbance |     |
| --------------------- | --- | -------------------------- | --- | ----------- | --- |
6/5
has a period of s. After sampling, the disturbance appear as a
| sinusoid | with the frequency |     |     |     |     |
| -------- | ------------------ | --- | --- | --- | --- |
5
|     |     | f =1− | =1/6 Hz |     |     |
| --- | --- | ----- | ------- | --- | --- |
a
6
This low-frequency signal with time period 6 s is seen in the figure.
Prefiltering
The aliasing effect can create significant difficulties if proper pre-
cautions arenot taken. High frequencies, which in analog controllers
normallyareeffectivelyeliminatedbylow-passfiltering,may,because
of aliasing, appear as low-frequency signals in the bandwidth of the
sampledcontrolsystem.Toavoidthesedifficulties,ananalogprefilter
(which
effectively eliminates all signal components with frequencies
above half the sampling frequency) should be introduced. Such a fil-
ter is called an antialiasing filter. A second-order Butterworth filter
is a common antialiasing filter. Higher-order filters are also used in
critical applications. An implementation of such a filter using opera-
tional amplifiers is shown in Figure 3.31. The selection of the filter
| bandwidth | is illustrated | by the following | example.  |     |     |
| --------- | -------------- | ---------------- | --------- | --- | --- |
| EXAMPLE   | 3.2 Selection  | of prefilter     | bandwidth |     |     |
Assume it is desired that the prefilter attenuate signals by a factor
isω
| of16athalfthesamplingfrequency. |           |         | Ifthefilterbandwidth |     | b and |
| ------------------------------- | --------- | ------- | -------------------- | --- | ----- |
| the sampling                    | frequency | isω, we | get                  |     |       |
s
|     |     | (ω/2ω)2 | =16 |     |     |
| --- | --- | ------- | --- | --- | --- |
|     |     | s       | b   |     |     |

|     |     |     | 3.6 DigitalImplementation | 95  |
| --- | --- | --- | ------------------------- | --- |
_
_
+ _
+
+
| Figure | 3.31 | Circuitdiagramofasecond-orderButterworthfilter. |     |     |
| ------ | ---- | ----------------------------------------------- | --- | --- |
Hence,
1
|     |     | ω   | = ω |     |
| --- | --- | --- | --- | --- |
b 8 s
Notice that the dynamics of the prefilter will be combined with
| the process | dynamics. |     |     |     |
| ----------- | --------- | --- | --- | --- |
Discretization
Toimplement acontinuous-time control law,suchasaPIDcontroller
in a digital computer, it is necessary to approximate the derivatives
and the integral that appear in the control law. A few different ways
| to do this       | are presented | below.  |     |     |
| ---------------- | ------------- | ------- | --- | --- |
| Proportional     | Action        |         |     |     |
| The proportional |               | term is |     |     |
|                  |               | P= K(by | −y) |     |
sp
This term is implemented simply by replacing the continuous vari-
| ables with | their sampled | versions.   | Hence,      |        |
| ---------- | ------------- | ----------- | ----------- | ------ |
|            |               | P(t )= K(by | (t )−y(t )) | (3.26) |
|            |               | k           | sp k k      |        |
|            | {t }          |             |             |        |
where denotes the sampling instants, i.e., the times when the
k
| computer     | reads the | analog input. |     |     |
| ------------ | --------- | ------------- | --- | --- |
| Integral     | Action    |               |     |     |
| The integral | term      | is given by   |     |     |
(cid:1)t
K
|     |     | I(t)= | e(s)ds |     |
| --- | --- | ----- | ------ | --- |
T
i
0

| 96 Chapter |         | 3 PID Control |                  |      |      |           |     |        |
| ---------- | ------- | ------------- | ---------------- | ---- | ---- | --------- | --- | ------ |
| It follows | that    |               |                  |      |      |           |     |        |
|            |         |               |                  | dI K |      |           |     |        |
|            |         |               |                  | =    | e    |           |     | (3.27) |
|            |         |               |                  | dt T | i    |           |     |        |
| There are  | several | ways          | of approximating |      | this | equation. |     |        |
Forward differences: Approximating the derivative by a forward
| difference | gives |     |        |       |     |       |     |     |
| ---------- | ----- | --- | ------ | ----- | --- | ----- | --- | --- |
|            |       |     | I(t )− | I(t ) |     |       |     |     |
|            |       |     | k+1    | k     | K   |       |     |     |
|            |       |     |        |       | =   | e(t ) |     |     |
|            |       |     | h      |       | T   | k     |     |     |
i
This leads to the following recursive equation for the integral term
Kh
|     |     | I(t | )=  | I(t )+ |     | e(t ) |     | (3.28) |
| --- | --- | --- | --- | ------ | --- | ----- | --- | ------ |
|     |     |     | k+1 | k      |     | k     |     |        |
T
i
Backward differences: If the derivative in Equation (3.27) is ap-
proximated instead by a backward difference, the following is ob-
tained:
|     |     | I(t | )− I(t | −1) |     |       |     |     |
| --- | --- | --- | ------ | --- | --- | ----- | --- | --- |
|     |     |     | k      | k   | K   |       |     |     |
|     |     |     |        |     | =   | e(t ) |     |     |
|     |     |     | h      |     | T   | k     |     |     |
i
This leads to the following recursive equation for the integral term
Kh
|     |     | I(t | )=  | I(t )+ | e(t | )   |     | (3.29) |
| --- | --- | --- | --- | ------ | --- | --- | --- | ------ |
|     |     |     | k+1 | k      |     | k+1 |     |        |
T
i
| Tustin’s      | approximation |        | andrampequivalence: |            |      |               | Anothersimple |        |
| ------------- | ------------- | ------ | ------------------- | ---------- | ---- | ------------- | ------------- | ------ |
| approximation |               | method | is due              | to Tustin. | This | approximation |               | is     |
|               |               |        |                     | Kh         | e(t  | )+e(t         | )             |        |
|               |               | I(t    | )= I(t              | )+         | k+1  |               | k             | (3.30) |
|               |               | k+1    | k                   |            |      |               |               |        |
|               |               |        |                     | T          |      | 2             |               |        |
i
Yetanother methodiscalledrampequivalence. Thismethodgives ex-
actoutputs atthesampling instants, iftheinputsignal iscontinuous
andpiece-wiselinearbetweenthesamplinginstants.Therampequiv-
alence method gives the same approximation of the integral term as
(3.30).
| the Tustin     | approximation, |                    | i.e.,         | Equation |         |         |             |        |
| -------------- | -------------- | ------------------ | ------------- | -------- | ------- | ------- | ----------- | ------ |
| Notice         | that           | all approximations |               | have     | the     | same    | form, i.e., |        |
|                |                | I(t                | )= I(t        | )+b      | e(t )+b | e(t     | )           | (3.31) |
|                |                | k+1                | k             | i1       | k+1     | i2      | k           |        |
| but with       | different      | values             | of parameters |          | b       | and b   | .           |        |
|                |                |                    |               |          | i1      | i2      |             |        |
| Derivative     |                | Action             |               |          |         |         |             |        |
| The derivative |                | term is            | given by      | Equation |         | (3.22), | i.e.,       |        |
|                |                |                    | T dD          |          |         | dy      |             |        |
|                |                |                    | d             | + D =−KT |         |         |             | (3.32) |
d
|     |     |     | N dt |     |     | dt  |     |     |
| --- | --- | --- | ---- | --- | --- | --- | --- | --- |
This equation can be approximated in the same way as the integral
term.

3.6 DigitalImplementation 97
Forward differences: Approximating the derivative by a forward
difference gives
T d D(t k+1 )− D(t k ) + D(t )=−KT y(t k+1 )−y(t k )
k d
N h h
This can be rewritten as
(cid:5) (cid:6)
Nh
D(t
k+1
)= 1− D(t
k
)−KN(y(t
k+1
)−y(t
k
)) (3.33)
T
d
Backward differences: If the derivative in Equation (3.32) is ap-
proximated by a backward difference, the following equation is ob-
tained:
T d D(t k )− D(t k−1 ) + D(t )=−KT y(t k )−y(t k−1 )
k d
N h h
This can be rewritten as
T KT N
D(t
k
)=
T +
d
Nh
D(t
k−1
)−
T +
d
Nh
(y(t
k
)−y(t
k−1
)) (3.34)
d d
Tustin’s approximation: Using the Tustin approximation to ap-
proximate the derivative term gives
2T −Nh 2KT N
D(t
k
)=
2T
d
+Nh
D(t
k−1
)−
2T +
d
Nh
(y(t
k
)−y(t
k−1
)) (3.35)
d d
Ramp equivalence: Finally, the ramp equivalence approximation
is
D(t k )= e −Nh/TdD(t k−1 )−
KT
d
(1−
h
e −Nh/Td )
(y(t k )−y(t k−1 )) (3.36)
All approximations have the same form,
D(t
k
)=a
d
D(t
k−1
)−b
d
(y(t
k
)−y(t
k−1
)) (3.37)
but with different values of parameters a and b .
d d
The approximations of the derivative term are stable only when
(cid:2)a (cid:2) < 1. The forward difference approximation requires that T >
d d
Nh/2. The approximation becomes unstable for small values of T .
d
The other approximations arestable for all values of T . Notice, how-
d
ever, that Tustin’s approximation and the forward difference approx-
imation give negative values of a if T is small. This is undesirable
d d
because the approximation will then exhibit ringing. The backward
difference approximation will give good results for all values of T . It
d
is also easier to compute than the ramp equivalence approximation
and is, therefore, the most common method.

98 Chapter 3 PID Control
FD
40 RE
BD
T
0
−2 −1 0 1 2
2 FD
RE
−2
BD T
−6
−2 −1 0 1 2
Figure 3.32 Phase curves for PD controllers obtained by differ-
ent discretizations of the derivative term sT /(1 + sT /N) with
d d
T =1,N =10andasamplingperiod0.02.Thediscretizationsare
d
forward differences (FD), backward differences (BD), Tustin’s ap-
proximation (T), and ramp equivalence (RE). The lower diagram
shows the differences between the approximations and the true
phase curve.
Figure3.32showsthephasecurvesforthedifferentdiscrete time
approximations.Tustin’sapproximationandtherampequivalenceap-
proximation give the best agreement with the continuous time case,
the backward approximation gives less phase advance, and the for-
ward approximation gives more phase advance. The forward approx-
imation is seldom used because of the problems with instability for
small values of derivative time T . Tustin’s algorithm is used quite
d
frequently because of its simplicity and its close agreement with the
continuous time transfer function. The backward difference is used
when an algorithm that is well behaved for small T is needed.
d
All approximations of the PID controller can be represented as
R(q)u(kh) =T(q)y (kh)−S(q)y(kh) (3.38)
sp
where qis the forward shift operator, and the polynomials R,S, and
T are of second order. The polynomials R,S, and T have the forms
R(q)=(q−1)(q−a )
d
S(q)= s q2+s q+s (3.39)
0 1 2
T(q)= t q2+t q+t
0 1 2
which means that Equation (3.38) can be written as
u(kh)= t y (kh)+t y (kh−h)+t y (kh−2h)
0 sp 1 sp 2 sp
−s y(kh)−s y(kh−h)−s y(kj−2h)
0 1 2
+(1+a )u(kh−h)−a u(kh−h)
d d

3.6 DigitalImplementation 99
Table 3.1 Coefficients in different approximations of the contin-
uous time PID controller.
Forward Backward Tustin Rampequivalence
Kh Kh Kh
b 0
i1 T 2T 2T
i i i
Kh Kh Kh
b 0
i2 T 2T 2T
i i i
Nh T 2T −Nh
a
d
1−
T T +
d
Nh 2T
d
+Nh
e−Nh/Td
d d d
b KN
KT
d
N 2KT
d
N KT
d
(1−e−Nh/Td )
d T +Nh 2T +Nh h
d d
The coefficients in the S and T polynomials are
s = K +b +b
0 i1 d
s =−K(1+a )−b a +b −2b
1 d i1 d i2 d
s = Ka −b a +b
2 d i2 d d (3.40)
t = Kb+b
0 i1
t =−Kb(1+a )−b a +b
1 d i1 d i2
t = Kba −b a
2 d i2 d
Thecoefficients in the polynomials for different approximation meth-
ods are given in Table 3.1.
Incremental Form
The algorithms described so far are called positional algorithms be-
cause they give the output of the controller directly. In digital imple-
mentations it iscommon toalso use velocity algorithms. Thediscrete
time version of such an algorithm is also called an incremental algo-
rithm.This form is obtained bycomputing the time differences of the
controller output and adding the increments.
∆u(t
k
)=u(t
k
)−u(t
k−1
)=∆P(t
k
)+∆I(t
k
)+∆D(t
k
)
In some cases integration is performed externally. This is natural
when a stepper motor is used. The output of the controller should
then represent the increments of the control signal, and the mo-
tor implements the integrator. The increments of the proportional
part, the integral part, and the derivative part are easily calculated

| 100            | Chapter | 3       | PID Control |             |       |      |          |     |
| -------------- | ------- | ------- | ----------- | ----------- | ----- | ---- | -------- | --- |
| from Equations |         | (3.26), | (3.31)      | and (3.37): |       |      |          |     |
| ∆P(t           | )= P(t  | )−P(t   | )=K         | (by (t      | )−y(t | )−by | (t )+y(t | ))  |
|                |         |         | k−1         |             |       |      | k−1      | k−1 |
| k              |         | k       |             | sp          | k     | k    | sp       |     |
| ∆I(t           | )= I(t  | )−I(t   | )=b         | e(t )+b     | e(t   | )    |          |     |
| k              |         | k       | k−1         | i1 k        | i2    | k−1  |          |     |
∆D(t )= D(t )−D(t k−1 )=a ∆D(t k−1 )−b (y(t )−2y(t k−1 )+y(t k−2 ))
| k   |     | k   |     | d   |     | d k |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
One advantage with the incremental algorithm is that most of the
computations are done using increments only. Short word-length cal-
culations can often be used. It is only in the final stage where the
increments are added that precision is needed. Another advantage
is that the controller output is driven directly from an integrator.
This makes it very easy to deal with windup and mode switches. A
problem with the incremental algorithm is that it cannot be used for
∆P
controllers with P or PD action only. Therefore, has to be cal-
culated in the following way when integral action is not used (see
3.4).
Section
|              |     |      |      | (cid:20)    | (cid:21) |         |     |     |
| ------------ | --- | ---- | ---- | ----------- | -------- | ------- | --- | --- |
|              |     | ∆P(t | )= K | by (t )−y(t | )        | +u −u(t | )   |     |
|              |     | k    |      | sp k        | k        | b       | k−1 |     |
| Quantization |     | and  | Word | Length      |          |         |     |     |
A digital computer allows only finite precision in the calculations. It
is sometimes difficult to implement the integral term on computers
with a short word length. The difficulty is understood from Equation
| (3.31)for |     |          |       |                |     |       | e(t )+b | e(t ) |
| --------- | --- | -------- | ----- | -------------- | --- | ----- | ------- | ----- |
|           | the | integral | term. | The correction |     | terms | b k+1   |       |
|           |     |          |       |                |     |       | i1      | i2 k  |
are normally small in comparison to I(t ), and they may be rounded
k
offunlessthewordlengthissufficientlylarge.Thisrounding-offeffect
gives anoffset, called integration offset. Togetafeel for the orders of
| magnitudeinvolved, |     |     | assumethatweusethebackwardapproximation |     |     |     |     |     |
| ------------------ | --- | --- | --------------------------------------- | --- | --- | --- | --- | --- |
and that all signals are normalized to have a largest magnitude of
one. The correction term Kh/T ⋅ e in Equation (3.29) then has the
i
Kh/T.
| largest  | magnitude |     |        | i Let the | sampling | period   | h be 0.02    | s, the |
| -------- | --------- | --- | ------ | --------- | -------- | -------- | ------------ | ------ |
|          |           | =   |        | =         |          |          | =            |        |
| integral | time      | T   | 20 min | 1200 s    | and      | the gain | K 0.1. Then, |        |
i
Kh
|     |     |     |     | =1.7 10 | −6 =2 | −19.2 |     |     |
| --- | --- | --- | --- | ------- | ----- | ----- | --- | --- |
|     |     |     | T   | i       |       |       |     |     |
To avoid rounding off the correction term, it is thus necessary to
have a precision of at least 20 bits. More bits are required to obtain
meaningful numericalvalues. Thesituation isparticularly important
when a stepping motor that outputs increments is used. It is then
necessarytoresorttospecialtrickstoavoidroundingofftheintegral.
One simple way is to use a longer sampling period for the integral
term. For instance, if a sampling period of 1 s is used instead of 0.02
s in the previous example, a precision of 14 bits is sufficient.

|     |     |     | 3.6 | DigitalImplementation |     | 101 |
| --- | --- | --- | --- | --------------------- | --- | --- |
Three-PositionPulseOutput
In Section 3.4, it was mentioned that the PID controller may have
different types of outputs. We now return to the three-position pulse
output and give a more detailed description of its implementation.
Ifavalve isdriven byaconstant-speed electrical motor, the valve
can be in three states: “increase,” “stop,” and “decrease.” Control of
valves with electrical actuators is performed with a controller output
that can be in three states. Three-position pulse output is performed
usingtwodigitaloutputs fromthecontroller. Whenthefirstoutputis
conducting, the valve position will increase. When the second output
is conducting, the valve position will decrease. If none of the outputs
are conducting, the valve position is constant. The two outputs must
| never be | conducting | at the | same time. |     |     |     |
| -------- | ---------- | ------ | ---------- | --- | --- | --- |
There is normally both a dead zone and a dead time in the con-
troller to ensure that the change of direction of the motor is not too
frequent and not too fast. It means that the controller output is con-
stant aslong asthemagnitude ofthecontrol error iswithin thedead
zone, and that the output is stopped for a few seconds before it is
| allowed | to change | direction. |     |     |     |     |
| ------- | --------- | ---------- | --- | --- | --- | --- |
A servomotor is characterized by its running time T , which is
run
thetimeittakesforthemotortogofromoneendpositiontotheother.
Sincetheservomotorhasaconstantspeed,itintroducesanintegrator
in the control loop, where the integration time is determined by T .
run
AblockdiagramdescribingaPIDcontroller withthree-position pulse
output combined with an electrical actuator is shown in Figure 3.33.
| Supposethatwehaveasteady-statesituation, |     |     |     |     | wheretheoutputfrom |     |
| ---------------------------------------- | --- | --- | --- | --- | ------------------ | --- |
the PID controller u is equal to the position v of the servo-motor.
Suppose further that we suddenly want to increase the controller
outputbyanamount∆u.Aslongastheincrease-outputisconducting,
| the output | vfrom | the servo-motor | will | increase | according | to  |
| ---------- | ----- | --------------- | ---- | -------- | --------- | --- |
(cid:1)t
|     |     | ∆v= | 1 1dt= |     | t   |     |
| --- | --- | --- | ------ | --- | --- | --- |
|     |     |     | T      | T   |     |     |
|     |     |     | run    | run |     |     |
0
|         | ∆v    | ∆u,    |             |      |            |            |
| ------- | ----- | ------ | ----------- | ---- | ---------- | ---------- |
| To have | equal | to the | integration | must | be stopped | after time |
t=∆uT
run
|     |            |  ∆ u | 1   |          | 1      | v   |
| --- | ---------- | ---- | --- | -------- | ------ | --- |
|     | PID        |      |     |          | sT     |     |
|     |            |      | –1  |          |    run |     |
|     | Controller |      |     | Actuator |        |     |
Figure 3.33 A PID controller with three-position pulse output
| combined | withan | electricalactuator. |     |     |     |     |
| -------- | ------ | ------------------- | --- | --- | --- | --- |

| 102 | Chapter | 3 PID | Control |     |     |
| --- | ------- | ----- | ------- | --- | --- |
Ina digital controller, this means that the digital output correspond-
ing to an increasing valve position is to be conducting for n sampling
| periods, | where | n is | given by |     |     |
| -------- | ----- | ---- | -------- | --- | --- |
∆uT
|     |     |     |     | n= run |     |
| --- | --- | --- | --- | ------ | --- |
h
| and | where h is | the | sampling | period of | the controller. |
| --- | ---------- | --- | -------- | --------- | --------------- |
To be able to perform a correct three-position pulse output, two
buffers (Buff increase and Buff decrease) must be used to hold
the number of pulses that should be sent out. The following is a
computer code for three-position pulse output. For the sake of sim-
plicity, details such as dead zone and dead time are omitted in the
code.
| if  | delta    | u > 0    | then       |                 |      |
| --- | -------- | -------- | ---------- | --------------- | ---- |
|     | if valve | is       | increasing | then            |      |
|     | Buff     | increase |            | = Buff increase | + n; |
else
|     | Buff | decrease |          | = Buff decrease | - n;           |
| --- | ---- | -------- | -------- | --------------- | -------------- |
|     | if   | Buff     | decrease | < 0 then        |                |
|     |      | Buff     | increase | = -             | Buff decrease; |
|     |      | Buff     | decrease | = 0;            |                |
|     |      | valve    | is       | decreasing      | = false;       |
|     |      | valve    | is       | increasing      | = true;        |
end;
end;
| else | if delta | u        | < 0 then   |                 |      |
| ---- | -------- | -------- | ---------- | --------------- | ---- |
|      | if valve | is       | decreasing | then            |      |
|      | Buff     | decrease |            | = Buff decrease | + n; |
else
|     | Buff | increase |          | = Buff increase | - n;           |
| --- | ---- | -------- | -------- | --------------- | -------------- |
|     | if   | Buff     | increase | < 0 then        |                |
|     |      | Buff     | decrease | = -             | Buff increase; |
|     |      | Buff     | increase | = 0;            |                |
|     |      | valve    | is       | increasing      | = false;       |
|     |      | valve    | is       | decreasing      | = true;        |
end;
end;
end;
| if   | Buff increase  |          | > 0    | then     |      |
| ---- | -------------- | -------- | ------ | -------- | ---- |
|      | Increaseoutput |          | =      | 1;       |      |
|      | Decreaseoutput |          | =      | 0;       |      |
|      | Buff increase  |          | = Buff | increase | - 1; |
| else | if Buff        | decrease |        | > 0 then |      |
|      | Increaseoutput |          | =      | 0;       |      |
|      | Decreaseoutput |          | =      | 1;       |      |
|      | Buff decrease  |          | = Buff | decrease | - 1; |
end;

|     |     |     |     | 3.7 Operational | Aspects 103 |
| --- | --- | --- | --- | --------------- | ----------- |
According to Figure 3.33, the controller output is ∆u instead of u in
thecaseofthree-positionpulseoutput.Theintegralpartofthecontrol
algorithm is outside the controller, in the actuator. This solution
causesnoproblemsifthecontrolalgorithmreallycontainsanintegral
part.PandPDcontrolcannotbeobtainedwithoutinformation ofthe
| valve position | (see Figure | 3.17.)  |     |     |     |
| -------------- | ----------- | ------- | --- | --- | --- |
| 3.7            | Operational | Aspects |     |     |     |
Practically all controllers can be run in two modes: manual or auto-
matic. In manual mode the controller output is manipulated directly
bytheoperator,typicallybypushingbuttonsthatincreaseordecrease
the controller output. A controller may also operate in combination
withothercontrollers,suchasinacascadeorratioconnection,orwith
nonlinear elements, suchas multipliers andselectors. This gives rise
tomoreoperational modes.Thecontrollers alsohaveparametersthat
can be adjusted in operation. When there are changes of modes and
parameters, it is essential toavoid switching transients. Theway the
mode switchings and the parameter changes are made depends on
| the structure | chosen | for the | controller. |     |     |
| ------------- | ------ | ------- | ----------- | --- | --- |
BumplessTransferBetweenManualandAutomatic
Sincethecontroller isadynamic system, itisnecessary tomakesure
that the state of the system is correct when switching the controller
| between | manual andautomatic |     | mode. | Whenthe | system isinmanual |
| ------- | ------------------- | --- | ----- | ------- | ----------------- |
mode, the control algorithm produces a control signal that may be
different from the manually generated control signal. It is necessary
to make sure that the two outputs coincide at the time of switching.
| This is                                      | called bumpless | transfer. |     |     |               |
| -------------------------------------------- | --------------- | --------- | --- | --- | ------------- |
| Bumplesstransferiseasytoobtainforacontroller |                 |           |     |     | inincremental |
form. This is shown in Figure 3.34. The integrator is provided with
a switch so that the signals are either chosen from the manual or
the automatic increments. Since the switching only influences the
| increments | there will | not be | any large | transients. |     |
| ---------- | ---------- | ------ | --------- | ----------- | --- |
A similar mechanism can be used in the series, or interacting,
(see
implementation of a PID controller shown in Figure 3.8 Figure
3.35). In this case there will be a switching transient if the output of
| the PD | part is not zero | at the | switching | instant. |     |
| ------ | ---------------- | ------ | --------- | -------- | --- |
Forcontrollerswithparallelimplementation,theintegratorofthe
PIDcontrollercanbeusedtoaddupthechangesinmanualmode.The
controller shown in Figure 3.36 is such a system. This system gives
a smooth transition between manual and automatic mode provided

| 104 Chapter | 3 PID Control |     |
| ----------- | ------------- | --- |
+
| –   | MCU |     |
| --- | --- | --- |
M u
1
A   s
y
  sp
Inc PID
y
Figure 3.34 Bumpless transfer in a controller with incremental
| output. MCU | stands for manual | controlunit. |
| ----------- | ----------------- | ------------ |
+
| –   | MCU |     |
| --- | --- | --- |
u
M Σ
A
y
  sp
PD
y 1
+sT
  1
i
| Figure 3.35 | BumplesstransferinaPIDcontrollerwithaspecial |     |
| ----------- | -------------------------------------------- | --- |
seriesimplementation.
PD
A
M
A
 ∆ I u
|     | Σ   | 1 Σ    |
| --- | --- | ------ |
| +   |     |   s    |
−
M
− +
Σ
Figure 3.36 A PID controller where one integrator is used both
to obtain integral action in automatic mode and to sum the incre-
| mentalcommands | in manualmode. |     |
| -------------- | -------------- | --- |

|     |     |     | 3.7 | Operational Aspects | 105 |
| --- | --- | --- | --- | ------------------- | --- |
1
Σ
|     |     | T   |     | +   |     |
| --- | --- | --- | --- | --- | --- |
t
–
| + 1   | Σ   | 1    |     |     |     |
| ----- | --- | ---- | --- | --- | --- |
| − T   |     | s    |     |     |     |
|     m |     |      |     |     |     |
y
sp
PD
 y
M
| e K |     |     |     |     | u   |
| --- | --- | --- | --- | --- | --- |
|     | Σ   | 1   | Σ   |     |     |
s
| T   |     |       |     |     |     |
| --- | --- | ----- | --- | --- | --- |
| i   |     |       |     | A   |     |
|     |     |       |     | –   | +   |
Σ
1
T
t
| Figure   | 3.37 PID         | controller | with parallel | implementation | that |
| -------- | ---------------- | ---------- | ------------- | -------------- | ---- |
| switches | smoothly between | manual     | and automatic | control.       |      |
that the switch is made when the output of the PD block is zero. If
| this is not | the case, there | will be | a switching | transient. |     |
| ----------- | --------------- | ------- | ----------- | ---------- | --- |
It is also possible to use a separate integrator to add the incre-
mental changes from the manual control device. To avoid switching
transients in such a system, it is necessary to make sure that the
integrator in the PID controller is reset to a proper value when the
controllerisinmanualmode.Similarly,theintegratorassociatedwith
manualcontrol mustberesettoaproper value whenthecontroller is
inautomaticmode.ThiscanberealizedwiththecircuitshowninFig-
| ure3.37.Withthis | system | theswitch | between | manualandautomatic |     |
| ---------------- | ------ | --------- | ------- | ------------------ | --- |
is smooth even if the control error or its derivative is different from
zero at the switching instant. When the controller operates in man-
ual mode, as is shown in Figure 3.37, the feedback from the output
v of the PID controller tracks the output u. With efficient tracking
the signal v will thus be close to u at all times. There is a similar
tracking mechanism that ensures that the integrator in the manual
| control circuit | tracks the | controller | output. |     |     |
| --------------- | ---------- | ---------- | ------- | --- | --- |
BumplessParameterChanges
A controller is a dynamical system. A change of the parameters of
a dynamical system will naturally result in changes of its output.
Changes in the output can be avoided, in some cases, by a simulta-
neous change of the state of the system. The changes in the output
will also depend on the chosen realization. With a PID controller it

| 106 | Chapter 3 | PID Control |     |     |     |
| --- | --------- | ----------- | --- | --- | --- |
is natural to require that there be no drastic changes in the output
if the parameters are changed when the error is zero. This will hold
for all incremental algorithms because the output of an incremental
algorithm is zero when the input is zero, irrespective of the param-
eter values. It also holds for a position algorithm with the structure
showninFigure 3.8.Foraposition algorithm itdepends, however, on
| the implementation. |     | Assume | that the state | is chosen as |     |
| ------------------- | --- | ------ | -------------- | ------------ | --- |
(cid:1)t
= e(τ)dτ
x I
| when | implementing | the algorithm. | The integral | term is then |     |
| ---- | ------------ | -------------- | ------------ | ------------ | --- |
K
=
I x I
T
i
Any change of K or T will then result in a change of I. To avoid
i
bumpswhentheparametersarechanged,itisessentialthatthestate
| be chosen | as  |     |     |     |     |
| --------- | --- | --- | --- | --- | --- |
(cid:1)t
K(τ)
|     |     | x = | e(τ)dτ |     |     |
| --- | --- | --- | ------ | --- | --- |
|     |     | I   | T(τ)   |     |     |
i
| when | implementing | the integral | term. |     |     |
| ---- | ------------ | ------------ | ----- | --- | --- |
With sensible precautions, it is easy to ensure bumpless parame-
ter changes if parameters are changed when the error is zero. There
is, however, one case where special precautions have to be taken,
namely, if setpoint weighting (Equation 3.20)is used. To have bump-
less parameter changes in such a case it is necessary that the quan-
P+I
| tity | be invariant | to parameter | changes. | This means that | when |
| ---- | ------------ | ------------ | -------- | --------------- | ---- |
Track
Σ
1
T
t
|     | Manual | 1   | Σ   | 1      |     |
| --- | ------ | --- | --- | ------ | --- |
|     |        | T   |     |   s    |     |
     m
TR
M
M
|     |     | Figure 3.38 | Manual controlmodule. |     |     |
| --- | --- | ----------- | --------------------- | --- | --- |

|     |     |     |     | 3.7 | Operational Aspects | 107 |
| --- | --- | --- | --- | --- | ------------------- | --- |
TR
M
| Manual |     | M   |     |     |     |     |
| ------ | --- | --- | --- | --- | --- | --- |
input
Manual
TR
M
| set point |     | M   |     |     |     |     |
| --------- | --- | --- | --- | --- | --- | --- |
External
M
| set point |     |     | SP  |     |     |     |
| --------- | --- | --- | --- | --- | --- | --- |
| Measured  |     |     | MV  | PID |     |     |
| value     |     |     |     |     | A   |     |
TR
| Figure  | 3.39             | A reasonably | complete | PID        | controller with | anti- |
| ------- | ---------------- | ------------ | -------- | ---------- | --------------- | ----- |
| windup, | automatic-manual |              | mode,    | and manual | and external    | set-  |
point.
parameters are changed, the state I should be changed as follows
|     | =     | + (b        | −y)−     |       | (b −y)   | (3.41) |
| --- | ----- | ----------- | -------- | ----- | -------- | ------ |
|     | I new | I old K old | old y sp | K new | new y sp |        |
Tobuildautomationsystemsitisusefultohavesuitablemodules.
Figure 3.38 shows the block diagram for a manual control module. It
has two inputs, a tracking input and an input for the manual con-
trol commands. The system has two parameters, the time constant
T for the manual control input and the reset time constant T. In
| m   |     |     |     |     |     | t   |
| --- | --- | --- | --- | --- | --- | --- |
digital implementations it is convenient to add a feature so that the
command signal accelerates as long as one of the increase-decrease
buttons are pushed. Using the module for PID control and the man-
ual control module in Figure 3.38, it is straightforward to construct
a complete controller. Figure 3.39 shows a PID controller with inter-
nal or external setpoints via increase/decrease buttons and manual
automatic mode. Notice that the system only has two switches.
ComputerCode
As an illustration, the following is a computer code for a PID algo-
rithm. The controller handles both anti-windup and bumpless trans-
fer.
| "Compute  |     | controller | coefficients |     |      |     |
| --------- | --- | ---------- | ------------ | --- | ---- | --- |
| bi=K*h/Ti |     |            | "integral    |     | gain |     |
ad=(2*Td-N*h)/(2*Td+N*h)
| bd=2*K*N*Td/(2*Td+N*h) |     |     | "derivative |     | gain |     |
| ---------------------- | --- | --- | ----------- | --- | ---- | --- |
a0=h/Tt

| 108 | Chapter   | 3 PID     | Control |     |     |     |     |     |
| --- | --------- | --------- | ------- | --- | --- | --- | --- | --- |
|     | "Bumpless | parameter | changes |     |     |     |     |     |
I=I+Kold*(bold*ysp-y)-Knew*(bnew*ysp-y)
|     | "Control                | algorithm |     |           |            |              |            |     |
| --- | ----------------------- | --------- | --- | --------- | ---------- | ------------ | ---------- | --- |
|     | r=adin(ch1)             |           |     | "read     | setpoint   | from         | ch1        |     |
|     | y=adin(ch2)             |           |     | "read     | process    | variable     | from       | ch2 |
|     | P=K*(b*ysp-y)           |           |     | "compute  |            | proportional | part       |     |
|     | D=ad*D-bd*(y-yold)      |           |     | "update   | derivative |              | part       |     |
|     | v=P+I+D                 |           |     | "compute  |            | temporary    | output     |     |
|     | u=sat(v,ulow,uhigh)     |           |     | "simulate |            | actuator     | saturation |     |
|     | daout(ch1)              |           |     | "set      | analog     | output       | ch1        |     |
|     | I=I+bi*(ysp-y)+ao*(u-v) |           |     | "update   | integral   |              |            |     |
|     | yold=y                  |           |     | "update   | old        | process      | output     |     |
The computation of the coefficients should be done only when the
controllerparametersarechanged.Precomputationofthecoefficients
ad, ao, bd, and bi saves computer time in the main loop. The main
program must be called once every sampling period. The program
has three states: yold, I,and D. One state variable can be eliminated
at the cost of a less readable code. Notice that the code includes
derivation of the process output only, proportional action on part of
| the | error      | only (b(cid:6)=1), | and anti-windup. |     |     |     |     |     |
| --- | ---------- | ------------------ | ---------------- | --- | --- | --- | --- | --- |
| 3.8 | Commercial |                    | Controllers      |     |     |     |     |     |
Commercial PID controllers differ in the structure of the control
|     | (standard-series-parallel, |     |     | absolute-velocity), |     |     |                   |     |
| --- | -------------------------- | --- | --- | ------------------- | --- | --- | ----------------- | --- |
| law |                            |     |     |                     |     |     | the parameteriza- |     |
tion, the limitation of high-frequency gain (filtering), and in how the
setpoint is introduced. To be able to tune a controller, it is necessary
to know the structure and the parameterization of the control algo-
rithm.Thisinformation is,unfortunately, notusually available inthe
controller manuals. In this section, we have tried to summarize the
| properties |     | of controllers | from | some | different | manufacturers. |     |     |
| ---------- | --- | -------------- | ---- | ---- | --------- | -------------- | --- | --- |
Different structures of the PID algorithm were presented in Sec-
|     |     |     |     |     |     | U(s),Y(s),andY |     | (s) |
| --- | --- | --- | --- | --- | --- | -------------- | --- | --- |
tion3.4.Tosummarizetheresultsweintroduce
sp
as the Laplace transforms of process input u, process output y, and
|          |     |                   |     | E(s)= | (s)−Y(s)denote |     |            |     |
| -------- | --- | ----------------- | --- | ----- | -------------- | --- | ---------- | --- |
| setpoint |     | y sp .Furthermore | let |       | Y sp           |     | theLaplace |     |
transform of the control error. Three different structures are used in
the commercial controllers. The standard form, or ISA form, is given
by
|     |     | (cid:5) |     |      |     |         | (cid:6) |     |
| --- | --- | ------- | --- | ---- | --- | ------- | ------- | --- |
|     |     |         | 1   |      | sT  |         |         |     |
|     | =   | −Y+     |     | E+   | d   | (cY −Y) |         |     |
| I.  | U   | K bY sp |     | 1+sT | /N  | sp      |         |     |
sT
|     |        |               | i   |     | d   |     |     |     |
| --- | ------ | ------------- | --- | --- | --- | --- | --- | --- |
| the | series | form is given | by  |     |     |     |     |     |

3.9 When Can PID Control Be Used? 109
(cid:5)(cid:2) (cid:3) (cid:2) (cid:3) (cid:6)
1 1+scT (cid:8) 1 1+sT (cid:8)
II. U = K (cid:8) b+ d Y − 1+ d Y
sT(cid:8) 1+sT(cid:8)/N sp sT(cid:8) 1+sT(cid:8)/N
i d i d
and the parallel form by
K (cid:8)(cid:8) K (cid:8)(cid:8) s
III. U = K (cid:8)(cid:8)(bY −Y)+ i E+ d (cY −Y)
sp s 1+sK(cid:8)(cid:8)/(NK(cid:8)(cid:8)) sp
d
The relations between the different parameters are discussed in Sec-
tion 3.4. Recall that the parameters b and c are the weightings that
influence the setpoint response. The values of b and c used are typi-
cally 0 or 1 in commercial controllers. This does not use the power of
setpoint weighting fully aswas discussed in Section 3.4.The setpoint
weight factors band c are chosen differently in different commercial
controllers.
Thehigh-frequency gainofthederivative termislimited toavoid
noise amplification. This gain limitation can be parameterized in
terms of the parameter N.
The sampling period is an important parameter of a digital PID
controller, which limits how fast processes can be controlled. The
values used in commercial controllers vary significantly.
Table3.2summarizesthepropertiesofsomecommoncommercial
PID controllers.
3.9 When Can PID Control Be Used?
Therequirementsonacontrolsystemmayincludemanyfactors,such
as response to command signals, insensitivity to measurement noise
andprocessvariations, andrejectionofloaddisturbances. Thedesign
ofacontrolsystemalsoinvolves aspectsofprocessdynamics,actuator
saturation, and disturbance characteristics. It may seem surprising
that a controller as simple as the PID controller can work so well.
The general empirical observation is that most industrial processes
can be controlled reasonably well with PID control provided that
the demands on the performance of the control are not too high.
In the following paragraphs we delve further into this issue by first
considering caseswherePIDcontrol issufficient andthen discussing
somegenericproblemswheremoresophisticated controlisadvisable.
WhenIs PI ControlSufficient?
Derivative action is frequently not used. It is an interesting observa-
tion that many industrial controllers only have PI action and that in
others the derivative action can be (and frequently is) switched off.
It can be shown that PI control is adequate for all processes where

110
|     |     | Table 3.2  | Properties           | of the PID | algorithmsin |         | some        | commercialcontrollers. |     |       | The    |     |     |     |
| --- | --- | ---------- | -------------------- | ---------- | ------------ | ------- | ----------- | ---------------------- | --- | ----- | ------ | --- | --- | --- |
|     |     | structures | of thecontrollersare |            | labeled      | ISA(I), | series(II), |                        | and | ideal | (III). |     |     |     |
Chapter
| Controller |     |     |     | Structure |     | Setpoint  |     |     | Derivativegain |            |     |     | Sampling |     |
| ---------- | --- | --- | --- | --------- | --- | --------- | --- | --- | -------------- | ---------- | --- | --- | -------- | --- |
|            |     |     |     |           |     | weighting |     |     |                | limitation |     |     | period   |     |
3
|     |     |     |     |     |     | b   |     | c   |     | N   |     |     | (s) |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
PID
| Allen Bradley |     | PLC 5 |     | I, III |     | 1.0 |     | 1.0 |     | none |     | load | dependent |     |
| ------------- | --- | ----- | --- | ------ | --- | --- | --- | --- | --- | ---- | --- | ---- | --------- | --- |
Control
| Bailey Net                | 90    |          |        | II, III |     | 0.0or 1.0 | 0.0or | 1.0 |     | 10   |     |       | 0.25   |        |
| ------------------------- | ----- | -------- | ------ | ------- | --- | --------- | ----- | --- | --- | ---- | --- | ----- | ------ | ------ |
| Fisher ControlsProvox     |       |          |        | II      |     | 1.0       |       | 0.0 |     | 8    |     | 0.1,  | 0.25,  | or 1.0 |
| Fisher ControlsDPR        |       | 900,     | 910    | II      |     | 0.0       |       | 0.0 |     | 8    |     |       | 0.2    |        |
| Fisher Porter             |       | MicroDCI |        | II      |     | 1.0       | 0.0or | 1.0 |     | none |     |       | 0.1    |        |
| Foxboro                   | Model | 761      |        | II      |     | 1.0       |       | 0.0 |     | 10   |     |       | 0.25   |        |
| Honeywell                 | TDC   |          |        | II      |     | 1.0       |       | 1.0 |     | 8    |     | 0.33, | 0.5,or | 1.0    |
| Moore ProductsType        |       | 352      |        | II      |     | 1.0       |       | 0.0 |     | 1−30 |     |       | 0.1    |        |
| AlfaLavalAutomationECA40, |       |          | ECA400 | II      |     | 0.0       |       | 0.0 |     | 8    |     |       | 0.2    |        |
| Taylor Mod                | 30    |          |        | II      |     | 0.0or 1.0 |       | 0.0 |     | 17or | 20  |       | 0.25   |        |
3.3−10
| Toshiba  | TOSDIC | 200  |     | II  |     | 1.0       |       | 1.0 |     |      |     |     | 0.2        |     |
| -------- | ------ | ---- | --- | --- | --- | --------- | ----- | --- | --- | ---- | --- | --- | ---------- | --- |
| Turnbull | TCS    | 6000 |     | II  |     | 1.0       |       | 1.0 |     | none |     |     | 0.036−1.56 |     |
| Yokogawa | SLPC   |      |     | I   |     | 0.0or 1.0 | 0.0or | 1.0 |     | 10   |     |     | 0.1        |     |

|     |     |     | 3.9 | When Can | PID Control | Be Used? | 111 |
| --- | --- | --- | --- | -------- | ----------- | -------- | --- |
thedynamics areessentially ofthefirstorder(level controls insingle
etc).
tanks, stirred tank reactors with perfect mixing, Itis fairly easy
to find out if this is the case by measuring the step response or the
frequency response ofthe process. Ifthestep response looks like that
of a first-order system or, more precisely, if the Nyquist curve lies
in the first and the fourth quadrants only, then PI control is suffi-
cient. Another reason is that the process has been designed so that
its operation does not require tight control. Then, even if the process
hashigher-order dynamics, whatitneeds isanintegral actiontopro-
vide zero steady-state offset and an adequate transient response by
| proportional | action. |                    |     |     |     |     |     |
| ------------ | ------- | ------------------ | --- | --- | --- | --- | --- |
| WhenIs       | PID     | ControlSufficient? |     |     |     |     |     |
Similarly, PID control is sufficient for processes where the dominant
dynamics are of the second order. For such processes there are no
| benefits | gained | by using | a more | complex | controller. |     |     |
| -------- | ------ | -------- | ------ | ------- | ----------- | --- | --- |
Atypicalcaseofderivativeactionimprovingtheresponseiswhen
the dynamics are characterized by time constants that differ in mag-
nitude. Derivative action can then profitably be used to speed up the
response. Temperature control is a typical case. Derivative control is
alsobeneficialwhentightcontrolofahigher-ordersystemisrequired.
The higher-order dynamics would limit the amount of proportional
gain for good control. With a derivative action, improved damping is
provided, hence, a higher proportional gain can be used to speed up
| the transient | response. |                             |     |     |     |     |     |
| ------------- | --------- | --------------------------- | --- | --- | --- | --- | --- |
| WhenIs        | More      | SophisticatedControlNeeded? |     |     |     |     |     |
The benefits of using a more sophisticated controller than the PID is
| demonstrated |     | by some   | examples | below. |     |     |     |
| ------------ | --- | --------- | -------- | ------ | --- | --- | --- |
| Higher-Order |     | Processes |          |        |     |     |     |
When the system is of a higher order than two, the control can be
improved byusing amorecomplex controller than thePIDcontroller.
| This is | illustrated | by the  | following         | example. |         |     |     |
| ------- | ----------- | ------- | ----------------- | -------- | ------- | --- | --- |
| EXAMPLE | 3.3         | Control | of a higher-order |          | process |     |     |
Consider a third-order process described by the following transfer
function.
1
G(s)=
(s+1)3

| 112 Chapter | 3   | PID Control |     |     |     |     |
| ----------- | --- | ----------- | --- | --- | --- | --- |
y
| sp  |     |     | CC  |     |     |     |
| --- | --- | --- | --- | --- | --- | --- |
1
| 0.5 |     |     | PID |     |     |     |
| --- | --- | --- | --- | --- | --- | --- |
0
| 0   |     | 10  |     | 20  |     | 30  |
| --- | --- | --- | --- | --- | --- | --- |
8
CC
4
PID
0
| 0      |              | 10  |                    | 20  |                   | 30  |
| ------ | ------------ | --- | ------------------ | --- | ----------------- | --- |
| Figure | 3.40 Control |     | of the third-order |     | system in Example | 3.3 |
using a PID controller (PID) and a more complex controller (CC).
Thefigureshowsresponsestoasetpointchange,aloaddisturbance,
| andfinally | ameasurementdisturbance. |             |        | Theupper | diagramshows      |     |
| ---------- | ------------------------ | ----------- | ------ | -------- | ----------------- | --- |
| setpoint   | y and                    | measurement | signal | y, and   | the lower diagram |     |
sp
| shows controlsignal |     | u.  |     |     |     |     |
| ------------------- | --- | --- | --- | --- | --- | --- |
Figure 3.40 shows the control obtained using a PID controller and a
more complex controller of higher order. The PID controller has the
parameters K = 3.4,T = 2.0 and T = 0.6. The PID controller is
|               |                          | i   |             | d   |     |     |
| ------------- | ------------------------ | --- | ----------- | --- | --- | --- |
| compared with | a controller             |     | of the form |     |     |     |
|               | R(s)u(t)=−S(s)y(t)+T(s)y |     |             |     | (t) |     |
sp
| with the following |       | controller       | polynomials |     |     |     |
| ------------------ | ----- | ---------------- | ----------- | --- | --- | --- |
|                    | R(s)= | s(s2+11.5s+57.5) |             |     |     |     |
S(s)=144s3+575s2+870s+512
T(s)=8s3+77s2+309s+512
Thebenefits of using a morecomplex controller in the caseof higher-
| order dynamics | is   | clearly | demonstrated | in  | the figure. |     |
| -------------- | ---- | ------- | ------------ | --- | ----------- | --- |
| Systems with   | Long | Dead    | Time         |     |             |     |
Control of systems with a dominant time delay are notoriously dif-
ficult. It is also a topic on which there are many different opinions
concerningthemeritofPIDcontrol.Thereseemstobegeneralagree-
ment that derivative action does not help much for processes with
dominant time delays. For open-loop stable processes, the response
to command signals can be improved substantially by introducing
dead-time compensation. The load disturbance rejection can also be
improved to some degree because a dead-time compensator allows a
higher loop gain than a PID controller. Systems with dominant time
| delays are thus | candidates |     | for more | sophisticated | control. |     |
| --------------- | ---------- | --- | -------- | ------------- | -------- | --- |

|      |     |     | 3.9 | When | Can PID | Control | Be  | Used? 113 |
| ---- | --- | --- | --- | ---- | ------- | ------- | --- | --------- |
| y sp | SP  | PI  |     |      |         |         |     |           |
1
0
| 0   |     | 20  |     | 40  |     | 60  |     | 80  |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
1
SP
0.6
PI
0.2
| 0      |      | 20                                          |     | 40  |     | 60  |     | 80  |
| ------ | ---- | ------------------------------------------- | --- | --- | --- | --- | --- | --- |
| Figure | 3.41 | ControlofthesysteminExample3.4withPIcontrol |     |     |     |     |     |     |
(PI) and with a Smith predictor (SP). The upper diagram shows
setpoint y sp and measurement signal y, and the lower diagram
| shows    | controlsignal |           | u.  |                 |     |     |     |     |
| -------- | ------------- | --------- | --- | --------------- | --- | --- | --- | --- |
| EXAMPLE  | 3.4           | Dead-time |     | compensation    |     |     |     |     |
| Consider | a process     | described |     | by the equation |     |     |     |     |
dy(t)
=−0.5y(t)+0.5u(t−4)
dt
| Theprocesshasatimeconstant |     |     |     | of2andatimedelayof4timeunits. |     |     |     |     |
| -------------------------- | --- | --- | --- | ----------------------------- | --- | --- | --- | --- |
This process was first controlled by a PI controller with a gain of 0.2
|        |          |         |     | (see   | 3.41). |     |        |            |
| ------ | -------- | ------- | --- | ------ | ------ | --- | ------ | ---------- |
| and an | integral | time of | 2.5 | Figure |        | The | figure | also shows |
the properties of the control obtained with a Smith predictor. The
response to setpoint changes is much improved, while the difference
is less for the load disturbance. When dead-time compensation was
used, the gain in the PI controller was increased to K = 1, and the
=1.
| integral | time | was T |     |     |     |     |     |     |
| -------- | ---- | ----- | --- | --- | --- | --- | --- | --- |
i
| Systems | with | Oscillatory |     | Modes |     |     |     |     |
| ------- | ---- | ----------- | --- | ----- | --- | --- | --- | --- |
Systems with oscillatory modes that occur when there are inertias
and compliances is another case where PID control is not sufficient.
There are several approaches to systems of that type. In the so-
called notch filter approach, no attempt is made to damp the oscilla-
tory modes, but an effort is made to reduce the signal transmission
throughthecontrollerbyafilterthatdrasticallyreducessignaltrans-
missionattheresonantfrequency.APIDcontrollermaybeusedwhen
there is only one dominant oscillatory mode. Notch filter action can
be achieved by judicious choice of the controller parameters. In this
case, parameters T and T should be chosen so that the numerator
|     |     | i   | d   |     |     |     |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
(3.15)
| has complex |     | roots. The | interacting | form | in  | Equation |     | does not |
| ----------- | --- | ---------- | ----------- | ---- | --- | -------- | --- | -------- |
| work well   | in  | this case. |             |      |     |          |     |          |

| 114 | Chapter | 3 PID Control |     |     |     |     |     |     |
| --- | ------- | ------------- | --- | --- | --- | --- | --- | --- |
y
sp
1
y
0
| 0   |     | 20  |     |     | 40  |     |     | 60  |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
1
u
0
| 0   |     | 20  |     |     | 40  |     |     | 60  |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
Figure 3.42 Response of the closed-loop system to setpoint and
load disturbances. The graphs show setpoint y , process output y,
sp
|      |         |           |                |     |            |     | =   | −0.25, |
| ---- | ------- | --------- | -------------- | --- | ---------- | --- | --- | ------ |
| and  | control | signal u. | The controller |     | parameters | are | K   |        |
| =−1, |         | b=0.      |                |     |            |     |     |        |
| T    | and     |           |                |     |            |     |     |        |
i
| EXAMPLE  | 3.5         | PI control | of      | a system | with         | oscillatory |     | modes |
| -------- | ----------- | ---------- | ------- | -------- | ------------ | ----------- | --- | ----- |
| Consider | for example | a          | process | with     | the transfer | function    |     |       |
ab2
G(s)=
(s+a)(s2+b2)
|       | =       | =    |             |     |         |          |     |             |
| ----- | ------- | ---- | ----------- | --- | ------- | -------- | --- | ----------- |
| where | a 1 and | b 5. | The process |     | has two | undamped |     | oscillatory |
poles. If these poles are neglected, the process is simply a first-order
systemthatcanconvenientlybecontrolledbyaPIcontroller.Attempt-
ing to control the process with a PI controller, wefind that controller
parameters K and T have to be negative. Reasonable values of the
i
|            |     | = −0.25 |     | =   | −1.    |      |       |         |
| ---------- | --- | ------- | --- | --- | ------ | ---- | ----- | ------- |
| parameters | are | K       | and | T   | Figure | 3.42 | shows | the re- |
i
sponse of the closed-loop system to setpoint and load disturbances.
Noticethatthesetpoint commanddoesnotexcitetheoscillatory poles
somuch. These modes areclearly visible, however, in the load distur-
banceresponse.Withanonzero bthesetpoint changeswillalsoexcite
| the oscillatory |        | modes, as  | is seen | in Figure | 3.43.         |     |         |        |
| --------------- | ------ | ---------- | ------- | --------- | ------------- | --- | ------- | ------ |
| The             | system | in Example | 3.5     | gives     | only moderate |     | damping | of the |
oscillatory modes.Forsystemswheretheoscillatory modesareinside
the servo bandwidth, it is necessary to have a controller with com-
plex zeros. Such a controller can provide damping of the oscillatory
modes because the poles will beattracted tothe controller zeros. The
| controller | zeros | are the | zeros of | the function |     |     |         |        |
| ---------- | ----- | ------- | -------- | ------------ | --- | --- | ------- | ------ |
|            |       |         |          | (cid:5)      |     |     | (cid:6) |        |
|            |       | 1       |          | T            | 1   | 1   |         |        |
|            |       | 1+ +sT  | =        | d s2+        |     | s+  |         | (3.42) |
d
|        |          | sT               |     | s   | T              | TT  |     |     |
| ------ | -------- | ---------------- | --- | --- | -------------- | --- | --- | --- |
|        |          | i                |     |     | d              | i   | d   |     |
| Assume | that the | zeros correspond |     | to  | the polynomial |     |     |     |
s2+2ζωs+ω2

|     |     |     | 3.9 | When | Can PID | Control | Be Used? | 115 |
| --- | --- | --- | --- | ---- | ------- | ------- | -------- | --- |
y
sp
1
y
0
| 0   |     | 20  |     |     | 40  |     |     | 60  |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
1
u
0
| 0   |     | 20  |     |     | 40  |     |     | 60  |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
Figure 3.43 Response of the closed-loop system to setpoint and
load disturbances. The graphs show setpoint y , process output y,
sp
= −0.25,
| and  | control signal | u.  | The controller |     | parameters |     | are K |     |
| ---- | -------------- | --- | -------------- | --- | ---------- | --- | ----- | --- |
| =−1, | b=1.           |     |                |     |            |     |       |     |
| T    | and            |     |                |     |            |     |       |     |
i
we find
|     |     |     | ωT  | =2ζ |     |     |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
i
(3.43)
1
|     |     |     | ωT  | =   |     |     |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
d 2ζ
Hence
T
|     |     |     |     | i =4ζ2 |     |     |     | (3.44) |
| --- | --- | --- | --- | ------ | --- | --- | --- | ------ |
T
d
|           | ζ       |           |     |        |          |        |     | ζ =  |
| --------- | ------- | --------- | --- | ------ | -------- | ------ | --- | ---- |
| The value | of used | typically |     | has to | be quite | small, | say | 0.2, |
whichgives T/T =0.16.Thisratioissignificantly differentfromthe
i d
<
commonly used value 4. Also, notice that a controller with T i 4T d
can not be realized using the series form. To deal with oscillatory
| systems | it is thus | essential | that | the parallel |     | form | is used. |     |
| ------- | ---------- | --------- | ---- | ------------ | --- | ---- | -------- | --- |
The above calculation isbased on a simplified PID controller. For
a controller where the derivative term has a limited high-frequency
|                 | (3.42) |     | (3.43) |      |          |     |     |     |
| --------------- | ------ | --- | ------ | ---- | -------- | --- | --- | --- |
| gain, Equations |        | and |        | are  | replaced | by  |     |     |
|                 |        |     | 1      |      | sT       |     |     |     |
|                 |        |     | 1+     | +    | d        |     |     |     |
|                 |        |     |        | 1+sT | /N       |     |     |     |
sT
|     |     |     |     | i        | d   |     |     |     |
| --- | --- | --- | --- | -------- | --- | --- | --- | --- |
| and |     |     |     | (cid:22) |     |     |     |     |
1
|     |     | ωT  | =±ζ+ | ζ2− |     |     |     |     |
| --- | --- | --- | ---- | --- | --- | --- | --- | --- |
i
N +1
|     |     |     | (cid:23) |          |     | (cid:24) |     |        |
| --- | --- | --- | -------- | -------- | --- | -------- | --- | ------ |
|     |     |     |          | (cid:22) |     |          |     | (3.45) |
1
|     |     | ωT  | =∓  | ζ− ζ2− |     |     |     |     |
| --- | --- | --- | --- | ------ | --- | --- | --- | --- |
|     |     | d   |     |        |     | +1  |     |     |
N
It is desirable to have N as small as possible, this value is
1
|     |     |     | N   | = −1 |     |     |     |     |
| --- | --- | --- | --- | ---- | --- | --- | --- | --- |
ζ2

| 116 Chapter | 3 PID | Control |     |     |
| ----------- | ----- | ------- | --- | --- |
which gives
|     |     | ωT  | =ζ  |     |
| --- | --- | --- | --- | --- |
i (3.46)
|     |     | ωT  | = Nζ |     |
| --- | --- | --- | ---- | --- |
d
Hence
|     |     | T 1 | ζ2   |        |
| --- | --- | --- | ---- | ------ |
|     |     | i = | =    | (3.47) |
|     |     | T N | 1−ζ2 |        |
d
Forsystems with oscillatory modes, thenormal situation isthat T i is
much smaller than T . Notice also that the choice of parameter N is
d
| critical for | these applications. |     |     |     |
| ------------ | ------------------- | --- | --- | --- |
Summary
When the dynamics of the process to be controlled are simple, a PID
controller issufficient.Whenthedynamicsbecomemorecomplicated,
the control performance can be improved by using a more sophisti-
cated controller structure than the PID. Examples of such processes
have been given above. We end this section with some additional ex-
amples.
Forsomesystemswithlargeparametervariationsitispossibleto
design linear controllers that allow operation over a wide parameter
| range. Such | controllers | are, however, | often of high | order. |
| ----------- | ----------- | ------------- | ------------- | ------ |
The control of process variables that areclosely related to impor-
tantquality variables maybeof asignificant economic value. Insuch
control loops it is frequently necessary to select the controller with
respect to the disturbance characteristics. This often leads to strate-
giesthatarenotofthePIDtype.Theseproblemsareoftenassociated
| with time          | delays. |                                |     |          |
| ------------------ | ------- | ------------------------------ | --- | -------- |
| Ageneralcontroller |         | attemptstomodelthedisturbances |     | actingon |
the system. Since a PID controller has limited complexity, it cannot
model complex disturbance behavior in general nor periodic distur-
| bances in | particular. |     |     |     |
| --------- | ----------- | --- | --- | --- |
| 3.10      | Conclusions |     |     |     |
A detailed presentation of the PID algorithm has been given. Sev-
eral modifications of the “textbook” version must be made to obtain
a practical, useful controller. Problems that must be handled are, for
example, integral wind-up and introduction of setpoint values. In a
computer implementation, a discrete version of the PID algorithm is
needed. Several methods toderivediscrete PIDalgorithms have been
described. Additional problems due to the sampling procedure must

3.11 References 117
be handled, such as the design of a prefilter to avoid aliasing. A dis-
cussionofthelimitations ofthePIDalgorithmandacharacterization
ofprocesses wherethePIDcontroller managestoperform thecontrol
have also been given.
3.11 References
Proportional feedback in the form of a centrifugal governor was used
to regulate the speed of windmills around 1750. In 1788 James Watt
usedasimilarsystemforspeedcontrolofsteamengines.Thebenefits
of integral action was discovered a little later. Feedback control with
proportional and integral action was rediscovered many times after
that. In the early stages, the development of controllers was closely
related to development of sensors and actuators. Sensing, actuation,
and control were often combined in the same device.
The PID controller, in the form we know it today, emerged in
the period from 1915 to 1940. It coincided with the development of
legendary control companies such as Bristol, Fisher, Foxboro, Honey-
well, Leeds & Northrup, and Taylor Instrument. Proportional and
integral action had been used for a long time. Integral action was
often called automatic reset, because it replaced a manual reset that
wasusedinproportional controllers toobtainthecorrectsteadystate
value.Thepotentialofacontrollerthatcouldanticipatefuturecontrol
errors was discussed in the 1920s. However, it took some time before
theideacouldbeimplemented.Acontrollerwithderivativeactionwas
introduced by Ralph Clarridge of the Taylor Instrument Company in
1935. At that time the function was called “pre-act.” An interesting
overviewoftheearlyhistoryofPIDcontrollersisgivenin(Stock,1987
88). There is also much interesting material in publications from the
instrument companies. The interview with Nichols, who is one of the
pioneers in our field, in (Blickley, 1990) gives a perspective on the
early development.
It is interesting to observe that feedback was crucial for the con-
struction of the controller itself. The early pneumatic systems used
the idea that an essentially linear controller can be obtained by a
feedback loop composed of linear passive components and a nonlin-
ear amplifier, the flapper valve. Similar ideas wereused in electronic
controllers with electric motors and relays.
Manyofthepractically useful modifications ofthecontroller first
appeared as special hardware functions. They were not expressed in
mathematicalform.Anearlymathematicalanalysisofasteamengine
with a governor was made in (Maxwell, 1868). This analysis clearly
showed the difference between proportional and integral control. The
papers (Minorsky, 1922), (Küpfmüller, 1928), (Nyquist, 1932), and

| 118     | Chapter | 3    | PID Control |     |        |           |     |                |     |
| ------- | ------- | ---- | ----------- | --- | ------ | --------- | --- | -------------- | --- |
| (Hazen, | 1934)   |      |             |     |        |           |     |                |     |
|         |         | were | available   |     | at the | time when | the | PID controller |     |
wasdeveloped. However, there islittle evidence that theengineers in
the process control field knew about them. Process control, therefore,
(Grebe
developed independently. Two of the early papers were et al.,
1933), written by engineers at the Dow Chemical Company, (Ivanoff,
| 1934), | (Callender |     |         | 1936), | (Hartree |     | 1937). |     |     |
| ------ | ---------- | --- | ------- | ------ | -------- | --- | ------ | --- | --- |
|        |            |     | et al., |        | and      | et  | al.,   |     |     |
The PID controller has gone through an interesting development
because of the drastic technology changes that have happened since
1940. The pneumatic controller improved drastically by making sys-
tematic use of the force balance principle. Pneumatics was replaced
by electronics when the operational amplifier appeared in the 1950s.
| Averysignificantdevelopment |     |     |     |     | tookplacewiththeemergenceofcom- |     |     |     |     |
| --------------------------- | --- | --- | --- | --- | ------------------------------- | --- | --- | --- | --- |
puter control in the 1960s. In the early computer control systems the
computer commanded the setpoints of analog controllers. The next
stage of the development was direct digital control (DDC), where the
computer was controlling the actuator directly, see (Webb, 1967). A
digital computer was then used to implement many PID controllers.
This development led to a reconsideration of much of the fundamen-
|      |        |          |     | (Goff,1966b), |     | (L&N,1968), |     | (Moore |        |
| ---- | ------ | -------- | --- | ------------- | --- | ----------- | --- | ------ | ------ |
| tals | of PID | control, | see | e.g.          |     |             |     |        | etal., |
1970), and (Palmor and Shinnar, 1979). The appearance of micro-
processors in the 1970s made it possible to use digital control for
|        |      |              |     | (Stojić |     |           | 1986). |         |        |
| ------ | ---- | ------------ | --- | ------- | --- | --------- | ------ | ------- | ------ |
| single | loop | controllers, |     | see     | and | Petrović, |        | It also | led to |
the development of distributed control systems for process control,
(Lukas, 1986).
| where | the PID | controller |     | was | a key element, | see |     |     | As  |
| ----- | ------- | ---------- | --- | --- | -------------- | --- | --- | --- | --- |
thecomputing power of themicroprocessors increased itwas possible
tointroducetuningandadaptationinthesingleloopcontrollers. This
development started in the 1980s and has accelerated in the 1990s,
| see | (Åström | et al., | 1993). |     |     |     |     |     |     |
| --- | ------- | ------- | ------ | --- | --- | --- | --- | --- | --- |
It is interesting to observe that many facts about PID control
were rediscovered in connection with the shifts in technology. One
reason being that many practical aspects of PID control were con-
sidered as proprietory information that was not easily accessible in
public literature. Much useful information was also scattered in the
literature.
In spite of their wide spread use PID controllers are only treated
superficially in many textbooks and at university courses. The book
| (Shinskey, |     | 1988) |       |        |           |                |     |        |     |
| ---------- | --- | ----- | ----- | ------ | --------- | -------------- | --- | ------ | --- |
|            |     |       | gives | a good | coverage. | Implementation |     | issues | are |
discussed in (Goff, 1966b), (Takahashi et al., 1972), (Clarke, 1984),
(ÅströmandWittenmark,1990).Thepaper(ÅströmandSteingrímsson,
1991)
|     | describes |     | an implementation |     |     | on a digital | signal | processor, |     |
| --- | --------- | --- | ----------------- | --- | --- | ------------ | ------ | ---------- | --- |
which admits a very high sampling rate. The usefulness of a two-
|                   |     |     |           |             |     | in(Horowitz, |     | 1963).Theap- |     |
| ----------------- | --- | --- | --------- | ----------- | --- | ------------ | --- | ------------ | --- |
| degree-of-freedom |     |     | structure | isdiscussed |     |              |     |              |     |
plication to PID control is treated in (Shigemasa et al., 1987).
|     | The phenomena |     | of  | integral | windup | was well | known | in the | early |
| --- | ------------- | --- | --- | -------- | ------ | -------- | ----- | ------ | ----- |
analog implementations. The controller structures used were often

|     |     |     | 3.11 | References 119 |
| --- | --- | --- | ---- | -------------- |
such that windup was avoided. The anti-windup schemes were redis-
covered in connection with the development of direct digital control.
This is discussed in (Fertik and Ross, 1967). Much work on avoid-
ing windup have been done since then, and windup has now made
(Åström
| its way | into some | text books of control, | see | and Witten- |
| ------- | --------- | ---------------------- | --- | ----------- |
mark, 1984). There are many papers written on the windup phe-
|         | (Kramer | 1971),       | (Glattfelder |               |
| ------- | ------- | ------------ | ------------ | ------------- |
| nomena, | see     | and Jenkins, |              | and Schaufel- |
berger, 1983), (Krikelis, 1984), (Gallun et al., 1985), (Kapasouris
and Athans, 1985), (Glattfelder and Schaufelberger, 1986), (Howes,
1986),(Åström,1987b),(Hanusetal.,1987),(ChenandWang,1988),
(Glattfelder et al., 1988), (Hanus, 1988), (Zhang and Evans, 1988),
| (Åström |                | 1989), (Rundqwist, | 1990), | (Walgama |
| ------- | -------------- | ------------------ | ------ | -------- |
|         | and Rundqwist, |                    |        | and      |
and Sternby, 1990). Mode switching is treated in the paper (Åström,
1987b).
The Smith predictor for control of systems with long time delays
was presented in (Smith, 1957). The papers (Ross, 1977) and (Meyer
1976)
| et al., | compare | the Smith predictor | with the | PID controller. |
| ------- | ------- | ------------------- | -------- | --------------- |

Controller Design
4.1 Introduction
This chapter describes some methods for determining the parame-
ters of a PID controller. To obtain rational methods for designing
controllers it is necessary to define the main purpose of the control
system. This is done in Section 4.2.
The design methods differ with respect to the knowledge of the
process dynamics they require. A PI controller is described by two
parameters (K and T) and a PID controller by three or four pa-
i
rameters (K, T, T , and N). The classical Ziegler-Nichols methods
i d
are discussed in Section 4.3. In these methods process dynamics are
characterized by two parameters. One parameter is related to the
process gain and the other describes how fast the process is. In the
step response method, the parameters are simple characteristics ob-
tained fromthestepresponse. Inthefrequency response method, the
parameters are the ultimate gain and the ultimate frequency.
An obvious extension of the frequency response method is to de-
velop methods that are based on more knowledge of the open-loop
transfer function, e.g., the slope of the transfer function or its values
at two or more frequencies. In Section 4.4 we discuss various meth-
ods that are based on attempts to shape the loop transfer function.
Section 4.5 treats analytical design methods, where the controller
transfer function is obtained from the specifications and the process
transfer function by a direct calculation.
One possibility for compromise between several different criteria
is to use optimization methods. This is discussed in Section 4.6. An-
other way to characterize process dynamics with few parameters is
touselow-order dynamic models withfew parameters. Suchmethods
are discussed in Section 4.7 where the design goal is to position all
the poles of the closed-loop system. It is shown that methods based
on dynamic models of first and second order lead to PI and PID con-
trollers.
Insteadofattemptingtopositionallclosed-looppoles,itcanbeat-
temptedtoassignonlyafewdominating poles. Suchmethodsaredis-
120

4.2 Specifications 121
cussed in Section 4.8.The approach leads tosystematic design meth-
ods and a unification of many other techniques. New simple design
methods based on the dominant pole design method are presented in
| Chapter 5.          |     |         |                    |     |               |
| ------------------- | --- | ------- | ------------------ | --- | ------------- |
| InSection4.9,design |     | methods | basedondisturbance |     | rejection are |
presented. Finally, conclusions and references are given in Sections
| 4.10 and 4.11. |     |     |     |     |     |
| -------------- | --- | --- | --- | --- | --- |
4.2 Specifications
When solving a control problem it is necessary to understand what
the primary goal of control is. Two common types of problems are to
follow the setpoint and to reject disturbances. It is also important to
| have an assessment |          | of the | major restrictions, | which | can be |
| ------------------ | -------- | ------ | ------------------- | ----- | ------ |
| • System           | dynamics |        |                     |       |        |
• Nonlinearities
• Disturbances
| • Process              | uncertainty |                   |                |             |     |
| ---------------------- | ----------- | ----------------- | -------------- | ----------- | --- |
| Typical specifications |             | on a              | control system | may include |     |
| • Attenuation          | of          | load disturbances |                |             |     |
| • Sensitivity          | to          | measurement       | noise          |             |     |
| • Robustness           | to          | model uncertainty |                |             |     |
| • Setpoint             | following   |                   |                |             |     |
Specifications can be expressed in many different ways. Features of
time responses for typical inputs is one possibility. Features of fre-
quency responses or transfer functions are other possibilities. Some
of the specifications such as attenuation and sensitivity to measure-
menterrors,areconflicting,andotherssuchassetpointfollowingand
| load disturbance | rejection |     | are nonconflicting. |     |     |
| ---------------- | --------- | --- | ------------------- | --- | --- |
For process control applications setpoint following is often less
important than load disturbance attenuation. Setpoint changes are
oftenonlymadewhentheproductionrateisaltered.Furthermore,the
response to setpoint changes can be improved by feeding the setpoint
through ramping functions or by adjusting the setpoint weightings
| described in | Section | 3.4. |     |     |     |
| ------------ | ------- | ---- | --- | --- | --- |
LoadDisturbances
Load disturbances are disturbances that drive the process variables
away from their desired values. Attenuation of load disturbances is
of primary concern for process control. This is particularly the case

| 122 Chapter | 4   | Controller | Design |     |     |     |
| ----------- | --- | ---------- | ------ | --- | --- | --- |
for regulation problems where the processes are running in steady
state with constant setpoint for a long time. Load disturbances are
often of low frequencies. Step signals are often used asprototype dis-
turbances. The disturbances may enter the system in many different
ways. If nothing else is known, it is often assumed that the distur-
bances enter at the process input. Typical responses due to a unit
step disturbance at the process input are shown in Figure 4.1. The
characteristics of the graphs in Figure 4.1 are often used to specify
theresponse toload disturbances. Let ebetheerror caused byaunit
stepdisturbanceattheprocessinput.Typicalquantitiesusedtochar-
acterize the error are: maximum error e , time to reach maximum
max
t max ,settling time t s ,decayratio d,andtheintegrated absolute error,
| which is defined |     | by  |     | (cid:1) |     |     |
| ---------------- | --- | --- | --- | ------- | --- | --- |
∞
|     |     |     | IAE= | (cid:2)e(t)(cid:2)dt |     | (4.1) |
| --- | --- | --- | ---- | -------------------- | --- | ----- |
0
The criterion IAE is in many cases a natural choice, at least for
control of quality variables. A severe drawback is that its evaluation
requires significant computations or a simulation of the process. The
simulation must also be made with sufficient accuracy. Since the cri-
terion is based on an infinite integral it is also necessary to simulate
| for a long time. |     |     |     |     |     |     |
| ---------------- | --- | --- | --- | --- | --- | --- |
For processes that are nonoscillatory, IAE is the same as the
| integrated | error |     |     |     |     |     |
| ---------- | ----- | --- | --- | --- | --- | --- |
(cid:1)
∞
|     |     |     | IE= | e(t)dt |     | (4.2) |
| --- | --- | --- | --- | ------ | --- | ----- |
0
The quantity IE is a good approximation of IAE for systems that are
oscillatory but well damped. The reason for using IE is that its value
is directly related to the controller parameters. To see this assume
| that the control | law | is  |     |     |     |     |
| ---------------- | --- | --- | --- | --- | --- | --- |
(cid:1)
t
|     |     | u(t)= | ke(t)+k | e(t)dt−k | dy   |     |
| --- | --- | ----- | ------- | -------- | ---- | --- |
|     |     |       |         | i        | d dt |     |
0
and that this controller gives a stable closed-loop system. Further-
more assume that the error is initially zero and that a unit step
disturbance is applied atthe process input. Since the closed-loop sys-
tem is stable andhas integral action the control error will goto zero.
| We thus find |     |     |     | (cid:1) |     |     |
| ------------ | --- | --- | --- | ------- | --- | --- |
∞
|     |     | u(∞)−u(0)= |     |     | e(t)dt |     |
| --- | --- | ---------- | --- | --- | ------ | --- |
k
i
0
Since the disturbance is applied at the process input, the change in
control signal is equal to the change of the disturbance. Hence,
(cid:1)
∞
1 T
|     |     | IE= | e(t)dt= |     | = i   | (4.3) |
| --- | --- | --- | ------- | --- | ----- | ----- |
|     |     |     | 0       |     | k i K |       |

|     |     |     | 4.2 Specifications | 123 |
| --- | --- | --- | ------------------ | --- |
e
e
| e      |     |     |        d    e |      0 |
| ------ | --- | --- | ------------- | ------ |
|    max |     |     | max           |        |
±pe
     0
t
    max
  s t
e
e
0
| e        |     |     |    d    e |     |
| -------- | --- | --- | --------- | --- |
|      max |     |     | max       |     |
±pe
     0
    max t
  s t
Figure 4.1 The error due to a unit step load disturbance at the
process input and some features used to characterize attenuation
of load disturbances. The curves show the open-loop error and the
error obtained using a controller without integral action (upper)
(lower).
| and with      | integralaction      |              |        |     |
| ------------- | ------------------- | ------------ | ------ | --- |
| Integral gain | k is thus inversely | proportional | to IE. |     |
i
ThecriterionIEisanaturalchoiceforcontrolofqualityvariables
foraprocesswheretheproductissenttoamixingtank.Thecriterion
may be strongly misleading, however, in other situations. It will be
zero for an oscillatory system with no damping. It will also be zero
| for a controller | with a double | integrator. |     |     |
| ---------------- | ------------- | ----------- | --- | --- |

| 124 Chapter   | 4 ControllerDesign |     |     |     |
| ------------- | ------------------ | --- | --- | --- |
| The quadratic | criterion          |     |     |     |
(cid:1)
∞
|     |     | ISE= | e2(t)dt | (4.4) |
| --- | --- | ---- | ------- | ----- |
0
is also easy to compute. It has, however, the disadvantage that it
gives a very high weight tolargeerrors, whichoften leads toa poorly
| damped closed | loop.            |     |     |     |
| ------------- | ---------------- | --- | --- | --- |
| Sensitivityto | MeasurementNoise |     |     |     |
Measurement noiseistypically ofhighfrequency.Careshouldalways
betakentoreducenoisebyappropriatefiltering.Forsampledsystems
it is also important to choose the sampling rate properly. Measure-
ment noise will be fed into the system through the feedback. It will
generate control actions andcontrol errors.Thetransmission of mea-
surement noise to control actions can be described by the transfer
function
G
|     |     | G = | c           | (4.5) |
| --- | --- | --- | ----------- | ----- |
|     |     | nu  | 1+G(cid:10) |       |
whereG istheprocesstransferfunction, G isthecontrollertransfer
| p   |     |     | c   |     |
| --- | --- | --- | --- | --- |
function, and G(cid:10) = G G is the loop transfer function. The transfer
|               |             | p c   |                      |     |
| ------------- | ----------- | ----- | -------------------- | --- |
| function from | measurement | noise | to process output is |     |
1
|     |     | =    | =   | (4.6) |
| --- | --- | ---- | --- | ----- |
|     |     | G ny | S   |       |
1+G(cid:10)
where S is called the sensitivity function. Since the magnitude of
G(cid:10) normally is small for high frequencies, we have approximately
| G = G | for high frequencies. |     |     |     |
| ----- | --------------------- | --- | --- | --- |
nu c
| The high-frequency |     | gain of a | PID controller is |       |
| ------------------ | --- | --------- | ----------------- | ----- |
|                    |     | K =       | K(1+ N)           | (4.7) |
hf
Notice that N = 0 corresponds to PI control. Multiplication of the
measurementnoiseby K hf givesthefluctuations inthecontrolsignal
that are caused by the measurement noise. Also notice that there
may be a significant difference in K for PI and PID control. It is
hf
typically an order of magnitude larger for a PID controller, since the
gain normally is higher for a PID controller than for a PI controller,
| and N is typically | around                 | 10. |     |     |
| ------------------ | ---------------------- | --- | --- | --- |
| Sensitivityto      | ProcessCharacteristics |     |     |     |
The controller parameters are typically matched to the process char-
acteristics. Since the process may change it is important that the

|     |     |     |     | 4.2 Specifications | 125 |
| --- | --- | --- | --- | ------------------ | --- |
controller parameters are chosen in such a way that the closed-loop
system is not too sensitive to variations in process dynamics. There
are many ways to specify the sensitivity. Many different criteria are
convenientlyexpressedintermsoftheNyquistcurveofthelooptrans-
|              | (s) =     | (s)G (s) (see |        | 4.2).     |          |
| ------------ | --------- | ------------- | ------ | --------- | -------- |
| fer function | G(cid:10) | G             | Figure | We choose | to char- |
c p
| acterize | sensitivity | by         |      |                               |       |
| -------- | ----------- | ---------- | ---- | ----------------------------- | ----- |
|          |             | (cid:11) 1 |      | (cid:11)                      |       |
|          | =           | (cid:11)   |      | (cid:11)= (cid:2)S(iω)(cid:2) | (4.8) |
|          | M max       |            |      | max                           |       |
|          | s 0≤ω<∞     | 1+G (iω)G  | (iω) | 0≤ω<∞                         |       |
|          |             | p          | c    |                               |       |
Notice that the transfer function S, which is called the sensitivity
function, also appeared in the expression for the sensitivity to mea-
surement noise (compare with Equation (4.6)). The quantity M is
s
simply the inverse of the shortest distance from the Nyquist curve to
−1.
the critical point Reasonable values of M are in the range from
s
1.3 to 2.
Sensitivity function S has many useful physical interpretations.
One is the following. Assume that there is a sinusoidal disturbance
with frequencyωthat enters the system in an arbitrary way. Let the
amplitude of the open-loop system be a . If the system is controlled
0
with a controller that gives the sensitivity function S, the amplitude
(cid:2)S(iω)(cid:2).
of the controlled system is then a 0 Feedback thus reduces the
|     |     |     |     | ImG (iω) |     |
| --- | --- | --- | --- | -------- | --- |
l
1
A
     m
−1
ϕ
|     |     |   m |     |     | (iω) |
| --- | --- | --- | --- | --- | ---- |
   R    eG
|     | 1   |     |     |     | l   |
| --- | --- | --- | --- | --- | --- |
M
     s
Figure 4.2 Definitions of sensitivity M, amplitude margin A ,
|                 |     |                |                           | s   | m   |
| --------------- | --- | -------------- | ------------------------- | --- | --- |
| andphasemarginϕ |     | .AsensitivityM | guaranteesthatthedistance |     |     |
|                 |     | m              | s                         |     |     |
fromthe criticalpoint tothe Nyquist curve isalways greaterthan
1/M.
s

| 126 Chapter | 4 Controller | Design |     |     |     |     |
| ----------- | ------------ | ------ | --- | --- | --- | --- |
effectof thedisturbance if (cid:2)S(iω)(cid:2)<1,and itamplifies a disturbance
(cid:2)S(iω)(cid:2)>1.
if
Underverygeneralassumptionsitcanbeshownthatthesensitiv-
ity can not be smaller than one for all frequencies. With a controller
havingintegralactionwehave(cid:2)S(0)(cid:2)=0.Lowfrequencydisturbances
thus can be reduced effectively with such a controller. When design-
ing a controller it is important to be aware of the frequencies where
disturbances areamplified.Itisalsoimportant thatthelargestvalue
of the sensitivity is limited. It is common to require that the maxi-
mum value of the sensitivity function, M be in the range of 1.3 to
s
2.
|                 |           | (A )        |         | (ϕ  | )           |      |
| --------------- | --------- | ----------- | ------- | --- | ----------- | ---- |
| Amplitude       | margin    | m and phase | margin  |     | m are other | com- |
| mon sensitivity | measures. | They are    | defined | as  |             |      |
1
=
|     |     | A m (cid:2)G(cid:10) (iω | )(cid:2) |     |     |     |
| --- | --- | ------------------------ | -------- | --- | --- | --- |
(4.9)
u
|                            |     | ϕ =π+argG(cid:10) | (iω | )       |     |       |
| -------------------------- | --- | ----------------- | --- | ------- | --- | ----- |
|                            |     | m                 |     | (cid:3) |     |       |
| wheretheultimatefrequencyω |     |                   |     |         |     | (iω)= |
u isthefrequencywhereargG(cid:10)
−π and the gain cross-over frequency ω is the frequency where
(cid:3)
| (cid:2)G(cid:10) (iω)(cid:2) | =             |               |           |        |         |        |
| ---------------------------- | ------------- | ------------- | --------- | ------ | ------- | ------ |
|                              | 1. See Figure | 4.2. The      | amplitude | margin | is also | called |
| gain margin.                 | We have       | the following | relations |        |         |        |
M
|     |     | A > s |     |     |     |     |
| --- | --- | ----- | --- | --- | --- | --- |
m −1
M
|     |     | s   |     |     |     | (4.10) |
| --- | --- | --- | --- | --- | --- | ------ |
1
ϕ >2arcsin
m
2M
s
|     |     | ○   | ○   |     |     |     |
| --- | --- | --- | --- | --- | --- | --- |
Typical values ofϕ range from 30 to 60 .Amplitude margins could
m
typicallyvaryfrom2to5.Ageometricalinterpretationofthecriterion
(4.8)
given by Equation is that the Nyquist curve of the loop transfer
function is always outside a circle around the critical point −1 with
1/M
the radius s . An engineering interpretation is that the system
|               |                           |     |     |             |     | /(M −1) |
| ------------- | ------------------------- | --- | --- | ----------- | --- | ------- |
| remainsstable | even ifthegainisincreased |     |     | bythefactor | M   |         |
|               |                           |     |     |             |     | s s     |
or decreased by the vector M /(M +1). The closed loop will remain
s s
| stable even | if a nonlinearity | characterized |     | by      |     |     |
| ----------- | ----------------- | ------------- | --- | ------- | --- | --- |
|             | xM /(M            | +1)< f(x)<    | xM  | /(M −1) |     |     |
|             | s                 | s             |     | s s     |     |     |
isinserted intheloop. Asmallvalue of M s thusensures thatthesys-
tem will remain stable in spite of nonlinear actuator characteristics.
SetpointFollowing
Specifications onsetpoint following mayinclude requirements onrise
time, settling time, decay ratio, overshoot, and steady-state offset for
stepchangesinsetpoint. SeeFigure4.3.Thesequantities aredefined
| in different | ways and there | are also | different | standards. |     |     |
| ------------ | -------------- | -------- | --------- | ---------- | --- | --- |

|     |     | 4.2 | Specifications | 127 |
| --- | --- | --- | -------------- | --- |
y
y sp
|     | o   | d   | ⋅o e ss |     |
| --- | --- | --- | ------- | --- |
y
0
| 0.9 | y   |     | ±p% |     |
| --- | --- | --- | --- | --- |
0
0.1y
0
t
r
t
s
u
| Figure 4.3 | Specificationsonsetpointfollowingbasedonthetime |           |     |     |
| ---------- | ----------------------------------------------- | --------- | --- | --- |
| response   | toa unit step inthe                             | setpoint. |     |     |
•
| Therisetimet | iseitherdefinedastheinverseofthelargestslope |     |     |     |
| ------------ | -------------------------------------------- | --- | --- | --- |
r
ofthestepresponseorthetimeittakesthesteptopassfrom10%
| to 90% of | its steady state | value. |     |     |
| --------- | ---------------- | ------ | --- | --- |
•
The settling time t s is the time it takes before the step response
p=2%
| remains  | within p% of | its steady state value. | The value | is  |
| -------- | ------------ | ----------------------- | --------- | --- |
| commonly | used.        |                         |           |     |
• The decay ratio d is the ratio between two consecutive maxima
of the error for a step change in setpoint or load. The value
| d = 1/4, | which is called | quarter amplitude | damping, | has been |
| -------- | --------------- | ----------------- | -------- | -------- |
used traditionally. This value is, however, too high as will be
shown later.
• The overshoot o is the ratio between the difference between the
firstpeakandthesteadystatevalueandthesteadystatevalueof
the step response. Inindustrial control applications it is common
to specify anovershoot of 8%–10%. In many situations it is desir-
able,however,tohaveanoverdampedresponsewithnoovershoot.
• The steady-state error e is the value of control error ein steady
ss
state.Withintegralactioninthecontroller,thesteady-stateerror
| is always | zero. |     |     |     |
| --------- | ----- | --- | --- | --- |

128 Chapter 4 Controller Design
Criteria like IAE, IE, and ISE can also be used to characterize
setpoint responses if the error inEquations (4.1), (4.2),and(4.4)are
interpreted astheerror duetoaunit stepchange ofthesetpoint. For
step changes in the setpoint there will always be a largeinitial error.
It is then useful to have criteria that put little weight on the initial
error. It has been found that criteria of the type
(cid:1)
∞
ITAE= t(cid:2)e(t)(cid:2)dt
(cid:1)0
∞
ITE= te(t)dt
(cid:1)0
∞
ITSE= te2(t)dt
(cid:1)0
∞
ISTE= t2e2(t)dt
0
are more suitable to judge performance for setpoint following. These
integrals are finite only if the steady-state error is zero. In some
casessetpointfollowingmayalsocontainrequirementsbasedonramp
signals.
For a system with pure error feedback the relation between pro-
cess output and setpoint is given by
Y(s)=
G
p
(s)G
c
(s)
Y =
G(cid:10) (s)
Y (4.11)
1+G
p
(s)G
c
(s) sp 1+G(cid:10) (s) sp
Thesetpoint response is thus uniquely given by G(cid:10).For systems with
two degrees of freedom the corresponding relation is
G (s)G (s) G (s)G (s)
Y(s)= p ff Y = p ff Y (4.12)
1+G
p
(s)G
c
(s) sp 1+G(cid:10) (s) sp
where G (s) is the transfer function between the setpoint and the
ff
controller output. (Compare withSection 3.4.)Setpoint following and
load disturbance rejection can be decoupled by using a two-degree-
of-freedom structure. For PID controllers it is mostly the setpoint
weighting that is used to modify the setpoint response.
Tojudgetheproperties ofacontrolsystem wemustconsider both
theprocess output andthecontrol signal. Theresponse of thecontrol
signal to a step change in the setpoint typically has an overshoot as
is shown in Figure 4.3. The initial change of the control signal is
∆u(0) = Kb∆y , where K is the controller gain, b is the setpoint
sp
weighting, and ∆y is the setpoint change. The steady-state change
sp
ofthecontrolsignal is ∆u =∆y /K ,where K isthestatic process
ss sp p p
gain. The quantity
∆u(0)
M = = KK b
u ∆u p
ss

|     |     |     |     |     | 4.2 Specifications | 129 |
| --- | --- | --- | --- | --- | ------------------ | --- |
is thus a normalized initial overshoot of the control signal. This ex-
pressionisacorrectvalueoftheovershoot ifthecontrolsignalhasits
largest value immediately after the change in the setpoint. For sys-
tems with time delays the maximum will occur later. The overshoot
| can | then be | approximated | by  | the expression |         |     |
| --- | ------- | ------------ | --- | -------------- | ------- | --- |
|     |         |              |     | (cid:2)        | (cid:3) |     |
L
|     |     |     | M = | KK b+ |     |     |
| --- | --- | --- | --- | ----- | --- | --- |
u p
T
i
where L is the apparent dead time and T i is the integration time of
the controller.
The dimensionless quantity M , which we call the control signal
u
overshoot, is a quantity that is useful for evaluating the performance
of a control system. For systems where an essential part of the dy-
namics is due to the sensors it is important that M u is not too large.
RelationsBetweenSpecifications
Specifications express different properties of a system such as load
disturbance attenuation and setpoint following. They are also ex-
pressed in different ways using frequency domain or time domain
properties. To get some insight into the relations we will investigate
| a second-order |               | system | in detail. |          |                   |     |
| -------------- | ------------- | ------ | ---------- | -------- | ----------------- | --- |
| Second-Order   |               | System |            |          |                   |     |
| Consider       | a first-order |        | system     | with the | transfer function |     |
K
|     |     |     | G (s)= | p    |     |     |
| --- | --- | --- | ------ | ---- | --- | --- |
|     |     |     | p      | 1+sT |     |     |
that is controlled by an I controller. For such a system the transfer
| function | from | setpoint | to process | output | is  |     |
| -------- | ---- | -------- | ---------- | ------ | --- | --- |
ω2
G p G c
|     |          | G(s)=     |         | =            | 0   | (4.13) |
| --- | -------- | --------- | ------- | ------------ | --- | ------ |
|     |          |           | 1+G     | G s2+2ζωs+ω2 |     |        |
|     |          |           |         | p c          | 0 0 |        |
| The | response | to a unit | step in | the setpoint | is  |        |
(cid:2) (cid:7) (cid:3)
1
|     | y(t)=1− | (cid:7) | −ζω | 0tsin ω | 1−ζ2+φ | (4.14) |
| --- | ------- | ------- | --- | ------- | ------ | ------ |
|     |         |         | e   |         | t      |        |
|     |         | 1−ζ2    |     |         | 0      |        |
(cid:7)
| whereφ=arctan |     | 1−ζ2/ζ. |     |     |     |     |
| ------------- | --- | ------- | --- | --- | --- | --- |
Thetransferfunctionfromaloaddisturbanceattheprocessinput
| to process | output | is given | by  |       |     |        |
| ---------- | ------ | -------- | --- | ----- | --- | ------ |
|            |        | (s)=     | G p | = K p | s   | (4.15) |
G
|     |     | ly  | 1+G G | T s2+2ζωs+ω2 |     |     |
| --- | --- | --- | ----- | ------------ | --- | --- |
|     |     |     | p     | c            | 0 0 |     |

| 130 | Chapter 4 | Controller | Design |     |     |     |     |     |
| --- | --------- | ---------- | ------ | --- | --- | --- | --- | --- |
A unit step load disturbance at the process input gives the error
(cid:7)
K
|     | e(t)= |     | (cid:7) p | e   | −ζω 0tsinω | t 1−ζ2 |     | (4.16) |
| --- | ----- | --- | --------- | --- | ---------- | ------ | --- | ------ |
0
ωT 1 −ζ2
0
0<ζ<1,
| If  | the | two closed-loop |     | poles | of  | the system | are |     |
| --- | --- | --------------- | --- | ----- | --- | ---------- | --- | --- |
(cid:7)
|     |     | p   | =−ζω | ±iω | 1−ζ2 |     |     |     |
| --- | --- | --- | ---- | --- | ---- | --- | --- | --- |
|     |     |     | i    | 0   | 0    |     |     |     |
where ζ is called the relative damping, and ω is the undamped
0
naturalfrequency.Thetimeresponsesofthesystemarecharacterized
| by a damped | oscillation |     | with | period |     |     |     |     |
| ----------- | ----------- | --- | ---- | ------ | --- | --- | --- | --- |
2π
|     |     |     | T   | = (cid:7) |     |     |     | (4.17) |
| --- | --- | --- | --- | --------- | --- | --- | --- | ------ |
p
|     |     |     |     | ω   | 1−ζ2 |     |     |     |
| --- | --- | --- | --- | --- | ---- | --- | --- | --- |
0
| and decay | ratio |     |     |       | √    |     |     |        |
| --------- | ----- | --- | --- | ----- | ---- | --- | --- | ------ |
|           |       |     | d=  | −2πζ/ | 1−ζ2 |     |     | (4.18) |
e
From the step response (Equation 4.14) we cancalculate the rise
time, the settling time, and the overshoot. Defining the rise time as
| the inverse | of the | maximum |     | slope | of the | step response | we  | get    |
| ----------- | ------ | ------- | --- | ----- | ------ | ------------- | --- | ------ |
|             |        |         |     | 1     | φ/tanφ |               |     |        |
|             |        |         | t   | =     | e      |               |     | (4.19) |
|             |        |         | r   | ω     |        |               |     |        |
0
The settling time, i.e., the time required for the output to be within
the fraction p of the steady state value, is a discontinuous function
of the parameters due to the oscillatory nature of the step response.
An approximative formula is obtained by considering the envelope of
| the step | response. | This | gives      |         |         |         |     |        |
| -------- | --------- | ---- | ---------- | ------- | ------- | ------- | --- | ------ |
|          |           |      |            | (cid:2) | (cid:7) | (cid:3) |     |        |
|          |           |      |            | log     | p 1−ζ2  |         |     |        |
|          |           |      | t (cid:9)− |         |         |         |     | (4.20) |
|          |           |      | s          |         | ζω      |         |     |        |
0
This formula is conservative because it overestimates the settling
| time. The | slope | has its | maximum |     | at  |     |     |     |
| --------- | ----- | ------- | ------- | --- | --- | --- | --- | --- |
φ
t=
ω cosφ
0
| Withζ=0.707 |          | p=0.02 |     |       | =2.2/ω |     | =6.0/ω. |     |
| ----------- | -------- | ------ | --- | ----- | ------ | --- | ------- | --- |
|             | and      |        |     | weget | t      | and | t       | The |
|             |          |        |     |       | r      | 0   | s       | 0   |
| overshoot   | is given | by     |     |       |        |     |         |     |
√
√
|         |              |        |      | −πζ/   | 1−ζ2   |      |     |     |
| ------- | ------------ | ------ | ---- | ------ | ------ | ---- | --- | --- |
|         |              |        | o= e |        | =      | d    |     |     |
| where d | is the decay | ratio. | It   | occurs | at the | time |     |     |
π
= (cid:7)
t max
|     |     |     |     | ω   | 1−ζ2 |     |     |     |
| --- | --- | --- | --- | --- | ---- | --- | --- | --- |
0

|               |             |       |           |     |       | 4.2     | Specifications | 131    |
| ------------- | ----------- | ----- | --------- | --- | ----- | ------- | -------------- | ------ |
|               |             |       | ζ=0.707,  |     |       | ζ=0.63, |                | ζ=0.5. |
| The overshoot |             | is 4% | for       |     | 8%    | for     | 16%            | for    |
| It is 50%     | for quarter |       | amplitude |     | decay | ratio.  |                |        |
Equation (4.16) gives the error signal after a step disturbance at
| the process | input. | This | signal | has | the | maximum |     |     |
| ----------- | ------ | ---- | ------ | --- | --- | ------- | --- | --- |
K
|     |     | e   | =   | (cid:7)p |     | e −φtanφ sinφ |     |     |
| --- | --- | --- | --- | -------- | --- | ------------- | --- | --- |
max
|     |     |     | ωT  |     | 1−ζ2 |     |     |     |
| --- | --- | --- | --- | --- | ---- | --- | --- | --- |
0
for
1
|     |     |     |     | =   | (cid:7) | φ   |     |     |
| --- | --- | --- | --- | --- | ------- | --- | --- | --- |
t max
|     |     |     |     |     | ω 1−ζ2 |     |     |     |
| --- | --- | --- | --- | --- | ------ | --- | --- | --- |
0
| The integrated |     | error | is  |     |     |     |     |     |
| -------------- | --- | ----- | --- | --- | --- | --- | --- | --- |
K
|     |     |     |     | IE= | p   |     |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
ω2T
0
ThisquantityisclosetotheIAE,iftheovershoot issufficientlysmall.
| The | high-frequency |     | gain | of   | the controller | is        |     |     |
| --- | -------------- | --- | ---- | ---- | -------------- | --------- | --- | --- |
|     |                |     |      | 2ζωT | −1             | 2ζωT      |     |     |
|     |                |     | =    |      | 0              | (cid:9) 0 |     |     |
|     |                |     | K hf |      |                |           |     |     |
|     |                |     |      |      | K              | K         |     |     |
|     |                |     |      |      | p              | p         |     |     |
where the approximation holds whenωT is large. The sensitivity is
0
|     |     |     | (cid:10)      |     |     | (cid:7) |     |     |
| --- | --- | --- | ------------- | --- | --- | ------- | --- | --- |
|     |     |     | 1+8ζ2+(1+4ζ2) |     |     | 1+8ζ2   |     |     |
|     |     | =   |               |     |     | (cid:7) |     |     |
M
|     |     | s   | 1+8ζ2+(−1+4ζ2) |     |     | 1+8ζ2 |     |     |
| --- | --- | --- | -------------- | --- | --- | ----- | --- | --- |
The sensitivity function is infinite for ζ = 0 and decreases with
|     | ζ.  |     |     | ζ   | =   |     |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
increasing Its values for 0.3, 0.5, and 0.7 are 2.0, 1.5, and
1.3. To have a reasonable value of the sensitivity it must, therefore,
berequiredthattherelativedampingisgreaterthan0.3.Thisimplies
| that the | decay | ratio | d must | be  | smaller | than 0.14. |     |     |
| -------- | ----- | ----- | ------ | --- | ------- | ---------- | --- | --- |
The equations given can be used to understand how the proper-
ties of the closed-loop system are influenced by ω and ζ. The in-
0
toω−2.
| tegrated | error | is inversely |     | proportional |     | The | maximum | error, |
| -------- | ----- | ------------ | --- | ------------ | --- | --- | ------- | ------ |
0
therisetime,andthesettling timeareproportional toω−1.Thehigh-
0
ω.
frequency gain of the controller is proportional to 0 Both the load
disturbance response and the setpoint response are improved by in-
creasingω.The control actions generated bynoise do increase, how-
0
withω.
ever, The overshoot, the decay ratio, and the sensitivity will
0
| increase | with | decreasing |     | ζ.  |     |     |     |     |
| -------- | ---- | ---------- | --- | --- | --- | --- | --- | --- |
This general pattern also holds for more complex systems. Both
load disturbance attenuation and response time to setpoint changes
will generally increase with increasing bandwidth of the system. For
more complex controllers, the load disturbance response and the set-
| point response |     | can be | specified |     | separately. |     |     |     |
| -------------- | --- | ------ | --------- | --- | ----------- | --- | --- | --- |

132 Chapter 4 Controller Design
AveragingControl
There are several situations where the purpose of control is not to
keep the process variables at constant values. Level control in buffer
tanks is a typical example. The reason for using a buffer tank is to
smoothflowvariations. Insuchacasethetanklevel should fluctuate
within some limits. It is often undesirable that the tank becomes
empty or that it overflows. The specifications are thus that the tank
level should be allowed to fluctuate between given limits. This is
called averaging control. It is often solved with a controller with a
small gain. Sometimes gain scheduling is introduced tohave a larger
gain when the level gets close to the limits. Another approach is to
use error-squared control. This was discussed in Section 3.4.
DominantPoles
The formulas derived above for a second-order system can often be
usedasapproximations formorecomplexsystems.Thereasonforthis
isthatthedynamicsofcomplexsystemscanoftenbecharacterizedby
afewpoles.Manypropertiesoftheclosed-loop systemcanbededuced
from the poles and the zeros of
G(s)=
G(cid:10) (s)
(4.21)
1+G(cid:10) (s)
The closed-loop zeros are the same as the zeros of loop transfer func-
tion G ll(s), and the closed-loop poles are the roots of the equation
e
1+G(cid:10) (s)=0 (4.22)
The pole-zero configurations of closed-loop systems may vary consid-
erably.Manysimplefeedbackloops,however,willhaveaconfiguration
of the type shown in Figure 4.4, where the principal characteristics
I ms
p
1
p
4
p p 3 z 1 R es
5
p
2
Figure 4.4 Pole-zero configuration of asimple feedback system.

4.2 Specifications 133
of the response aregiven by acomplex pair of poles, p and p ,called
1 2
thedominant poles.Theresponse isalsoinfluenced byrealpoles and
zeros p and z close to the origin. The position of p and z may be
3 1 3 1
reversed. Theremayalso bemorepoles andzerosfarfromtheorigin,
which typically are of less influence. Poles and zeros with real parts
much smaller than the real part of the dominant poles have little
influence on the transient response.
Complexpolesareoftencharacterizedintermsoftheir frequency
ω, which is the distance from the origin, and their relative damping
0
ζ.Ifapairofcomplexpolesisdominating,theformulasderivedabove
for a second-order system can be used as approximation. Classical
control was very much concerned with closed-loop systems having
the pole-zero configuration shown in Figure 4.4.
Even if many closed-loop systems have a pole-zero configuration
similartotheoneshowninFigure4.4,thereare,however,exceptions.
For instance, systems with mechanical resonances, which may have
poles and zeros close to the imaginary axis, are generic examples of
systems that do not fit the pole-zero pattern of the figure. Another
example is processes with a long dead time.
Determinationofthe DominantPolesfrom the
FrequencyResponse
Asimplemethodforapproximatedeterminationofthedominantpoles
fromknowledgeoftheNyquistcurveofthelooptransfer function will
now begiven. Consider theloop transfer function G(cid:10) (s)asa mapping
from the s-plane to the G(cid:10)-plane. The map of the imaginary axis in
the s-plane is the Nyquist curve G(cid:10) (iω), which is indicated in Figure
4.5.
The closed-loop poles are the roots of the characteristic equation
1+G(cid:10) (s)=0
The map of a straight vertical line through the dominant closed-loop
polesinthes-planeisthusacurvethroughthecriticalpoint G(cid:10) =−1
in the G(cid:10)-plane. This curve is shown by a dashed line in Figure
(cid:8) (cid:8)
4.5. Since the map is conform, the straight line AC is mapped on
the curve AC, which intersects the Nyquist curve orthogonally. The
(cid:8) (cid:8) (cid:8)
triangle ABC is also mapped conformally to ABC. If ABC can be
approximated by a triangle, we have
G(cid:10) (iω
2
)−G(cid:10) (iω
1
)
(cid:9)
1+G(cid:10) (iω
2
)
iω −iω σ
2 1
Whenω is close toω this becomes
1 2
σ=(1+G(cid:10) (iω
2
))
G(cid:10) (iω
iω
2
2
)−
−i
G
ω
(cid:10)
1
(iω 1 )
(cid:9) 1+
G (cid:10) (cid:8)
G
(i
(cid:10)
ω
(i
2
ω
)
2 )

| 134 | Chapter | 4 Controller |     | Design |     |     |     |
| --- | ------- | ------------ | --- | ------ | --- | --- | --- |
where
dG(cid:10) (s)
(cid:8)(s)=
G (cid:10)
ds
TodeterminethedominantpoleswefirstdeterminethepointAonthe
Nyquistcurvethatisclosesttotheultimatepoint.Thenwedetermine
the derivative of the loop transfer function at that point or evaluate
| the | transfer | function | at a neighboring |     | point | ω.  |     |
| --- | -------- | -------- | ---------------- | --- | ----- | --- | --- |
1
DesignParametersandDesignMethods
In control designs it is often convenient to have a few parameters
that can be changed to influence the performance of the system. The
parametersshouldbechoseninsuchawaythattheirinfluenceonthe
performance of the system is transparent. In the case of the second-
ω
order example discussed above, the parameters can be chosen as 0
andζ.
|     | The | relative | damping | can be | replaced | by the sensitivity | M . |
| --- | --- | -------- | ------- | ------ | -------- | ------------------ | --- |
s
A good design method should take a number of different specifi-
cations into account in a balanced way. Most design methods, unfor-
tunately, concentrate on one or a few of the specifications only.
| 4.3 | Ziegler-Nichols’ |     |     | and | Related | Methods |     |
| --- | ---------------- | --- | --- | --- | ------- | ------- | --- |
Two classical methods for determining the parameters of PID con-
trollers were presented by Ziegler and Nichols in 1942. These meth-
ods are still widely used, either in their original form or in some
modification. They often form the basis for tuning procedures used
by controller manufacturers and process industry. The methods are
based on determination of some features of process dynamics. The
|     |     | Ims |     |     |     |     | ImG |
| --- | --- | --- | --- | --- | --- | --- | --- |
l
A'=iω
2
| C'  |     |     |     |     | C= −1 |     |     |
| --- | --- | --- | --- | --- | ----- | --- | --- |
α
ReG
|     |     | B'=iω |     |     |     | α         | l   |
| --- | --- | ----- | --- | --- | --- | --------- | --- |
|     |     |       | 1   |     |     | A=G (iω ) |     |
|     |     |       |     |     |     | l 2       |     |
|     |     |       | ω   |     |     | B=G (iω)  |     |
|     |     |       |     |     |     | l 1       |     |
G (iω)
l
Res
σ
|     | Figure     | 4.5 Representationofthelooptransferfunctionasamap |     |     |     |     |     |
| --- | ---------- | ------------------------------------------------- | --- | --- | --- | --- | --- |
|     | of complex | planes.                                           |     |     |     |     |     |

4.3 Ziegler-Nichols’and RelatedMethods 135
y
a
L
Figure 4.6 Characterization of a step response in the Ziegler-
Nichols step response method.
controller parameters are then expressed in terms of the features by
simple formulas.
TheStepResponseMethod
The first design method presented by Ziegler and Nichols is based
on a registration of the open-loop step response of the system, which
is characterized by two parameters. The parameters are determined
from a unit step response of the process, as shown in Figure 4.6.
The point where the slope of the step response has its maximum
is first determined, and the tangent at this point is drawn. The
intersections between the tangent and the coordinate axes give the
parameters a and L. In Chapter 2, a model of the process to be
controlled was derived from these parameters. This corresponds to
modeling a process by an integrator and a time delay. Ziegler and
Nichols have given PID parameters directly as functions of a and L.
These are given in Table 4.1. An estimate of the period T of the
p
closed-loop system is also given in the table.
EXAMPLE 4.1 Ziegler-Nichols step response method
Ziegler-Nichols method will be applied to a process with the transfer
function
1
G(s)= (4.23)
(s+1)3
Measurements on the step response give the parameters a = 0.218
and L = 0.806. The controller parameters can now be determined
from Table 4.1. The parameters of a PID controller are K = 5.50,

| 136 Chapter | 4 Controller | Design |     |     |     |     |
| ----------- | ------------ | ------ | --- | --- | --- | --- |
Table 4.1 PID controller parameters obtained from the Ziegler-
| Nichols | step response | method. |     |     |     |     |
| ------- | ------------- | ------- | --- | --- | --- | --- |
|         | Controller    | K       | T   | T   | T   |     |
|         |               |         | i   | d   | p   |     |
1/a
|              | P                                            |       |     |     | 4L   |     |
| ------------ | -------------------------------------------- | ----- | --- | --- | ---- | --- |
|              | PI                                           | 0.9/a | 3L  |     | 5.7L |     |
|              | PID                                          | 1.2/a | 2L  | L/2 | 3.4L |     |
| T =1.61,andT | =0.403.Figure4.7showstheresponseoftheclosed- |       |     |     |      |     |
| i            | d                                            |       |     |     |      |     |
loopsystems toastep changeinsetpoint followed byastepchangein
the load. The behaviour of the controller is as can be expected. The
decay ratio for the step response is close to one quarter. It is smaller
fortheloaddisturbance. Theovershoot inthesetpoint response istoo
large. This can be improved by reducing parameter b. Compare with
Section 3.4.
TheFrequencyResponseMethod
This method is also based on a simple characterization of the pro-
cess dynamics. The design is based on knowledge of the point on the
| Nyquistcurveoftheprocesstransferfunction |     |     |     | G(s)wheretheNyquist |     |     |
| ---------------------------------------- | --- | --- | --- | ------------------- | --- | --- |
curve intersects the negative real axis. For historical reasons this
point is characterized by the parameters K and T ,which arecalled
|     |     |     |     | u   | u   |     |
| --- | --- | --- | --- | --- | --- | --- |
the ultimate gain and the ultimate period. These parameters can be
y
1
y sp
0
| 0   | 10  |     | 20  |     | 30  | 40  |
| --- | --- | --- | --- | --- | --- | --- |
u
2
−2
| 0   | 10  |     | 20  |     | 30  | 40  |
| --- | --- | --- | --- | --- | --- | --- |
Figure 4.7 Setpoint and load disturbance response of a process
withtransferfunction1/(s+1)3controlledbyaPIDcontrollertuned
withtheZiegler-Nicholsstepresponsemethod.Thediagramsshow
| setpoint | y , process output | y, and | controlsignal |     | u.  |     |
| -------- | ------------------ | ------ | ------------- | --- | --- | --- |
sp

4.3 Ziegler-Nichols’and RelatedMethods 137
Table 4.2 PID controller parameters obtained from the Ziegler-
Nichols frequency response method.
Controller K T T T
i d p
P 0.5K T
u u
PI 0.4K 0.8T 1.4T
u u u
PID 0.6K 0.5T 0.125T 0.85T
u u u u
determined in the following way. Connect a controller to the process,
set the parameters so that control action is proportional, i.e., T =∞
i
and T =0. Increase the gain slowly until the process starts to oscil-
d
late.Thegainwhenthisoccursis K andtheperiodoftheoscillation
u
is T .Theparameters canalsobedetermined approximately byrelay
u
feedback as is discussed in Section 2.6.
Ziegler-Nichols have given simple formulas for the parameters of
the controller in terms of the ultimate gain and the ultimate period
(seeTable 4.2).An estimate of theperiod T ofthe dominant dynam-
p
ics of the closed-loop system is also given in the table.
We illustrate the design procedure with an example.
EXAMPLE 4.2 The Ziegler-Nichols frequency response method
Consider the same process as in Example 4.1. The process given by
Equation (4.23) √has the ultimate gain K
u
= 8 and the ultimate
period T = 2π/ 3 (cid:9) 3.63. Table 4.2 gives the parameters K = 4.8,
u
T = 1.81, and T = 0.44 for a PID controller. Figure 4.8 shows
i d
the closed-loop setpoint and load disturbance responses when the
controller is applied to the process given by Equation (4.23). The
parameters and the performance of the controllers obtained with the
frequency response method are close to those obtained by the step
response method. The responses are slightly better damped.
The Ziegler-Nichols tuning rules were originally designed to give
systemswithgoodresponsestoloaddisturbances.Theywereobtained
by extensive simulations of many different systems. The design cri-
terion was quarter amplitude decay ratio. Equation (4.18) gives a
relation between decay ratio dandrelative dampingζ.Usingthis re-
lation we find that d=1/4, gives ζ=0.22, which is often too small,
asisseenintheexamples.ForthisreasontheZiegler-Nichols method
often requires modification or retuning. Since the primary design ob-
jectivewastoreduceloaddisturbances, itisoftennecessarytochoose
setpoint weighting carefully in order to obtain a satisfactory setpoint
response.

| 138 Chapter |     | 4 Controller | Design |     |     |     |     |     |
| ----------- | --- | ------------ | ------ | --- | --- | --- | --- | --- |
y
1
y
sp
0
| 0   |     | 10  |     | 20  |     | 30  |     | 40  |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
u
2
−2
| 0   |     | 10  |     | 20  |     | 30  |     | 40  |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
Figure 4.8 Setpoint and load disturbance response of a process
with the transfer function 1/(s + 1)3 controlled by a PID con-
troller that is tuned with the Ziegler-Nichols frequency response
| method.Thediagramsshowsetpoint |     |     |     | y   | ,processoutput |     | y,andcon- |     |
| ------------------------------ | --- | --- | --- | --- | -------------- | --- | --------- | --- |
sp
| trolsignal          | u.  |     |                              |     |     |     |     |     |
| ------------------- | --- | --- | ---------------------------- | --- | --- | --- | --- | --- |
| RelationsBetweenthe |     |     | Ziegler-NicholsTuningMethods |     |     |     |     |     |
Insight into the relations between the Ziegler-Nichols methods can
be obtained by calculating the controller parameters for different
| systems. | Consider | a process | with | the transfer |     | function |     |     |
| -------- | -------- | --------- | ---- | ------------ | --- | -------- | --- | --- |
b
|     |     |     | G(s)= | e −sL |     |     |     |     |
| --- | --- | --- | ----- | ----- | --- | --- | --- | --- |
s
which is the model originally used by Ziegler and Nichols to derive
their tuning rules for the step response method. For this process we
have a= bL. The ultimate frequency is ω =π/2L, which gives the
u
| ultimate        | period | T =4L, | and | the ultimate       | gain | is            | K =π/2bL. |     |
| --------------- | ------ | ------ | --- | ------------------ | ---- | ------------- | --------- | --- |
|                 |        | u      |     |                    |      |               | u         |     |
| Thestepresponse |        | method |     | gives thefollowing |      | parametersfor |           | aPI |
controller
0.9
|     |     |     | =   | =3L   |     |     |     |     |
| --- | --- | --- | --- | ----- | --- | --- | --- | --- |
|     |     |     | K   | , T i |     |     |     |     |
bL
| This can | be compared | with | the    | parameters |     |     |     |     |
| -------- | ----------- | ---- | ------ | ---------- | --- | --- | --- | --- |
|          |             |      | = 0.63 | =3.2L      |     |     |     |     |
|          |             |      | K      | , T        |     |     |     |     |
|          |             |      | bL     | i          |     |     |     |     |
obtained for the frequency response method. Notice that the integral
times are within 10% but that the step response method gives a gain
| that is about | 40% | higher. |     |     |     |     |     |     |
| ------------- | --- | ------- | --- | --- | --- | --- | --- | --- |
The PID parameters obtained from the step response method are
|     |     | 1.2 |     |       |     | L   |     |     |
| --- | --- | --- | --- | ----- | --- | --- | --- | --- |
|     |     | =   |     | =2L   |     | =   |     |     |
|     |     | K   | , T | i and | T   | d   |     |     |
|     |     | bL  |     |       |     | 2   |     |     |

|     |     | 4.3 | Ziegler-Nichols’and | RelatedMethods |     | 139 |
| --- | --- | --- | ------------------- | -------------- | --- | --- |
  I  mG(iω)
 I
ReG(iω)
ω
 A
 P
 D
Figure 4.9 A given point on the Nyquist curve may be moved to
another position in the G-plane by PI, PD, or PID control. Point
|          |       |        | G(iω),     | −iG(iω), | iG(iω) |     |
| -------- | ----- | ------ | ---------- | -------- | ------ | --- |
| A may be | moved | in the | directions |          | and    | by  |
changing the proportional, integral, and derivative gain, respec-
tively.
| and those given | by  | the frequency | response    | methods | are, |     |
| --------------- | --- | ------------- | ----------- | ------- | ---- | --- |
|                 |     | 0.94          |             |         | L    |     |
|                 | K   | =             | , T =2L and | T       | =    |     |
|                 |     |               | i           | d       |      |     |
|                 |     | bL            |             |         | 2    |     |
In this particular case both methods give the same values of integral
andderivativetimesbutthestepresponsemethodgivesagainthatis
| about25%higher | thanthefrequencyresponse |     |     | method.Theresults |     | of  |
| -------------- | ------------------------ | --- | --- | ----------------- | --- | --- |
this example are quite typical. The step response method often gives
| higher values         | of the | gain. |                       |     |     |     |
| --------------------- | ------ | ----- | --------------------- | --- | --- | --- |
| AnInterpretationofthe |        |       | FrequencyDomainMethod |     |     |     |
The frequency domain method can be interpreted as a method where
| onepointoftheNyquistcurveispositioned. |     |     |     | WithPIorPIDcontrol,it |     |     |
| -------------------------------------- | --- | --- | --- | --------------------- | --- | --- |
ispossible tomoveagiven point ontheNyquist curvetoanarbitrary
position inthecomplexplane,asindicatedinFigure4.9.Bychanging
thegain, a point onthe Nyquist curve ismoved radially from theori-
gin. The point can be moved in the orthogonal direction by changing
integralorderivativegain.Noticethatwithpositivecontrollerparam-
| etersthepoint | canbemoved |     | toaquarterplanewithPIorPDcontrol |     |     |     |
| ------------- | ---------- | --- | -------------------------------- | --- | --- | --- |
andtoahalf plane with PIDcontrol. Thefrequency response method
starts with determination of the point (−1/K ,0) where the Nyquist
u
curve of the open-loop transfer function intersects the negative real
axis. Letusnow investigate how theultimate point ischangedbythe

140 Chapter 4 Controller Design
controller. For a PI controller with Ziegler-Nichols tuning we have
K =0.4K andω T =(2π/T )0.8T =5.02. Thererfore, the transfer
u u i u u
function of the PI controller at the ultimate frequency is
(cid:5) (cid:6)
1
G (iω )= K 1+ =0.4K (1−i/5.02)= K (0.4−0.08i)
c u iω T u u
u i
The ultimate point is thus moved to −0.4+0.08i. This means that a
○
lag of 11.2 is introduced at the ultimate frequency.
For a PID controller we have K = 0.6K , ω T =πand ω T =
u u i u d
π/4. The frequency response of the controller at frequencyω is
u
(cid:5) (cid:2) (cid:3)(cid:6) (cid:5) (cid:2) (cid:3)(cid:6)
1 π 1
G (iω )= K 1+i ω T − =0.6K 1+i −
c u u d ω T u 4 π
u i
(cid:9)0.6K (1+0.467i)
u
○
Thiscontrollergivesaphaseadvanceof25 attheultimatefrequency.
The loop transfer function is
G(cid:10) (iω
u
)= G
p
(iω
u
)G
c
(iω
u
)=−0.6(1+0.467i)=−0.6−0.28i
The Ziegler-Nichols frequency response method thus moves the ulti-
mate point (−1/K ,0) to the point −0.6−0.28i. The distance from
u
this point to the critical point is 0.5. This means that the method
gives a sensitivity that is always greater than 2.
ModifiedZiegler-NicholsMethod
With the given interpretation of the frequency domain method, it is
straightforward to generalize it in the following way. Choose an arbi-
trarypointontheNyquistcurveoftheopen-loopsystem.Determinea
controller that moves this point to a suitable location. Let the chosen
point be
A= G p (iω 0 )= r a ei(π+φ a )
Determine a controller that moves this point to
B = G(cid:10) (iω 0 )=r b ei(π+φ b )
Writing the frequency response of the controller as G c (iω 0 ) = r c eiφ c
we get
r b ei(π+φ b ) = r a r c ei(π+φ a +φ c )
The controller should thus be chosen so that
r
r = b
c
r
a
φ =φ −φ
c b a

|     |      |            | 4.3 Ziegler-Nichols’and |           |     | RelatedMethods | 141 |
| --- | ---- | ---------- | ----------------------- | --------- | --- | -------------- | --- |
| For | a PI | controller | this implies            |           |     |                |     |
|     |      |            |                         | cos(φ −φ) |     |                |     |
r
|     |     |     | K = b | b   | a   |     |        |
| --- | --- | --- | ----- | --- | --- | --- | ------ |
|     |     |     |       | r a |     |     | (4.24) |
1
=
|     |     |     | T i ω | tan(φ | −φ) |     |     |
| --- | --- | --- | ----- | ----- | --- | --- | --- |
|     |     |     | 0     | a     | b   |     |     |
This means that we must require φ > φ in order to have positive
a b
| T.  | For a | PID controller | we get | similarly |     |     |     |
| --- | ----- | -------------- | ------ | --------- | --- | --- | --- |
i
r cos(φ −φ)
|     |     |     | =   | b   | b   | a   |     |
| --- | --- | --- | --- | --- | --- | --- | --- |
K
r
|     |     |     |     |     | a   |     | (4.25) |
| --- | --- | --- | --- | --- | --- | --- | ------ |
1
|     |     |     | ωT −    | =tan(φ | −φ) |     |     |
| --- | --- | --- | ------- | ------ | --- | --- | --- |
|     |     |     | 0 d ω T |        | b   | a   |     |
|     |     |     | 0       | i      |     |     |     |
Thegain K isuniquely given. Thereis, however, only oneequation to
determine parameters T and T . An additional condition must thus
i d
be introduced to determine these parameters uniquely. A common
method is to specify that the ratio of these parameters is constant,
i.e.,
=αT
|     |     |     | T   | d i |     |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- |
as in the Ziegler-Nichols rules, where α = 0.25. Straightforward
| calculations |     | then give |     |     |     |         |     |
| ------------ | --- | --------- | --- | --- | --- | ------- | --- |
|              |     | (cid:5)   |     |     |     | (cid:6) |     |
(cid:25)
1
|     |     | =   | tan(φ −φ)+ | 4α+tan2(φ |     | −φ) |     |
| --- | --- | --- | ---------- | --------- | --- | --- | --- |
|     | T i | 2αω | b a        |           |     | b a |     |
(4.26)
0
=αT
T
|     | d   | i   |     |     |     |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- |
Assuming that a Ziegler-Nichols experiment is used to determine a
|            |     |             | = 1/K  |          | φ   | =         |            |
| ---------- | --- | ----------- | ------ | -------- | --- | --------- | ---------- |
| suitable   |     | point, we   | have r | and      |     | 0. The PI | controller |
|            |     |             | a      | u        | a   |           |            |
| parameters |     | then become |        |          |     |           |            |
|            |     |             | K =    | K r cosφ |     |           |            |
u b b
(4.27)
T
|     |     |     | T =− | u      |     |     |     |
| --- | --- | --- | ---- | ------ | --- | --- | --- |
|     |     |     | i    | 2πtanφ |     |     |     |
b
Notice that φ must be negative in order to have positive controller
b
α =
| parameters. |     | Choosing | 0.25, | the PID | controller | parameters | are |
| ----------- | --- | -------- | ----- | ------- | ---------- | ---------- | --- |
given by
|     |     |     | K = K | r cosφ |     |     |     |
| --- | --- | --- | ----- | ------ | --- | --- | --- |
|     |     |     |       | u b    | b   |     |     |
(cid:20) (cid:21)
|     |     |     | T     | 1+sinφ |     |     |        |
| --- | --- | --- | ----- | ------ | --- | --- | ------ |
|     |     |     | = u   |        | b   |     |        |
|     |     |     | T i π | cosφ   |     |     | (4.28) |
b
(cid:20) 1+sinφ (cid:21)
|     |     |     | = T | u   | b   |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- |
T
|     |     |     | d 4π | cosφ |     |     |     |
| --- | --- | --- | ---- | ---- | --- | --- | --- |
b
| Noticethatthetuning |     |     | rulesareofthesameformasforthefrequency |     |     |     |     |
| ------------------- | --- | --- | -------------------------------------- | --- | --- | --- | --- |
response method but with different values of the numerical parame-
ters.Systems withbetter damping than theZiegler-Nichols rules can

| 142 | Chapter | 4 Controller |     | Design |     |     |     |     |
| --- | ------- | ------------ | --- | ------ | --- | --- | --- | --- |
be obtained by proper choices of r and φ. A reasonable choice is
|      |      |     |     |     | b b |     |     |     |
| ---- | ---- | --- | --- | --- | --- | --- | --- | --- |
| =0.5 | andφ | =20 | ○   |     |     |     |     |     |
| r    |      |     | .   |     |     |     |     |     |
| b    |      | b   |     |     |     |     |     |     |
It has been suggested by Pessen to move the ultimate point to
| −0.2  | −     | −0.2  | −      |      |               |     | =        |     |
| ----- | ----- | ----- | ------ | ---- | ------------- | --- | -------- | --- |
|       | 0.36i | or    | 0.21i. | This | corresponds   | to  | r b 0.41 | and |
| φ =61 | ○     | =0.29 | andφ   | =46  | ○             |     |          |     |
|       | , and | r     |        |      | respectively. |     |          |     |
| b     |       | b     |        | b    |               |     |          |     |
There arelimitations with a design method where only one point
on the Nyquist curve is positioned. The properties of the closed-loop
system can then change significantly depending on the slope of the
curve. This is illustrated in Figure 4.10, which shows the Nyquist
=2,
| curves | of three | systems | having | the | same amplitude |     | margin, | A   |
| ------ | -------- | ------- | ------ | --- | -------------- | --- | ------- | --- |
m
whichmeans thattheNyquist curves ofallsystems passthrough the
(−0.5,0).
| point        |        | The                   | figure | also shows | the closed-loop |     | responses | to a |
| ------------ | ------ | --------------------- | ------ | ---------- | --------------- | --- | --------- | ---- |
| step         | change | in setpoint.          |        |            |                 |     |           |      |
| Assessmentof |        | Ziegler-NicholsTuning |        |            |                 |     |           |      |
TheZiegler-Nichols tuning procedures aresimple and intuitive. They
require little process knowledge and they can beapplied with modest
effort. These are some of the reasons why they are so widely used.
The methods have, however, some limitations as we have already
seen. A fundamental drawback is that the basic design criterion is
to obtain a closed-loop system with quarter amplitude decay ratio
(d = 0.25).
|     |     | This gives | good | rejection | of load | disturbances, | but | also |
| --- | --- | ---------- | ---- | --------- | ------- | ------------- | --- | ---- |
creates a closed-loop system that is very poorly damped and that has
poor stability margins. The closed-loop gain is typically 2 to 3 times
too high. The frequency response method is more reliable than the
stepresponse method. Onereasonforthisisthattheultimate gainis
uniquelydefined,butthattherearemanywaystodefinetheapparent
dead time. The step response method typically also gives somewhat
higher gains.
The methods generally will work better for PID control than for
PI control. The reason for this will be discussed in Chapter 5. Let it
| suffice | here | to give | an example. |     |     |     |     |     |
| ------- | ---- | ------- | ----------- | --- | --- | --- | --- | --- |
| EXAMPLE |      | 4.3 PI  | control     |     |     |     |     |     |
Consider the same process as in Examples 4.1 and 4.2, where the
transfer function has three equal lags. See Equation (4.23). Mea-
=
surements on the step response give the parameters a 0.218 and
L = 0.806. The step response method gives a PI controller with pa-
|     |     | =   |     | =   |     |     | =   |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
rameters K 4.13 and T i 2.42√. The ultimate gain is K u 8 and
the ultimate period is T = 2π/ 3 (cid:9) 3.63. The frequency domain
u
method gives a PI controller with parameters K =3.2 and T =2.90.
i
Notice that the gains obtained with the frequency response method
arelower than those obtained with the step response method. Figure

|     |     |     | 4.3 Ziegler-Nichols’and |     | RelatedMethods | 143 |
| --- | --- | --- | ----------------------- | --- | -------------- | --- |
0
1
–1
0
|     | –1  |     | 0   | 0 20 | 40 60 80 100 |     |
| --- | --- | --- | --- | ---- | ------------ | --- |
0
1
0.5
–1
0
|     | –1  |     | 0   |       |             |     |
| --- | --- | --- | --- | ----- | ----------- | --- |
|     |     |     |     | 0 100 | 200 300 400 |     |
| 0   |     |     |     | 1     |             |     |
0.5
–1
0
|        | –1  |      | 0              | 0 20     | 40 60 80 100           |     |
| ------ | --- | ---- | -------------- | -------- | ---------------------- | --- |
| Figure |     | 4.10 | Nyquist curves | of three | systems with amplitude |     |
=2,andtheircorrespondingclosed-loopstepresponses.
| marginA |     | m   |     |     |     |     |
| ------- | --- | --- | --- | --- | --- | --- |
4.11 shows the response of the closed-loop system to step changes in
setpoint and load when the PI controller is tuned with the frequency
response method. The figure shows clearly that the decay ratio is
much larger than the design value d=1/4. The performance is even
worse if the step response method is used. Compare with Figure 4.8
which shows the results obtained with a PID controller tuned by the
| Ziegler-Nichols |     | frequency | response | method. |     |     |
| --------------- | --- | --------- | -------- | ------- | --- | --- |

| 144 | Chapter | 4 Controller |     | Design |     |     |     |     |
| --- | ------- | ------------ | --- | ------ | --- | --- | --- | --- |
y
1
y
sp
0
| 0   |     | 10  |     | 20  |     | 30  |     | 40  |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
u
2
−2
| 0   |     | 10  |     | 20  |     | 30  |     | 40  |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
Figure 4.11 Setpoint and load disturbance response of aprocess
| withtransferfunctionG(s)=(s+1)−3 |     |     |     |     | controlledbyaPIcontroller |     |     |     |
| -------------------------------- | --- | --- | --- | --- | ------------------------- | --- | --- | --- |
tuned with the Ziegler-Nichols frequency response method. The
| diagramsshow |     | setpoint | y   | ,processoutput |     | y,andcontrolsignal |     | u.  |
| ------------ | --- | -------- | --- | -------------- | --- | ------------------ | --- | --- |
sp
| Although |     | theZiegler-Nichols |     | methods |     | havemanyattractive |     | prop- |
| -------- | --- | ------------------ | --- | ------- | --- | ------------------ | --- | ----- |
ertiestheyarefarfromperfect.Hence,thereisaneedtocharacterize
thosesituationswherereasonabletuningisobtainedwiththeZiegler-
Nichols method andalso to estimate the achievable performance. For
this purpose the process will be characterized by the quantities nor-
|         |      | timeτandgain |     | ratioκintroduced |     |     |            |          |
| ------- | ---- | ------------ | --- | ---------------- | --- | --- | ---------- | -------- |
| malized | dead |              |     |                  |     |     | in Chapter | 2.Recall |
thatτis the ratio of apparent dead time and average residence time
and that κis the ratio of the process gains at frequencies ω and 0.
u
Also remember that both quantities normally vary from 0 to 1 and
that they are approximately linearly related. Furthermore processes
κorτare
| with small |          |     | easy to | control. | The | difficulty | increases | as the |
| ---------- | -------- | --- | ------- | -------- | --- | ---------- | --------- | ------ |
| parameters | approach | 1.  |         |          |     |            |           |        |
The following empirical rules have been developed based on sim-
ulation ofalargenumber ofsystems. Thereisnoprecise definition of
the region of validity. Roughly speaking they apply to processes with
| essentially | monotone | step  | responses. |           |     |            |      |            |
| ----------- | -------- | ----- | ---------- | --------- | --- | ---------- | ---- | ---------- |
| Case 1:     | Small    | κ and | τ.         | Processes |     | with small | κ or | τ are easy |
ofτmeans
| to control.                          | A   | small value |     |     | that | the dynamics            |     | is lag domi- |
| ------------------------------------ | --- | ----------- | --- | --- | ---- | ----------------------- | --- | ------------ |
| nated.Inthiscasetherearefactorsother |     |             |     |     |      | thanprocessdynamicsthat |     |              |
limits performance, e.g., measurement noise. If specifications on re-
sponse time are not severe, satisfactory performance can often be ob-
tainedwithaPIcontroller.ThetuningobtainedbytheZiegler-Nichols
methods can often be improved significantly by using other methods.
Derivativeactionorevenmorecomplicatedcontrollawsareoftenuse-
fulforobtaining systems withhighperformance inthosecaseswhere
the disturbances are small. Notice that the Ziegler-Nichols rules do
| not give | guidance | for finding |     | parameters |     | in PD controllers. |     |     |
| -------- | -------- | ----------- | --- | ---------- | --- | ------------------ | --- | --- |

|         |              | 4.3 | Ziegler-Nichols’and |         |     | RelatedMethods |       | 145 |
| ------- | ------------ | --- | ------------------- | ------- | --- | -------------- | ----- | --- |
| Case 2: | Intermediate | κ   | and                 | τ. This | is  | the primary    | range | for |
using the Ziegler-Nichols method for PID control. Derivative action
oftengivessignificantimprovementofperformance.Theovershootfor
setpoint changes can often be too large. It can be reduced by proper
| choice of | setpoint | weighting. |     |     |     |     |     |     |
| --------- | -------- | ---------- | --- | --- | --- | --- | --- | --- |
Case 3: κ and τ close to 1. This case corresponds to processes
| thataredeadtimedominated.TheZiegler-Nichols |     |     |     |     |     | tuningrulesdonot |     |     |
| ------------------------------------------- | --- | --- | --- | --- | --- | ---------------- | --- | --- |
performwellinthosecases.PIorPIDcontrolcanstillbeused,butthe
tuning rules must be improved. It is also possible to get drastically
improved setpoint responses by using other control algorithms like
the Smith predictor. (Compare with Example 3.4 in Section 3.9.)
| The | boundaries | between | the | different | cases | are | approximately |     |
| --- | ---------- | ------- | --- | --------- | ----- | --- | ------------- | --- |
0.07 and 0.4 for κ, or 0.15 and 0.4 for τ. The following example
illustrates that the Ziegler-Nichols rules give poor tuning in Case 3.
| EXAMPLE  | 4.4 Ziegler-Nichols |          |          | tuning   | for | κandτclose |     | to 1 |
| -------- | ------------------- | -------- | -------- | -------- | --- | ---------- | --- | ---- |
| Consider | a process           | with the | transfer | function |     |            |     |      |
−5s
e
G(s)=
(s+1)3
=1.25
| Applying | the frequency | response |     | method | we find | that | K   | and |
| -------- | ------------- | -------- | --- | ------ | ------- | ---- | --- | --- |
u
T =15.7.The controller parameters then become K =0.75, T =7.9
| u   |     |     |     |     |     |     |     | i   |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
=
| and T d | 2.0. The | normalized |     | dead | time varies | between |     | 0.6 and |
| ------- | -------- | ---------- | --- | ---- | ----------- | ------- | --- | ------- |
to 0.7 depending on the method used to compute it. Compare with
Section 2.4.Thegainratio is,however, uniquely defined andbecomes
κ=
0.8. This case thus belongs to Case 3 above. Figure 4.12 shows
a simulation of the setpoint and load responses of the closed-loop
system. The responses are oscillatory as can be expected. Notice also
that the recovery from load disturbances is slow because the integral
| action is  | too small.  |     |     |     |     |     |     |     |
| ---------- | ----------- | --- | --- | --- | --- | --- | --- | --- |
| Achievable | Performance |     |     |     |     |     |     |     |
It is also of interest to characterize the performance that can be
achievedwithZiegler-Nichols tunedPIDcontrollers.Afirstindication
is already given in Table 4.1 and Table 4.2, which give the period
of the closed-loop systems. Several empirical observations have been
| made from | experimental | investigations |     |     | of tuned | loops. |     |     |
| --------- | ------------ | -------------- | --- | --- | -------- | ------ | --- | --- |
The rise time obtained is approximately equal to the apparent
dead time for processes without integration and L/2 for processes
with integration.
| The | error due | to a step | disturbance |     | at  | the process | input | has |
| --- | --------- | --------- | ----------- | --- | --- | ----------- | ----- | --- |
a maximum at a time that is approximately equal to 0.25T or L.
u
κ,
The size of the peak is approximately 1.4K where K is the static
|         |              |          |       |                 | p   |      | p   |     |
| ------- | ------------ | -------- | ----- | --------------- | --- | ---- | --- | --- |
| process | gain. Notice | that the | error | is proportional |     | toκ. |     |     |

| 146 Chapter | 4   | Controller | Design |     |     |     |
| ----------- | --- | ---------- | ------ | --- | --- | --- |
y
sp
1
y
0
| 0   |     | 50  |     | 100 |     | 150 |
| --- | --- | --- | --- | --- | --- | --- |
u
1
−1
| 0   |     | 50  |     | 100 |     | 150 |
| --- | --- | --- | --- | --- | --- | --- |
Figure 4.12 Step responses of a process with the transfer func-
tion G(s)= e−5s/(s+1)3 controlled by PID controllers tuned with
theZiegler-Nicholsfrequencyresponsemethod.Thediagramsshow
| setpoint | y , process | output | y, and | controlsignal | u.  |     |
| -------- | ----------- | ------ | ------ | ------------- | --- | --- |
sp
With Ziegler-Nichols tuning the sensitivity is always larger than
2. In Section 4.2 it was shown that a quarter amplitude decay ratio
| corresponds | to a sensitivity |     | M =2.6. |     |     |     |
| ----------- | ---------------- | --- | ------- | --- | --- | --- |
s
TuningMaps
Since the Ziegler-Nichols methods only give “ball-park” values, it is
necessary tomakemanual tuning to obtain the desired performance.
A device called tuning maps have been developed to guide man-
ual tuning. The purpose of these maps is to provide intuition about
how changes in controller parameters influence the behaviour of the
closed-loop system. The tuning maps are simply two-dimensional ar-
rays of transient responses or frequency responses organized in a
| systematic | way. |     |     |     |     |     |
| ---------- | ---- | --- | --- | --- | --- | --- |
An example of a tuning map is given in Figure 4.13. The figure
illustrateshowtheloaddisturbanceresponseisinfluencedbychanges
| in gain and | integral | time. | The process | model |     |     |
| ----------- | -------- | ----- | ----------- | ----- | --- | --- |
1
G(s)=
(s+1)8
| hasbeenusedintheexample.TheZiegler-Nichols |     |     |     |     | frequencyresponse |     |
| ------------------------------------------ | --- | --- | --- | --- | ----------------- | --- |
method gives the controller parameters K = 1.13, T = 7.58, and
i
=
T d 1.9. The figure shows clearly the benefits of having a smaller
value of T. Judging from the figure, the values K = 1 and T = 5.0
|     | i   |     |     |     |     | i   |
| --- | --- | --- | --- | --- | --- | --- |
appear reasonable. The figure also shows that the choice of T is
i
<
fairly critical. Also notice that controllers with T 7.6 cannot be
i
| implemented | on series | form | (compare | with Section | 3.4). |     |
| ----------- | --------- | ---- | -------- | ------------ | ----- | --- |

|        |       |        | 4.3 Ziegler-Nichols’and |                 | RelatedMethods |           |        | 147 |
| ------ | ----- | ------ | ----------------------- | --------------- | -------------- | --------- | ------ | --- |
| K =1.5 | T =10 |        | K                       | =1.5 T =5       |                | K         | =1.5 T | =3  |
|        | i     |        |                         | i               |                |           | i      |     |
| K =1.0 | T =10 |        | K                       | =1.0 T =5       |                | K         | =1.0 T | =3  |
|        | i     |        |                         | i               |                |           | i      |     |
| K =0.5 | T =10 |        | K                       | =0.5 T =5       |                | K         | =0.5 T | =3  |
|        | i     |        |                         | i               |                |           | i      |     |
| Figure | 4.13  | Tuning | map                     | for PID control | of             | a process | with   | the |
transfer function G(s)=(s+1)−8. The figure shows the responses
to a unit step disturbance at the process input. Parameter T d has
| the value | 1.9. |     |     |     |     |     |     |     |
| --------- | ---- | --- | --- | --- | --- | --- | --- | --- |
Another example of a tuning map is given in Figure 4.14, which
shows the Nyquist curves of the loop transfer functions that corre-
spond toFigure 4.13.Thefigure shows thatwithZiegler-Nichols tun-
ing thereis toomuchphase lead. This isreduced byreducing param-
eter T. A comparative study of curves like Figure 4.13 and Figure
i
4.14 is a good way to develop intuition for the relations between the
| time domain |     | and the frequency |     | domain. |     |     |     |     |
| ----------- | --- | ----------------- | --- | ------- | --- | --- | --- | --- |
It is useful to have a simple way to judge if the integral action
of a controller is too weak, as in the three left and the lower middle
| examplesinFigures |     | 4.13and4.14.Suchacriterioncanbebasedona |     |     |     |     |     |     |
| ----------------- | --- | --------------------------------------- | --- | --- | --- | --- | --- | --- |
calculation of the asymptotic behaviour of the loop transfer function
for low frequencies. For a process with transfer function G and a PI
p
| controller | with | transfer | function | G we have |     |     |     |     |
| ---------- | ---- | -------- | -------- | --------- | --- | --- | --- | --- |
c
|     |     | G(cid:10) (s)= | G (s)G | (s) |     |     |     |     |
| --- | --- | -------------- | ------ | --- | --- | --- | --- | --- |
|     |     |                | p      | c   |     |     |     |     |
(cid:5) (cid:6)
|     |     |         | (cid:20) | (cid:21)   |      |     |     |     |
| --- | --- | ------- | -------- | ---------- | ---- | --- | --- | --- |
|     |     |         |          | (cid:8)(0) |      | 1   |     |     |
|     |     | (cid:9) | G (0)+sG |            | K 1+ |     |     |     |
|     |     |         | p        | p          |      | sT  |     |     |
i
(cid:8)(0)
|     |     |         | KG (0) |           | KG  |     |     |     |
| --- | --- | ------- | ------ | --------- | --- | --- | --- | --- |
|     |     | (cid:9) | p      | + KG (0)+ |     | p   |     |     |
p
|     |     |     | sT  |     |     | T   |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
|     |     |     | i   |     |     | i   |     |     |
Thus, for low frequencies the asymptote of the Nyquist curve is
| parallel | to the | imaginary | axis | with the real | part | equal | to  |     |
| -------- | ------ | --------- | ---- | ------------- | ---- | ----- | --- | --- |
(cid:5) (cid:6)
|     |     |      | KG  | (cid:8)(0) |     | T   |     |     |
| --- | --- | ---- | --- | ---------- | --- | --- | --- | --- |
|     |     | (0)+ |     | p =        | 1−  | ar  |     |     |
|     |     | KG   |     | KK         |     |     |     |     |
|     |     | p    |     | T          | p   | T   |     |     |
|     |     |      |     | i          |     | i   |     |     |
= G(0)
| where K |     | is the | static | process | gain, and | T   | is the | average |
| ------- | --- | ------ | ------ | ------- | --------- | --- | ------ | ------- |
|         | p   |        |        |         |           | ar  |        |         |
residence time. It is reasonable to require that the real part of the

148 Chapter 4 Controller Design
K =1.5 T i =10 K =1.5 T i =5 K =1.5 T i =3
x
0 0 x 0
x
x
x
–1 x –1 –1
–1 0 –1 0 –1 0
K =1.0 T i =10 K =1.0 T i =5 K =1.0 T i =3
0 x 0 x 0 x
x
x
x
–1 –1 –1
x
–1 0 –1 0 –1 0
K =0.5 T i =10 K =0.5 T i =5 K =0.5 T i =3
0 x 0 x 0 x
x
x x
x
–1 –1 x –1
x
–1 0 –1 0 –1 0
Figure 4.14 Tuning map for PID control of a process with
the transfer function G(s) = (s + 1)−8. The figure shows the
Nyquist curvesofthelooptransferfunction.Parameter T hasthe
d
value 1.9.
asymptote is less than −0.5. This gives
2KK
T < T p (4.29)
i ar 1+2KK
p
For the system in Figures 4.13 and 4.14, we get the requirement
T <6.0 for the systems in the upper row, T <5.3 for the systems in
i i
the middle row, and T < 4.0 for the systems in the lower row. This
i
means that condition (4.29) excludes the three left and the lower
middle examples in Figures 4.13 and 4.14.
Assuming that the process dynamics is governed by
e
−sL
G (s)= K
p p 1+sT

|     |     |     | 4.3 Ziegler-Nichols’and |     |     | RelatedMethods | 149 |
| --- | --- | --- | ----------------------- | --- | --- | -------------- | --- |
we find that T = L+T. With Ziegler-Nichols tuning of a PI con-
ar
(4.29)
| troller, we | then | find that | condition |     | is   | satisfied if |     |
| ----------- | ---- | --------- | --------- | --- | ---- | ------------ | --- |
|             |      |           | <(L+T)    |     | 1.8T |              |     |
3L
L+1.8T
This means that we must require that the normalized dead time
satisfies
|     |     |     | τ=  | L <0.28 |     |     |     |
| --- | --- | --- | --- | ------- | --- | --- | --- |
L+T
| A similar | calculation |     | for a | process | described | by  |     |
| --------- | ----------- | --- | ----- | ------- | --------- | --- | --- |
e −sL
(s)=
|     |     |     | G p | K p |     |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- |
(1+sT)2
which has
L+(3−e)T
τ=
L+2T
shows that condition (4.29) holds for a PI controller tuned according
| to the Ziegler-Nichols |     |     | method | if  |     |     |     |
| ---------------------- | --- | --- | ------ | --- | --- | --- | --- |
τ<0.38
| WecanthusconcludethattheZiegler-Nichols |     |     |     |     |     | tuningrulesforPIcon- |     |
| --------------------------------------- | --- | --- | --- | --- | --- | -------------------- | --- |
ofτ.
trollers can be applied only for small values The upper bound is
approximatelyτ=0.3.Forlarger normalized dead times theintegral
| action is | too weak. |     |     |     |     |     |     |
| --------- | --------- | --- | --- | --- | --- | --- | --- |
TheChien,HronesandReswickMethod
There has been many suggestions of modifications of the Ziegler-
| Nichols | methods. | Chien, | Hrones | and | Reswick | (CHR) changed | the |
| ------- | -------- | ------ | ------ | --- | ------- | ------------- | --- |
stepresponsemethodtogivebetterdampedclosed-loopsystems.They
proposed to use “quickest response without overshoot” or “quickest
response with 20% overshoot” as design criteria. They also made
the important observation that tuning for setpoint response or load
| disturbance | response |     | are different. |     |     |     |     |
| ----------- | -------- | --- | -------------- | --- | --- | --- | --- |
To tune the controller according to the CHR method, the param-
eters a and L of the process model are first determined in the same
way as for the Ziegler-Nichols step response method. The controller
parameters for the load disturbance response method are then given
as functions of these two parameters. They are summarized in Ta-
ble 4.3.
Thetuningrulesbasedonthe20%overshootdesigncriteriainTa-
ble 4.3 are quite similar to the Ziegler-Nichols step response method
presented in Table 4.1. However, when the 0% overshoot design cri-
teria is used, the gain and the derivative time are smaller and the

150 Chapter 4 Controller Design
Table4.3 ControllerparametersobtainedfromtheChien,Hrones
and Reswick load disturbance response method.
Overshoot 0% 20%
Controller K T T K T T
i d i d
P 0.3/a 0.7/a
PI 0.6/a 4L 0.7/a 2.3L
PID 0.95/a 2.4L 0.42L 1.2/a 2L 0.42L
integral time is larger. This means that the proportional action, the
integral action, as well as the derivative action, are smaller.
In the setpoint response method, the controller parameters are
not only based on a and L, but also on the time constant T. Methods
toobtain these parameters werepresented inSection 2.4.Thetuning
rules for setpoint response are summarized in Table 4.4.
Discussion
TheZiegler-Nichols tuning rules weredeveloped empirically basedon
simulation ofalargenumberofcases.Thecasesconsidered weretyp-
ically such that process dynamics is the main factor that limits per-
formance. When developing the rules it was also attempted to choose
numerical values that give simple rules. The methods aresimple and
easy to use. The process is characterized by two parameters that can
bedeterminedbysimpleexperiments.Thefrequencyresponsemethod
hastheadvantagethatparameters K andT areeasiertodetermine
u u
accurately than the parameters a and L, which are used by the step
response method.
Themaindesigncriterionwastoobtaingoodrejectionofloaddis-
turbancesspecified asquarteramplitude decayratio.Little emphasis
was given to measurement noise, sensitivity to process variations,
and setpoint response. The quarter amplitude decay ratio gives sys-
tems with very poor damping. The step response method often gives
higher loop gains than the frequency domain method. Both methods
givebetterparametersforPIDcontrolthanforPIcontrol,butinspite
of their widely spread use they give poor tuning.

|          |                                                 |       |          |         | 4.4   | Loop Shaping | 151 |
| -------- | ----------------------------------------------- | ----- | -------- | ------- | ----- | ------------ | --- |
| Table4.4 | ControllerparametersobtainedfromtheChien,Hrones |       |          |         |       |              |     |
| and      | Reswick setpoint                                |       | response | method. |       |              |     |
|          | Overshoot                                       |       | 0%       |         |       | 20%          |     |
|          | Controller                                      | K     | T        | T       | K     | T            | T   |
|          |                                                 |       | i        | d       |       | i            | d   |
|          |                                                 | 0.3/a |          |         | 0.7/a |              |     |
P
|     | PI           | 0.35/a | 1.2T |      | 0.6/a  | T    |       |
| --- | ------------ | ------ | ---- | ---- | ------ | ---- | ----- |
|     |              | 0.6/a  |      |      | 0.95/a |      |       |
|     | PID          |        | T    | 0.5L |        | 1.4T | 0.47L |
| 4.4 | Loop Shaping |        |      |      |        |      |       |
The Ziegler Nichols frequency response method tries to position one
point on the loop transfer function appropriately. Even though the
point is chosen cleverly it is surprising that such a method works so
well. Someconsequences of positioning one point only werediscussed
inSection4.3.Therearemanyotherdesignmethodsthattrytoobtain
a loop transfer function with a good shape. Some of these methods
| are discussed | in  | this section. |     |     |     |     |     |
| ------------- | --- | ------------- | --- | --- | --- | --- | --- |
SlopeAdjustments
Only two parameters are needed to change the value of the loop
transferfunctionatonefrequency.ThisisthereasonwhytheZiegler-
NicholsmethodgivesuniqueparametersforaPIcontroller.ForaPID
=
controller, which has three parameters, the condition T i 4T d was
introduced inordertoobtain unique parameter values. Thus, forPID
controllers we have one degree of freedom that can be used to shape
the loop transfer function. One possibility is to position one point
and to adjust the slope of the Nyquist curve at the chosen point.
ω
A natural requirement is that the slope at the chosen frequency 0
should be orthogonal to the line 1+G(cid:10) (iω ) (see Figure 4.15). This
0
ensures that the sensitivity is minimized locally. To see how this can
be accomplished, consider a system with Ziegler-Nichols tuning, i.e.,
1
|     |     |     | G (iω | )=− |     |     |     |
| --- | --- | --- | ----- | --- | --- | --- | --- |
|     |     |     | p     | u   | K   |     |     |
u
where the controller
|     |     |     |     | (cid:5)  |     | (cid:6)  |     |
| --- | --- | --- | --- | -------- | --- | -------- | --- |
|     |     |     |     | (cid:20) |     | (cid:21) |     |
1
|     |     | G (iω)= | K   | 1+i ωT | −    |     |     |
| --- | --- | ------- | --- | ------ | ---- | --- | --- |
|     |     | c       |     |        | d ωT |     |     |
i

152 Chapter 4 Controller Design
− 1
G i ω
R eG i
( )
ω
I mG i
( )
ω ( )
l
l
1 +G
l
l
Figure 4.15 Adjustment of the slope of the Nyquist curve.
is chosen so that the loop transfer function has the value r
ei(
b
π + φ )
b at
ω as was discussed in Section 4.3. This means that
u
K = K r cos
u b
φ
b
1
T −
d ω
1
=
2T
u i
ω
tan
u
φ
(4.30)
=a
b
Notice that we still have freedom to choose the ratio T/T . To make
i d
thischoice sothattheNyquist curvehasagiven slope at ω consider
u
thelooptransferfunction G(cid:10) (i ω )= G (i
p
ω )G (i
c
ω ).Differentiatingthe
loop transfer function with respect to ω gives.
dG(cid:10) (i ω )
d ω
= G (i
p
ω
dG (i
) c
ω )
d ω
dG (i
+ p
ω )
d ω
G (i
c
ω )
Furthermore, we have
dG (i
c
ω )
d ω
(cid:5)
1
= iK T +
d ω
(cid:6)
= iK(2T −a)
2T d
i
wherethelastequality follows fromEquation (4.30).Iftransfer func-
tion G is parameterized as
p
G (i
p
ω )=r( ω )ei( φ ( ω )− π )
straightforward but tedious calculations give
G(cid:10) (cid:8)(i ω
(cid:5)
(cid:8)
K r
)=− −a
u K r
u
φ (cid:8) ω
(cid:20)
+i
u
φ (cid:8)+a ω
(cid:6)
(cid:8) (cid:21)
r
+2T −a
u r d
(cid:8) where denotes derivative with respect to ω . Hence
dG(cid:10) (i
arg
ω )
=arctan
dt
φ (cid:8)+a ω r (cid:8)/r+2T −a
u d
r(cid:8)/r−a ω
u
φ (cid:8)

4.4 Loop Shaping 153
This gives the following equation for T .
d
(cid:5) (cid:6)
(cid:8) (cid:20) (cid:8) (cid:21)
1 r r
T = a−φ(cid:8)−aω + −aωφ(cid:8) tanψ (4.31)
d u u
2 r r
whereψis the desired slope of the Nyquist curve at ω . Parameter
u
T is then given by
i
1
T = (4.32)
i ω2(T −a)
u d
We illustrate the procedure with an example
EXAMPLE 4.5
Consider the same process model as in Examples 4.1 and 4.2, i.e.
1
G(s)=
(s+1)3
√This process has ultimate gain K
u
=8 and ultimate frequency ω
u
=
3. The amplitude r and its derivative, and the phase φ and its
derivative are
1 3ω
r = r (cid:8) =−
(1+ω2)3/2 (1+ω2)5/2
3
φ=π−3arctanω φ(cid:8) =−
(1+ω2)
Their values atω become
u
√
1 3 3 3
r(ω )= r (cid:8)(ω )=− φ(ω )=0 φ(cid:8)(ω )=−
u u u u
8 32 4
Suppose that wewant to move the ultimate point tothe new position
1
r = √ φ =45 ○
b b
2
The slope of Nyquist curve is orthogonal to the line 1+ G(cid:10) (iω
u
) if
it is c√hosen to ψ = 45 ○ . This choice gives an M
s
value equal to
M = 2(cid:9)1.4.
s
The controller parameters can now be obtained from Equations
(4.30),(4.31)and(4.32).Theybecome K =4,T =1.9,andT =0.75.
i d
Figure 4.16 shows the response of the closed-loop systems to a step
change in setpoint followed by a step change in the load.
FrequencyDomainDesignofa PIDController
The Ziegler-Nichols method was based on knowledge of the process
transfer function at the ultimate point. The design method we have

154 Chapter 4 Controller Design
y
1
y
sp
0
0 10 20 30 40
u
2
−2
0 10 20 30 40
Figure 4.16 Setpoint and load disturbance response of aprocess
with transfer function 1/(s + 1)3 controlled by a PID controller
tuned with the loop-shaping method. The diagrams show setpoint
y , processoutput y, and controlsignal u.
sp
just discussed requires, in addition, knowledge of the slope of the
plant transfer function at the ultimate point. More effective methods
can be used if the whole plant transfer function is known. Such a
method will now be discussed.
The design criterion is to obtain a specified sensitivity M with
s
good rejection of load disturbances. Let r(ω)andφ(ω)denote magni-
tude and phase of the frequency response of the process i.e.
G
(iω)=r(ω)ei(φ(ω)−π)
p
and let the controller transfer function be
k
G (s)= k+ i +k s
c d
s
To have a given sensitivity M , the Nyquist curve of the loop trans-
s
fer function must avoid a circle around the critical point with radius
r = 1/M (see Figure 4.17). Assume that the curve meets the cir-
0 s
cle tangentially at the point A. The condition that the loop transfer
function goes through A is
(cid:5) (cid:6)
(cid:20) (cid:21)
k
r(ω)ei(φ(ω)−π) k+i k ω− i =−1+r cosθ−ir sinθ
d ω 0 0
where r andθaredefined in Figure 4.17. Separating real and imag-
0
inary parts we get
r(ω)
kr(ω)cosφ(ω)+k sinφ(ω)−k ωr(ω)sinφ(ω)=−1+r cosθ
i ω d 0
r(ω)
kr(ω)sinφ(ω)−k cosφ(ω)+k ωr(ω)cosφ(ω)=−r sinθ
i ω d 0

|     |     |     |     |     | 4.4 Loop | Shaping | 155 |
| --- | --- | --- | --- | --- | -------- | ------- | --- |
( )
|     |     |     |     |    I |    mG i ω |     |     |
| --- | --- | --- | --- | ---- | --------- | --- | --- |
l
−1
|     |     |     | θ   | φ   |           |     |     |
| --- | --- | --- | --- | --- | --------- | --- | --- |
|     |     |     |     | δ   |    eG ( i | ω ) |     |
|     |     |     | r   |     |    R l    |     |     |
  0
A
Figure 4.17 Geometrical illustration of the loop-shaping design
method.
Calculating the derivative of the loop transfer function we find, after
simplifications,
(cid:23)
|     |            |        |               | (cid:2) | (cid:3)     |     |     |
| --- | ---------- | ------ | ------------- | ------- | ----------- | --- | --- |
|     |            | (i ω ) |               | (cid:8) |             |     |     |
|     | dG(cid:10) |        | =rei( φ − π ) | r       | k i (cid:8) |     |     |
|     |            |        |               | k − ω   | k − φ       |     |     |
|     |            | d ω    |               | r       | d ω         |     |     |
(cid:24)
|     |     |     | (cid:5) | (cid:2) | (cid:3) | (cid:6) |     |
| --- | --- | --- | ------- | ------- | ------- | ------- | --- |
(cid:8)
|      |           |            | +i       | φ (cid:8)+ ω −    | k i r +k + | k i |     |
| ---- | --------- | ---------- | -------- | ----------------- | ---------- | --- | --- |
|      |           |            |          | k k               |            |     |     |
|      |           |            |          | d                 | ω r d      | ω 2 |     |
| The  | condition | for        | tangency | can be written    | as         |     |     |
|      |           |            |          | dG(cid:10) (i ω ) | π          |     |     |
|      |           |            |          | =                 | − θ        |     |     |
|      |           |            | arg      | ω                 |            |     |     |
|      |           |            |          | d                 | 2          |     |     |
| This | can be    | simplified | to       |                   |            |     |     |
|      |           |            | ak+bk    | +ck               | =0         |     |     |
i d
where
(cid:8)( ω )
|     |     |     | a= φ (cid:8)( ω | )− r | δ   |     |     |
| --- | --- | --- | --------------- | ---- | --- | --- | --- |
tan
r( ω )
|     |     |     | 1   | r (cid:8)( ω ) | φ (cid:8)( ω )tan δ |     |        |
| --- | --- | --- | --- | -------------- | ------------------- | --- | ------ |
|     |     |     | b=  | − −            |                     |     | (4.33) |
|     |     |     | ω   | ω r( ω )       | ω                   |     |        |
2
|     |     |     |      | ω (cid:8)( ω ) |            |     |     |
| --- | --- | --- | ---- | -------------- | ---------- | --- | --- |
|     |     |     |      | r              | (cid:8)(   |     |     |
|     |     |     | c=1+ | + ω            | φ ω )tan δ |     |     |
|     |     |     |      | r( ω )         |            |     |     |
δ
and the angle is defined in Figure 4.17. We thus obtain three equa-
tions to determine the controller parameters k, k, and k . Notice,
|     |     |     |     |     | i   |     | d   |
| --- | --- | --- | --- | --- | --- | --- | --- |
however, thatboth ω and θ canbeconsidered asunknowns. Todeter-
minetheseparameters, wecanintroduce thecondition that k should
i
be as large as possible, i.e., to minimize IE. Another possibility is

| 156 | Chapter 4 Controller |     | Design |     |     |     |     |
| --- | -------------------- | --- | ------ | --- | --- | --- | --- |
to make ωas large as possible. The design of the controller then is
θvaries
| reduced | to an optimization |     | problem. | Notice | that | parameter |     |
| ------- | ------------------ | --- | -------- | ------ | ---- | --------- | --- |
in the range (0,π/2). The value ω can be used as an initial value
u
for the optimization. Instead of minimizing IEwe could also consider
minimization of IAE. However, this will increase the computational
effort considerably. Notice that when performing the optimization we
theargumentω
| also obtain |     |     | for which | the | optimum | isachieved. | This |
| ----------- | --- | --- | --------- | --- | ------- | ----------- | ---- |
0
indicates the frequency range where model precision is needed.
| 4.5 | Analytical | Tuning |     | Methods |     |     |     |
| --- | ---------- | ------ | --- | ------- | --- | --- | --- |
There are several analytical tuning methods where the controller
transfer function is obtained from the specifications by a direct cal-
culation. Let G and G be the transfer functions of the process and
|     | p   | c   |     |     |     |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- |
the controller. The closed-loop transfer function obtained with error
| feedback | is then |     |     |     |     |     |     |
| -------- | ------- | --- | --- | --- | --- | --- | --- |
G G
|     |     |     | G =   | p c |     |     |     |
| --- | --- | --- | ----- | --- | --- | --- | --- |
|     |     |     | 0 1+G |     |     |     |     |
p G c
| Solving | this equation | for | G we get |     |     |     |     |
| ------- | ------------- | --- | -------- | --- | --- | --- | --- |
c
|     |     |     | 1   | G   |     |     |        |
| --- | --- | --- | --- | --- | --- | --- | ------ |
|     |     |     | =   | ⋅ 0 |     |     | (4.34) |
G c
|     |     |     | G   | 1−G |     |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- |
|     |     |     | p   |     | 0   |     |     |
Iftheclosed-loop transfer function G isspecified and G isknown,it
|                      |     |     |                                      | 0   |     | p   |     |
| -------------------- | --- | --- | ------------------------------------ | --- | --- | --- | --- |
| isthuseasytocomputeG |     |     | .Thekeyproblemistofindreasonableways |     |     |     |     |
c
to determine G based on engineering specifications of the system.
0
It follows from Equation (4.34) that all process poles and zeros
are canceled by the controller. This means that the method cannot
be applied when the process has poorly damped poles and zeros. The
method will also give a poor load disturbance response when slow
| process | poles are canceled. |     |     |     |     |     |     |
| ------- | ------------------- | --- | --- | --- | --- | --- | --- |
λ-Tuning
The method called λ-tuning was developed for processes with long
| dead time | L. Consider | a   | process with | the   | transfer | function |     |
| --------- | ----------- | --- | ------------ | ----- | -------- | -------- | --- |
|           |             |     | = K          | p −sL |          |          |     |
|           |             |     | G            | e     |          |          |     |
p 1+sT
Assume that the desired closed-loop transfer function is specified as
e −sL
G =
|     |     |     | 0 1+sλT |     |     |     |     |
| --- | --- | --- | ------- | --- | --- | --- | --- |

4.5 Analytical Tuning Methods 157
where λis a tuning parameter. The time constants of the open- and
closed-loop systems arethesamewhenλ=1.Theclosed-loop system
responds faster than the open-loop system if λ<1. It is slower when
λ>1.
It follows from Equation (4.34) that the controller transfer func-
tion becomes
1+sT
G = (4.35)
c K (1+λsT−e−sL)
p
The controller has integral action, because G (0) = ∞. The input-
c
output relation of the controller is
(cid:20) (cid:21)
1
1+sλT−e −sL U(s)= (1+sT)E(s) (4.36)
K
p
This can be written as
(cid:5) (cid:6)(cid:5) (cid:6)
(cid:20) (cid:21)
1 1 K
U(s)= 1+ E(s)− p 1−e −sL U(s) (4.37)
λK sT 1+sT
p
When L = 0, this becomes a PI controller with gain K = 1/(λK )
p
and integral time T = T. The term
i
(cid:20) (cid:21)
K
p 1−e −sL U(s)
1+sT
can be interpreted as a prediction of the process output at time t
basedonthevaluesofthecontrolsignalinthetimeinterval(t−T,t).
The controller given by Equation (4.37) can thus be interpreted as a
predictive PI controller where the prediction is formed by correcting
fortheeffectsofthecontrolactionsthathavebeentaken,buthavenot
yet appeared in the output because of the delay in the process. The
controller is, therefore, called a predictive PI controller (PPI). For
processes with long dead times, the prediction given in Equations
(4.36) and (4.37) is much better than the prediction obtained by
derivative action.
The PPI controller can be written as
(cid:5) (cid:6)
(cid:20) (cid:21)
1 1 1
U(s)= 1+ E(s)− 1−e −sL U(s) (4.38)
λK sT sλT
p
In Section 4.2, it was shown that the integral error for a PID
controller is
T
IE = i
PID
K
Theintegrated errorsobtained withaPIDcontroller andacontroller
with λ-tuning are compared. With a PID controller based on the
Ziegler-Nichols step response method, we obtain
K L2
IE = p
PID
0.6T

158 Chapter 4 Controller Design
TocomputetheintegralerrorforthePPIcontrolleritwillbeassumed
that the system is initially at rest and that a load disturbance in the
formofaunitstepisappliedtotheprocessinput.Sincethecontroller
has integral action, we have u(∞)=1. To integrate Equation (4.38),
first note that
(cid:1)
∞(cid:20) (cid:21)
1 L
u(t)−u(t−L) dt=
λT λT
0
Integration of Equation (4.38) from 0 to ∞ now gives
(cid:1)
∞
1 L
u(∞)−u(0)=1= e(t)dt−
λK T λT
p 0
The integral error thus becomes
IE = K (L+λT)
PPI p
The integrated error is smaller with PPI control than with PID
controlwhen Lislarge.Forλ=1thecriteriaareequalwhen L/T =
1.1. The improvements with PPI control increases with decreasing
values of λ.
The sensitivity function obtained with λ-tuning is given by
e −sL 1+sλT −e −sL
S(s)=1− =
1+sλT 1+sλT
It can be shown that
M =max(cid:2)S(iω)(cid:2)
s ω
is always less than 2. An approximate expression for M is given by
s
T
M =2−λ
s L
Thus, to have a value of M smaller than 2 it is important that λis
s
sufficiently large.
We note that in order to make the integrated error small it is
advantageous tohave asmallvalue ofλ.Asmallvalue ofλ,however,
will increase the sensitivity.
In practice it is common to choose λbetween 0.5 and 5. The PPI
controller is particularly simple if λ= 1, i.e., if the desired closed-
loop time constant is equal to the open-loop time constant. Equation
(4.38) then becomes
(cid:5) (cid:6)
(cid:20) (cid:21)
1 1
U(s)= K 1+ E(s)− 1−e −sL U(s)
sT sT
i i
where K =1/K and T = T. This equation can also be written as
p i
e
−sL
U(s)= KE(s)+ U(s) (4.39)
1+sT
i

4.5 Analytical Tuning Methods 159
e u
K Σ
I
e−sL
1+sT
i
Figure 4.18 Block diagram ofthe PPI controller with λ=1.
A block diagram describing this equation is given in Figure 4.18. No-
tice the strong similarity with the PI controller shown in Figure 3.8.
TheHaalmanMethod
Another approach is to determine an ideal loop transfer function
G(cid:10) that gives the desired performance and to choose the controller
transfer function as
G =
G(cid:10)
(4.40)
c
G
p
where G is the process transfer function. Such an approach can
p
give PI and PID controllers provided that G(cid:10) and G
p
are sufficiently
simple. There are many ways to obtain a suitable G(cid:10).
Forsystemswithatimedelay L,Haalmanhassuggestedchoosing
2
G(cid:10) (s)= e −sL (4.41)
3Ls
The value 2/3 was found by minimizing the mean square error for a
step change in the setpoint. This choice gives a sensitivity M =1.9,
s
whichisareasonablevalue. Noticethatitisonlythedeadtimeofthe
process that influences the loop transfer function. All other process
poles and zeros are canceled, which may lead to difficulties.
ApplyingHaalman’smethodtoaprocesseswiththetransferfunc-
tion
1
G (s)= e −sL
p 1+sT
gives the controller
2(1+sT) 2T (cid:20) 1 (cid:21)
G (s)= = 1+
c
3Ls 3L sT
which is a PI controller with K = 2T/3L and T = T. These param-
i
eters can be compared with the values K =0.9T/L and T =3L ob-
i
tained by the Ziegler-Nichols step response method. A PID controller

| 160 | Chapter 4 | Controller | Design |     |     |     |     |     |     |
| --- | --------- | ---------- | ------ | --- | --- | --- | --- | --- | --- |
y
1
y sp
0
| 0   | 10  |     | 20  |     | 30  | 40  |     | 50  |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
u
1
−1
| 0                                           | 10   |                                               | 20  |     | 30  | 40            |     | 50  |     |
| ------------------------------------------- | ---- | --------------------------------------------- | --- | --- | --- | ------------- | --- | --- | --- |
| Figure                                      | 4.19 | Simulationofaclosed-loopsystemobtainedbyHaal- |     |     |     |               |     |     |     |
| man’smethod.TheplanttransferfunctionisG(s)= |      |                                               |     |     |     | e−s/(s+1).The |     |     |     |
diagramsshow setpoint y sp ,processoutput y,andcontrolsignal u.
is obtained if the method is applied to a process with the transfer
function
|                              |           | (s)= |       | 1      |      | −sL      |     |     |     |
| ---------------------------- | --------- | ---- | ----- | ------ | ---- | -------- | --- | --- | --- |
|                              |           | G    |       |        |      | e        |     |     |     |
|                              |           | p    | (1+sT | )(1+sT | )    |          |     |     |     |
|                              |           |      |       | 1      | 2    |          |     |     |     |
|                              |           |      |       |        | =2(T | +T )/3L, |     | =T  | +T  |
| Theparametersofthecontroller |           |      |       | are K  |      |          | T   |     | ,   |
|                              |           |      |       |        | 1    | 2        | i   | 1   | 2   |
| and T                        | = T T /(T | +T   | ).    |        |      |          |     |     |     |
| d                            | 1 2       | 1 2  |       |        |      |          |     |     |     |
For more complex processes it is necessary to approximate the
processes to obtain a transfer function of the desired form as was
discussedinSection2.9.Figure4.19showsasimulationofHaalman’s
method for asystem whose dynamics isdominated bydeadtime. The
normalized dead time is 0.5 for this system. The figure shows that
| the responses | are | excellent. |     |     |     |     |     |     |     |
| ------------- | --- | ---------- | --- | --- | --- | --- | --- | --- | --- |
DrawbacksofPole-ZeroCancellations
AkeyfeatureofHaalman’smethodisthatprocesspolesandzerosare
canceled by poles and zeros in the controller. When poles and zeros
are canceled, there will be uncontrollable modes in the closed-loop
system. This may lead to poor performance if the modes are excited.
The problem is particular severe if the canceled modes are slow or
| unstable. | We use   | an example | to              | illustrate | what | may             | happen. |     |     |
| --------- | -------- | ---------- | --------------- | ---------- | ---- | --------------- | ------- | --- | --- |
| EXAMPLE   | 4.6 Loss | of         | controllability |            | due  | to cancellation |         |     |     |
Consider aclosed-loop system whereaprocesswiththetransfer func-
tion
1
|     |     |     | G (s)= |      | e −sL |     |     |     |     |
| --- | --- | --- | ------ | ---- | ----- | --- | --- | --- | --- |
|     |     |     | p      | 1+sT |       |     |     |     |     |

4.5 Analytical Tuning Methods 161
iscontrolledwithaPIcontroller whoseparametersarechosensothat
the process pole is canceled. The transfer function of the controller is
then
(cid:20) 1 (cid:21) 1+sT
G (s)= K 1+ = K
c
sT sT
The process can be represented by the equation
dy(t) 1
= (u(t−L)−y(t)) (4.42)
dt T
and the controller can be described by
(cid:5) (cid:6)
du(t) dy(t) y(t)
=−K + (4.43)
dt dt T
Consider the behaviour of the closed-loop system when the initial
conditions are chosen as y(0) = 1 and u(t) = 0 for −L < t < 0.
Without feedback the output is given by
y (t)= e −t/T
ol
To compute the output for the closed-loop system we first eliminate
y(t) between Equations (4.42) and (4.43). This gives
du(t) K
=− u(t− L)
dt T
It thus follows that u(t)=0, and Equation (4.42) then implies that
y (t)= e −t/T = y (t)
cl ol
The trajectories of the closed-loop system and the open-loop system
thus are the same. The control signal is zero, which means that the
controller does not attempt to reduce the control error.
Theexampleclearlyindicates thattherearedrawbackswithcan-
cellation of process poles. Another illustration of the phenomenon is
given in Figure 4.20, which is a simulation of a closed-loop system
where the controller is designed by Haalman’s method. This simula-
tion is identical tothe simulation in Figure 4.19 but the process time
constant is now 10 instead of 1 for the simulation in Figure 4.19. In
this case we find that the setpoint response is excellent but that the
response toload disturbances is very poor. The reason for this is that
the controller cancels the pole s = −0.1, by having a controller zero
at s = −0.1. Notice that the process output after a load disturbance
decays with the time constant T = 10, but that the control signal is
practically constant due to the cancellation. The attenuation of load
disturbances is improved considerably by reducing the integral time
of the controller as shown in Figure 4.20.

| 162 Chapter | 4   | Controller | Design |     |     |     |     |     |
| ----------- | --- | ---------- | ------ | --- | --- | --- | --- | --- |
Haalman
Haalman
1
Retuned
Retuned
0
| 0   | 10  |     | 20  |     | 30  |     | 40  | 50  |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
Haalman
Retuned
0
Haalman
| −10                                           |      |                                               |     | Retuned   |     |              |              |     |
| --------------------------------------------- | ---- | --------------------------------------------- | --- | --------- | --- | ------------ | ------------ | --- |
| 0                                             | 10   |                                               | 20  |           | 30  |              | 40           | 50  |
| Figure                                        | 4.20 | Simulationofaclosed-loopsystemobtainedbyHaal- |     |           |     |              |              |     |
| man’smethod.TheprocesstransferfunctionisG(s)= |      |                                               |     |           |     |              | e−s/(10s+1), |     |
|                                               |      |                                               |     | =6.67andT |     | =10.Theupper |              |     |
| andthecontrollerparametersare                 |      |                                               |     | K         |     | i            |              |     |
=1andprocessoutput
| diagramshowssetpoint |     |     | y   |     |     | y,andthelower |     |     |
| -------------------- | --- | --- | --- | --- | --- | ------------- | --- | --- |
sp
diagramshowscontrolsignalu.Thefigurealsoshowstheresponses
| to aretuned |     | controller | with K | =6.67, | T =3and | b=0.5. |     |     |
| ----------- | --- | ---------- | ------ | ------ | ------- | ------ | --- | --- |
i
We have thus shown that cancellation of process poles may give
systemswithpoorrejectionofloaddisturbances. Noticethatthisdoes
| notshowupinsimulations |     |     | unlesstheprocessisexcited.Forexample, |     |     |     |     |     |
| ---------------------- | --- | --- | ------------------------------------- | --- | --- | --- | --- | --- |
it will not be noticed in a simulation of a step change in the setpoint.
We may also ask why there is such a big difference in the simulation
in Figure 4.18 and Figure 4.20. The reason is that the canceled pole
in Figure 4.20 is slow in comparison with the closed-loop poles, but
it is of the same magnitude as the closed-loop poles in Figure 4.18.
We can thus conclude that pole cancellation can be done for sys-
tems that are dead time dominated but not for systems that are lag
dominated.
TheInternalModelController(IMC)
Theinternal modelprinciple isageneral methodfordesign ofcontrol
systems that can be applied to PID control. A block diagram of such
a system is shown in Figure 4.21. In the diagram it is assumed that
all disturbances acting on the process are reduced to an equivalent
| disturbance | dattheprocessoutput.Inthefigure |     |     |     |     | G   | denotesamodel |     |
| ----------- | ------------------------------- | --- | --- | --- | --- | --- | ------------- | --- |
m
of the process, G† is an approximate inverse of G , and G is a low-
|     |     | m   |     |     |     | m   |     | f   |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
pass filter. The name internal model controller derives from the fact
that the controller contains a model of the process internally. This
| model is | connected | in  | parallel | with the | process. |     |     |     |
| -------- | --------- | --- | -------- | -------- | -------- | --- | --- | --- |
=
If the model matches the process, i.e., G G , the signal e is
|                                                 |     |     |     |     |     | m   | p       |     |
| ----------------------------------------------- | --- | --- | --- | --- | --- | --- | ------- | --- |
| equaltothedisturbancedforallcontrolsignalsu.IfG |     |     |     |     |     |     | =1andG† | is  |
|                                                 |     |     |     |     |     |     | f       | m   |

|            |     |     |     | 4.5 | Analytical | Tuning Methods | 163 |
| ---------- | --- | --- | --- | --- | ---------- | -------------- | --- |
| Controller |     |     |     |     |            |                | d   |
Process
y
|   sp |     |     |     |      | u   |      | y   |
| ---- | --- | --- | --- | ---- | --- | ---- | --- |
|      | Σ   | G   |     | G†   |     | G    | Σ   |
|      |     |     | f   |      | m   |    p |     |
G
   m
−
e
|     |     |     | −1  |     | Σ   |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- |
Figure 4.21 Block diagram of a closed-loop system with a con-
| troller | based | on theinternal |     | model | principle. |     |     |
| ------- | ----- | -------------- | --- | ----- | ---------- | --- | --- |
anexactinverseoftheprocess,thenthedisturbancedwillbecanceled
perfectly. The filter G is introduced to obtain a system that is less
f
sensitive to modeling errors. A common choice is G (s)=1/(1+sT),
|       |      |          |            |     |     | f   | f   |
| ----- | ---- | -------- | ---------- | --- | --- | --- | --- |
| where | T is | a design | parameter. |     |     |     |     |
f
The controller obtained by the internal model principle can be
representedasanordinaryseriescontrollerwiththetransferfunction
G G†
|     |     |     | G   | =     | f m |     | (4.44) |
| --- | --- | --- | --- | ----- | --- | --- | ------ |
|     |     |     |     | c 1−G | G†  |     |        |
G
|     |     |     |     |     | f m | m   |     |
| --- | --- | --- | --- | --- | --- | --- | --- |
From this expression it follows that controllers of this type cancel
| process                                               | poles | and zeros. |     |     |     |     |        |
| ----------------------------------------------------- | ----- | ---------- | --- | --- | --- | --- | ------ |
| Theinternalmodelprinciplewilltypicallygivecontrollers |       |            |     |     |     |     | ofhigh |
order.Bymakingspecialassumptionsitis,however,possibletoobtain
PIorPIDcontrollersfromtheprinciple.Toseethisconsideraprocess
| with | the transfer | function |     |     |     |     |     |
| ---- | ------------ | -------- | --- | --- | --- | --- | --- |
K
|     |     |     |     | (s)= | p −sL |     | (4.45) |
| --- | --- | --- | --- | ---- | ----- | --- | ------ |
|     |     |     | G   |      | e     |     |        |
p 1+sT
| An approximate |     | inverse | is  | given | by  |     |     |
| -------------- | --- | ------- | --- | ----- | --- | --- | --- |
1+sT
G†(s)=
|     |     |     |     | m   | K   |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- |
p
Notice that it is not attempted to find an inverse of the time delay.
| Choose | the | filter |     |      |     |     |     |
| ------ | --- | ------ | --- | ---- | --- | --- | --- |
|        |     |        |     | (s)= | 1   |     |     |
G
|     |     |     |     | f   | 1+sT |     |     |
| --- | --- | --- | --- | --- | ---- | --- | --- |
f
| Approximating |     | the time | delay | by  |     |     |     |
| ------------- | --- | -------- | ----- | --- | --- | --- | --- |
−sL
e (cid:9)1−sL

| 164      | Chapter | 4 ControllerDesign |     |     |     |
| -------- | ------- | ------------------ | --- | --- | --- |
| Equation | (4.44)  | now gives          |     |     |     |
1+sT
G (s)=
|     |     |     | c s(L+T) |     |     |
| --- | --- | --- | -------- | --- | --- |
|     |     |     | K p      | f   |     |
which is a PI controller. If the time delay is approximated instead by
| a first-order | Padé | approximation |     |     |     |
| ------------- | ---- | ------------- | --- | --- | --- |
1−sL/2
−sL
|     |     |     | e (cid:9) |     |     |
| --- | --- | --- | --------- | --- | --- |
1+sL/2
(4.44)
| Equation |      | gives instead  | the PID controller |                |     |
| -------- | ---- | -------------- | ------------------ | -------------- | --- |
|          |      | (1+sL/2)(1+sT) |                    | (1+sL/2)(1+sT) |     |
|          | (s)= |                | (cid:9)            |                |     |
G
|     | c   | K s(L+T | +sT L/2) | K s(L+T) |     |
| --- | --- | ------- | -------- | -------- | --- |
|     |     | p       | f f      | p f      |     |
(4.45),
| For processes |     | described | by Equation | we thus find | that the |
| ------------- | --- | --------- | ----------- | ------------ | -------- |
internal model principle will give PI or PID controllers. Approxima-
tions like the ones discussed in Section 2.9 can be used in the usual
manner to obtain PI and PID controllers for more complex processes.
An interesting feature of the internal model controller is that
robustness is considered explicitly in the design. Robustness can be
adjusted by selecting the filter G properly. A trade-off between per-
f
formanceandrobustnesscanbemadebyusingthefilterconstantasa
designparameter.TheIMCcanbedesignedtogiveexcellentresponse
to setpoint changes. Since the design method inherently implies that
poles and zeros of the plant are canceled, the response to load dis-
turbances may be poor if the canceled poles are slow in comparison
| withthedominant |     | poles. | Comparewiththeresponses | inFigure4.20. |     |
| --------------- | --- | ------ | ----------------------- | ------------- | --- |
The IMC controller can also be viewed as an extension of the Smith
predictor.
| 4.6 | Optimization |     | Methods |     |     |
| --- | ------------ | --- | ------- | --- | --- |
Optimization is a powerful tool for design of controllers. The method
is conceptually simple. A controller structure with a few parameters
is specified. Specifications are expressed as inequalities of functions
of the parameters. The specification that is most important is cho-
sen as the function to optimize. The method is well suited for PID
controllers where the controller structure and the parameterization
are given. There are several pitfalls when using optimization. Care
must be exercised when formulating criteria and constraints; other-
wise, a criterion will indeed be optimal, but the controller may still
be unsuitable because of a neglected constraint. Another difficulty is
that the loss function may have many local minima. A third is that
the computations required may easily be excessive. Numerical prob-
lems may also arise. Nevertheless, optimization is a good tool that

|     |     |     |     |     | 4.6 | Optimization | Methods | 165 |
| --- | --- | --- | --- | --- | --- | ------------ | ------- | --- |
Table 4.5 Controller parameters obtained from minimization of
| integratedabsolute |     |      | error, | IAE. |      |      |      |     |
| ------------------ | --- | ---- | ------ | ---- | ---- | ---- | ---- | --- |
|                    |     | L    | IAE    | M    | K    | K    | T    |     |
|                    |     |      |        | s    | hf   |      | i    |     |
|                    |     |      |        |      | ∞    | ∞    |      |     |
|                    |     | 0.0  | 0      |      |      |      | 0    |     |
|                    |     | 0.2  | 0.14   | 3.3  | 4.7  | 4.7  | 0.62 |     |
|                    |     | 0.5  | 0.60   | 3.0  | 2.0  | 2.0  | 1.1  |     |
|                    |     | 1.0  | 1.5    | 2.4  | 1.0  | 1.0  | 1.4  |     |
|                    |     | 2.0  | 3.2    | 2.1  | 0.60 | 0.60 | 1.8  |     |
|                    |     | 5.0  | 7.7    | 2.0  | 0.42 | 0.42 | 3.1  |     |
|                    |     | 10.0 | 15     | 1.9  | 0.37 | 0.37 | 5.3  |     |
has successfully been used to design PID controllers. In this section
| we discuss | some      | of   | these methods. |          |           |         |     |     |
| ---------- | --------- | ---- | -------------- | -------- | --------- | ------- | --- | --- |
| EXAMPLE    | 4.7       | A PI | controller     |          | optimized | for IAE |     |     |
| Consider   | a process |      | with the       | transfer | function  |         |     |     |
1
|     |     |     | G   | (s)= | e   | −sL |     | (4.46) |
| --- | --- | --- | --- | ---- | --- | --- | --- | ------ |
|     |     |     |     | p    | s+1 |     |     |        |
Table4.5gives controller parameters obtained whenminimizing IAE
for load disturbances. Some of the other criteria arealso given in the
table. Notice that the integrated absolute error increases with L, as
can be expected. Notice also that, although the criterion IAE is min-
imized, several other design criteria such as the M value and the
s
high-frequency controller gain K have undesirable values. Notice
hf
in particular that the values of M are quite high. The example illus-
s
trates the necessity of considering many performance criteria when
using optimization methods. Unfortunately, this was not observed in
| much of               | the | early work      | on    | controller   | tuning.       |                    |     |     |
| --------------------- | --- | --------------- | ----- | ------------ | ------------- | ------------------ | --- | --- |
| TuningFormulasBasedon |     |                 |       | Optimization |               |                    |     |     |
| Manystudies           |     | havebeendevoted |       |              | todevelopment | oftuningrulesbased |     |     |
| on optimization.      |     | Very            | often | a process    | described     | by                 |     |     |
|                       |     |                 |       |              | K −sL         |                    |     |     |
|                       |     |                 |       | G =          | p e           |                    |     |     |
p 1+sT
hasbeenconsidered.Thelossfunctionsobtainedforunitstepchanges
insetpointandprocessinputhavebeencomputedandformulasofthe

| 166 | Chapter |     | 4 Controller |     | Design |     |     |     |
| --- | ------- | --- | ------------ | --- | ------ | --- | --- | --- |
type
(cid:5) (cid:6)
b
L
p=a
T
where p is a controller parameter and a and b are constants, have
been fitted to the numerical values obtained. In many cases the
criterionisIAEforloaddisturbances, whichoftengivessystems with
low damping and poor sensitivity. The formulas given often only hold
for a small range of normalized dead times, e.g., 0.2 < τ < 0.6. It
should also be observed that criteria based on setpoint changes can
often bemisleading because it is often not observed that the setpoint
changes are drastically influenced by different setpoint weightings.
ModulusandSymmetricalOptimum
| Modulus |     | Optimum |     | (BO) and | Symmetrical | Optimum | (SO) | are two |
| ------- | --- | ------- | --- | -------- | ----------- | ------- | ---- | ------- |
methods for selecting andtuning controllers thataresimilar inspirit
| toHaalman’smethod. |     |     |     | TheacronymsBOandSOarederived |     |     |     | fromthe |
| ------------------ | --- | --- | --- | ---------------------------- | --- | --- | --- | ------- |
GermanwordsBetragsOptimumandSymmetrischeOptimum.These
methods are based on the idea of finding a controller that makes the
frequency response from setpoint to plant output as close to one as
G(s)
possible for low frequencies. If is the transfer function from the
setpoint to the output, the controller is determined in such a way
that G(0) = 1 and that dn(cid:2)G(iω)(cid:2)/dωn = 0 at ω= 0 for as many n
| as  | possible. | We  | illustrate   | the | idea with | a few examples. |     |     |
| --- | --------- | --- | ------------ | --- | --------- | --------------- | --- | --- |
|     |           | 4.8 | Second-order |     | system    |                 |     |     |
EXAMPLE
| Consider |     | the transfer |     | function |     |     |     |     |
| -------- | --- | ------------ | --- | -------- | --- | --- | --- | --- |
a 2
G(s)=
|     |     |     |     |     | s2+a | s+a |     |     |
| --- | --- | --- | --- | --- | ---- | --- | --- | --- |
|     |     |     |     |     |      | 1 2 |     |     |
which has been chosen so that G(0) = 1. Let us first consider how
the parameters should be chosen in order to get a maximally flat
| frequency |                      | response. |         | We have |       |             |      |     |
| --------- | -------------------- | --------- | ------- | ------- | ----- | ----------- | ---- | --- |
|           |                      |           |         | a2      |       |             | a2   |     |
|           | (cid:2)G(iω)(cid:2)2 |           | =       |         | 2     | =           | 2    |     |
|           |                      |           | a2ω2+(a |         | −ω2)2 | a2+ω2(a2−2a | )+ω4 |     |
|           |                      |           |         |         | 2     |             | 2    |     |
|           |                      |           | √1      |         |       | 2           | 1    |     |
| By        | choosing             | a         | =       | 2a we   | find  |             |      |     |
|           |                      |           | 1       | 2       |       |             |      |     |
a2
|     |     |     |     | (cid:2)G(iω)(cid:2)2 | =   | 2   |     |     |
| --- | --- | --- | --- | -------------------- | --- | --- | --- | --- |
a2+ω4
2
(cid:2)G(iω)(cid:2)
The first three derivatives of will vanish at the origin. The
| transfer |     | function | then | has | the form |     |     |     |
| -------- | --- | -------- | ---- | --- | -------- | --- | --- | --- |
ω2
|     |     |     |     | G(s)= | √   | 0      |     |     |
| --- | --- | --- | --- | ----- | --- | ------ | --- | --- |
|     |     |     |     |       | s2+ | 2ωs+ω2 |     |     |
|     |     |     |     |       |     | 0 0    |     |     |

|     |     |     |     |     | 4.6 Optimization |     | Methods | 167 |
| --- | --- | --- | --- | --- | ---------------- | --- | ------- | --- |
The step response of a system with this transfer function has an
=
overshoot o 4%. The settling time to 2% of the steady state value
is t =6/ω.
| s   | 0   |     |     |     |     |     |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
If the transfer function G in the example is obtained by error
feedback of a system with the loop transfer function G , the loop
BO
| transfer | function | is   |     |      |     |     |     |        |
| -------- | -------- | ---- | --- | ---- | --- | --- | --- | ------ |
|          |          |      |     | G(s) | ω2  |     |     |        |
|          |          | (s)= |     |      | =   | √0  |     | (4.47) |
G
|     |     | BO  | 1−G(s) |     | s(s+ | 2ω) |     |     |
| --- | --- | --- | ------ | --- | ---- | --- | --- | --- |
0
which is the desired loop transfer function for the method called
| modulus        | optimum.     |                            |          |            |            |     |                 |     |
| -------------- | ------------ | -------------------------- | -------- | ---------- | ---------- | --- | --------------- | --- |
| Thecalculation |              | inExample4.8canbeperformed |          |            |            |     | forhigher-order |     |
| systems        | with more    | effort.                    | We       | illustrate | by another |     | example.        |     |
| EXAMPLE        | 4.9          | Third-order                |          | system     |            |     |                 |     |
| Consider       | the transfer |                            | function |            |            |     |                 |     |
a
|            |              | G(s)= |        |           | 3   |     |     |     |
| ---------- | ------------ | ----- | ------ | --------- | --- | --- | --- | --- |
|            |              |       |        | s3+a s2+a | s+a |     |     |     |
|            |              |       |        | 1         | 2   | 3   |     |     |
| After some | calculations |       | we get |           |     |     |     |     |
a
|     | (cid:2)G(iω)(cid:2)= | (cid:25)  |     |     | 3          |     |        |     |
| --- | -------------------- | --------- | --- | --- | ---------- | --- | ------ | --- |
|     |                      | a2+(a2−2a |     | a   | )ω2+(a2−2a |     | )ω4+ω6 |     |
|     |                      | 3         | 2   | 1   | 3          | 1   | 2      |     |
Five derivatives of (cid:2)G(iω)(cid:2) will vanish at ω= 0, if the parameters
are such that a2 = 2a and a2 = 2a a . The transfer function then
|     |     | 1   | 2   | 2   | 1 3 |     |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
becomes
|       |                 | ω3  |     |     |                 | ω3  |     |        |
| ----- | --------------- | --- | --- | --- | --------------- | --- | --- | ------ |
| G(s)= |                 |     | 0   | =   |                 | 0   |     | (4.48) |
|       | s3+2ωs2+2ω2s+ω3 |     |     |     | (s+ω)(s2+ωs+ω2) |     |     |        |
|       |                 | 0   |     |     | 0               |     | 0   |        |
|       |                 |     | 0   | 0   |                 |     | 0   |        |
The step response of a system with this transfer function has an
o=8.1%.
| overshoot |     | The | settling | time | to 2% of | the | steady state | value |
| --------- | --- | --- | -------- | ---- | -------- | --- | ------------ | ----- |
is 9.4/ω. A system with this closed-loop transfer function can be
0
obtained with a system having error feedback and the loop transfer
function
ω3
|     |     |     | (s)= |     | 0   |     |     |     |
| --- | --- | --- | ---- | --- | --- | --- | --- | --- |
G(cid:10)
|     |     |     |     | s(s2+2ω | s+2ω2) |     |     |     |
| --- | --- | --- | --- | ------- | ------ | --- | --- | --- |
|     |     |     |     |         | 0      | 0   |     |     |
(4.48)
| The closed-loop |     | transfer | function |     | can | also | be obtained | from |
| --------------- | --- | -------- | -------- | --- | --- | ---- | ----------- | ---- |
other loop transfer functions if a two-degree of freedom controller is
| used. For | example, | if a | process | with | the transfer | function |     |     |
| --------- | -------- | ---- | ------- | ---- | ------------ | -------- | --- | --- |
ω2
|     |     |     | G (s)= |         | 0   |     |     |     |
| --- | --- | --- | ------ | ------- | --- | --- | --- | --- |
|     |     |     | p      | s(s+2ω) |     |     |     |     |
0

| 168 | Chapter | 4 Controller |     | Design |     |     |     |     |
| --- | ------- | ------------ | --- | ------ | --- | --- | --- | --- |
is controlled by a PI controller having parameters K = 2, T = 2/ω
|     |     |     |     |     |     |     |     | i 0 |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
b=0,
| and | the | loop transfer |     | function | becomes |     |     |     |
| --- | --- | ------------- | --- | -------- | ------- | --- | --- | --- |
ω2(2s+ω)
0
|     |     |     | G   | =        | 0   |     |     | (4.49) |
| --- | --- | --- | --- | -------- | --- | --- | --- | ------ |
|     |     |     | SO  | s2(s+2ω) |     |     |     |        |
0
The symmetric optimum aims at obtaining the loop transfer function
given byEquation (4.49).Notice that the Bode diagram of this trans-
frequencyω=ω.
| fer function | is  | symmetrical |     | around | the |     | This | is the |
| ------------ | --- | ----------- | --- | ------ | --- | --- | ---- | ------ |
0
| motivation | for | the name | symmetrical |     | optimum. |     |     |     |
| ---------- | --- | -------- | ----------- | --- | -------- | --- | --- | --- |
=
If a PI controller with b 1 is used, the transfer function from
| setpoint | to process | output | becomes |     |                 |     |     |     |
| -------- | ---------- | ------ | ------- | --- | --------------- | --- | --- | --- |
|          |            |        | G (s)   |     | (2s+ω)ω2        |     |     |     |
|          | G(s)=      |        | SO      | =   |                 | 0 0 |     |     |
|          |            | 1+G    |         | (s) | (s+ω)(s2+ωs+ω2) |     |     |     |
|          |            |        | SO      |     | 0               | 0   | 0   |     |
Thistransfer function isnotmaximallyflatbecauseofthezerointhe
numerator. This zero will also give a setpoint response with a large
| overshoot, | about   | 43%. |     |        |           |              |     |         |
| ---------- | ------- | ---- | --- | ------ | --------- | ------------ | --- | ------- |
| The        | methods | BO   | and | SO can | be called | loop-shaping |     | methods |
since both methods try to obtain a specific loop transfer function.
Thedesign methods canbedescribed asfollows. Itisfirstestablished
which of the transfer functions, G or G , is most appropriate.
|     |     |     |     |     | BO  | SO  |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
The transfer function of the controller G (s) is then chosen so that
c
| (s) = | (s)G | (s), |     |     |     |     |     |     |
| ----- | ---- | ---- | --- | --- | --- | --- | --- | --- |
G(cid:10) G where G(cid:10) is the chosen loop transfer function.
c p
| We illustrate | the       | methods | with    | the      | following | examples. |     |     |
| ------------- | --------- | ------- | ------- | -------- | --------- | --------- | --- | --- |
| EXAMPLE       | 4.10      | BO      | control |          |           |           |     |     |
| Consider      | a process | with    | the     | transfer | function  |           |     |     |
K
|     |     |     | G   | (s)= | p       |     |     | (4.50) |
| --- | --- | --- | --- | ---- | ------- | --- | --- | ------ |
|     |     |     | p   |      | s(1+sT) |     |     |        |
With a proportional controller the loop transfer function becomes
KK
|     |     |     | G(cid:10) | (s)= | p        |     |     |     |
| --- | --- | --- | --------- | ---- | -------- | --- | --- | --- |
|     |     |     |           |      | s(1+s T) |     |     |     |
Tomakethis transfer function equal to G given byEquation (4.47)
BO
| it must | be required | that |     |     | √   |     |     |     |
| ------- | ----------- | ---- | --- | --- | --- | --- | --- | --- |
2
ω =
0
2T
| The controller |     | gain should | be  | chosen | as  |     |     |     |
| -------------- | --- | ----------- | --- | ------ | --- | --- | --- | --- |
√
ω
|     |     |     |     |     | 2 1  |     |     |     |
| --- | --- | --- | --- | --- | ---- | --- | --- | --- |
|     |     |     | K = | 0   | =    |     |     |     |
|     |     |     |     | 2K  | p 2K | p T |     |     |

4.6 Optimization Methods 169
EXAMPLE 4.11 SO control
Consider aprocess withthesametransfer function asintheprevious
example (Equation (4.50)). With a PI controller having the transfer
function
K(1+sT)
G (s)= i
c
sT
i
we obtain the loop transfer function
K K(1+sT)
G(cid:10) (s)=
s2
p
T(1+sT
i
)
i
This is identical to G if we choose
SO
1
K =
2K T
p
T =4T
i
To obtain the transfer function given by Equation (4.48) between
setpoint and process output, the controller should have the input-
output relation
(cid:5) (cid:1) (cid:6)
1 t
u(t)= K −y(t)+ (y (s)−y(s))ds
sp
T
i
Thecoefficient binthestandardcontroller thusshould besettozero.
A Design Procedure
A systematic design procedure can be based on the methods BO and
SO. The design method consists of two steps. In the first step the
process transfer function is simplified to one of the following forms
K
G (s)= p (4.51)
1 1+sT
K
G (s)= p , T >T (4.52)
2 (1+sT )(1+sT ) 1 2
1 2
K
G (s)= p , T >T >T (4.53)
3 (1+sT )(1+sT )(1+sT ) 1 2 3
1 2 3
K
G (s)= p (4.54)
4 s(1+sT)
K
G (s)= p , T > T (4.55)
5 s(1+sT )(1+sT ) 1 2
1 2
Processpolesmaybecanceledbycontrollerzerostoobtainthedesired
loop transfer function. A slow pole may be approximated by an inte-
grator;fastpoles maybelumpedtogether asdiscussed inSection 2.9.

170 Chapter 4 ControllerDesign
The rule of thumb given in the original papers on the method is that
time constants such thatωT <0.25 can be regarded as integrators.
0
The controller is derived in the same way as in Examples 4.10
and 4.11 by choosing parameters so that the loop transfer function
matches either G or G . By doing this we obtain the results
BO SO
summarized in Table 4.6.Notice, for example, that Example 4.10and
4.11 correspond to the entries Process G in the table. It is natural
4
to view the smallest time constant as an approximation of neglected
dynamicsintheprocess.Itisinterestingtoobservethatitisthistime
constant that determines the bandwidth of the closed-loop system.
The setpoint response for the BO method is excellent. Notice
that it is necessary to use a controller with a two-degree-of-freedom
structure or a prefilter to avoid a high overshoot for the SO method.
Notice that process poles are canceled in the cases marked C1 or C2
in Table 4.6. The response to load disturbances will be poor if the
canceled pole is slow compared to the closed-loop dynamics, which is
characterized by ω in Table 4.6.
0
These design principles can be extended to processes other than
those listed in the table.
EXAMPLE 4.12 Application of BO and SO
Consider a process with the transfer function
1
G(s)= (4.56)
(1+s)(1+0.2s)(1+0.05s)(1+0.01s)
Since this transfer function is of fourth order, the design procedure
cannot be applied directly. We show how different controllers are ob-
tained depending on the approximations made. The performance of
theclosed-loop system depends ontheapproximation. Weuseparam-
eter ω as a crude measure of performance.
0
If a controller with low performance is acceptable, the process
(4.56) can be approximated with
1
G(s)= (4.57)
1+1.26s
The approximation has a phase error less than 10 ○ for ω≤ 1.12. It
follows from Table 4.6 that the system (4.57) can be controlled with
an integrating controller with
K 0.5
k = = =0.4
i
T 1.26
i
This gives a closed-loop system withω =0.55.
0
A closed-loop system with better performance is obtained if the
transfer function (4.56) is approximated with
1
G(s)= (4.58)
(1+s)(1+0.26s)

4.6 Optimization Methods 171
Table 4.6 Controller parameters obtained with the BO and SO
methods.EntryPgivestheprocesstransferfunction,entryCgives
the controller structure, and entry M tells whether the BO or SO
method is used. In the entry Remark, A1 means that 1+sT is
1
approximated by sT and Ci means that the time constant T is
1 i
canceled.
P C M Remark KK T T ω b c
p i d 0
0.7
G I BO 0.5 T
1 T
T 0.7
G P BO A1 1 1
2 2T T
2 2
T 0.7
G PI BO C1 1 T 1
2 2T 1 T
2 2
T 0.5
G PI SO A1 1 4T 0
2 2T 2 T
2 2
T 0.7
G PD BO A1, C2 1 T 1 1
3 2T 2 T
3 3
T +T T T 0.7
G PID BO C1, C2 1 2 T +T 1 2 1 1
3 2T 1 2 T +T T
3 1 2 3
T (T +4T ) 4T T 0.5 T
G PID SO A1, C2 1 2 3 T +4T 2 3 2 0
3 8T2 2 3 T +4T T T +4T
3 2 3 3 2 3
1 0.7
G P BO 1
4 2T T
1 0.5
G PI SO 4T 0
4 2T T
1 0.7
G PD BO C1 T 1 1
5 2T 1 T
2 2
T 0.5
G PD SO A1 1 4T 1 0
5 8T2 2 T
2 2
T +4T 4T T 0.5 T
G PID SO C1 1 2 T +4T 1 2 1 0
5 8T2 1 2 T +4T T T +4T
2 1 2 2 1 2
The slowest time constant is thus kept and the remaining time con-
stantsareapproximatedbylumpingtheirtimeconstants.Theapprox-
imation has a phase error less than 10 ○ forω≤5.15. A PI controller
can be designed using the BO method. The parameters K = 1.92
and T = 1 are obtained from Table 4.6. The closed-loop system has
i
ω =2.7.
0
If the transfer function is approximated as
1
G(s)= (4.59)
(1+s)(1+0.2s)(1+0.06s)
the approximation has a phase error less than 10 ○ for ω≤26.6. The

| 172 | Chapter | 4 Controller | Design |     |     |     |     |
| --- | ------- | ------------ | ------ | --- | --- | --- | --- |
| 4   |         |              |        | 4   |     |     |     |
|     | 3       |              |        |     | 3 2 |     |     |
1
2
|     | 1   |     |     |     |     | 1   |     |
| --- | --- | --- | --- | --- | --- | --- | --- |
0
| 0   |     | 5   |     | 10  |     | 15  | 20  |
| --- | --- | --- | --- | --- | --- | --- | --- |
5
0
| 0   |     | 5   |     | 10  |     | 15  | 20  |
| --- | --- | --- | --- | --- | --- | --- | --- |
Figure 4.22 Simulation of the closed-loop system obtained with
different controllers designed by the BO and SO methods given in
| Table4.7.Theupperdiagramshowssetpoint |     |               |       |               |     | y sp andprocessoutput |     |
| ------------------------------------- | --- | ------------- | ----- | ------------- | --- | --------------------- | --- |
| y, and                                | the | lower diagram | shows | controlsignal |     | u.                    |     |
BOmethodcanbeusedalsointhiscase.Table4.6givesthecontroller
|            |     | =10, | =1.2,and |     | =0.17.The |            |           |
| ---------- | --- | ---- | -------- | --- | --------- | ---------- | --------- |
| parameters | K   | T    | i        | T d |           | controller | structure |
is defined by the parameters b=1 and c=1. This controller gives a
|             |        | withω | =11.7. |     |     |     |     |
| ----------- | ------ | ----- | ------ | --- | --- | --- | --- |
| closed-loop | system |       | 0      |     |     |     |     |
(4.59).
| The | method | SO can | also | be applied | to  | the system | Table |
| --- | ------ | ------ | ---- | ---------- | --- | ---------- | ----- |
4.6 gives the controller parameters K = 15.3, T = 0.44, T = 0.11,
|         |     |           |            |     |      | i     | d   |
| ------- | --- | --------- | ---------- | --- | ---- | ----- | --- |
| b=0.45. |     |           |            |     | getω | =8.3. |     |
| and     |     | For these | parameters | we  |      | 0     |     |
Thus, we note that controllers with different properties can be
obtained by approximating the transfer function in different ways. A
summaryofthepropertiesoftheclosed-loopsystemsobtainedisgiven
inTable4.7,whereIAEreferstotheloaddisturbanceresponse.Notice
that Controller 2 cancels a process pole with time constant 1 s, and
that Controller 3 cancels process poles with time constants 1 s and
0.25 s. This explains why the IAE drops drastically for Controller 4,
which does not cancel any process poles. Controller 4 actually has a
| lower bandwidth |     | ω than | Controller |     | 3.  |     |     |
| --------------- | --- | ------ | ---------- | --- | --- | --- | --- |
0
Asimulation of the different controllers isshown in Figure 4.22.
Summary
In this section we discussed using optimization methods to arrive at
desirablelooptransferfunctions.ThemethodbyHaalmanisdesigned
| for systems | having | dead | time. | The | methods | BO and SO | apply to |
| ----------- | ------ | ---- | ----- | --- | ------- | --------- | -------- |
systems without dead time. Small dead times can be dealt with by
approximation. An interesting feature of both BO and SO is that
approximationsareusedtoobtainsimplelowordertransferfunctions.
There are possibilities to combine the approaches. A drawback with

4.7 Pole Placement 173
Table 4.7 Resultsobtainedwithdifferentcontrollersdesignedby
theBOandSOmethodsinExample4.12.Thefrequencyω defines
m
the upper limit when thephase error isless than10%.
Controller K T T k b c ω ω IAE
i d i 0 m
1 0.4 0.55 1.12 2.7
2 1.92 1 0.52 1 2.7 5.15 0.52
3 10 1.2 0.17 8.3 1 1 11.7 26.6 0.12
4 15.3 0.44 0.11 35 0.45 0 8.3 26.6 0.029
all design methods of this type is that process poles are canceled.
Thismayleadtopoorattenuation ofloaddisturbances ifthecanceled
polesareexcitedbydisturbances andiftheyareslowcomparedtothe
dominant closed-loop poles.
4.7 Pole Placement
This section presents design methods that are based on knowledge
of the process transfer function. The pole placement design method
simply attempts to find a controller that gives desired closed-loop
poles. We illustrate the method by two simple examples.
EXAMPLE 4.13 PI control of a first-order system
Suppose thattheprocesscanbedescribed bythefollowing first-order
model:
K
G (s)= p (4.60)
p 1+sT
which has only two parameters, the process gain (K ) and the time
p
constant (T). By controlling this process with the PI controller,
(cid:20) (cid:21)
1
G (s)= K 1+
c
sT
i
a second-order closed-loop system is obtained:
G G
G(s)= p c
1+G G
c p
Thetwoclosed-looppolescanbechosenarbitrarilybyasuitablechoice
of the gain (K) and the integral time (T) of the controller. This is
i
seen as follows. The poles are given by the characteristic equation,
1+G G =0
c p

174 Chapter 4 Controller Design
The characteristic equation becomes
1+ K K K K
s2+s p + p =0
T TT
i
Now suppose that the desired closed-loop poles are characterized by
their relative damping (ζ) and their frequency (ω). The desired
0
characteristic equation then becomes
s2+2ζωs+ω2 =0
0 0
Making the coefficients of these two characteristic equations equal
gives two equations for determining K and T:
i
K K
ω2 = p
0 TT
i
1+ K K
2ζω = p
0 T
Solving these for the controller parameters, we get
2ζωT −1
K = 0
K
p
2ζωT −1
T = 0
i ω2T
0
Notice that the transfer function from setpoint to process output has
a zero at s = −1/(bT). To avoid excessive overshoot in the setpoint
i
response, parameter bshould be chosen so that the zero is to the left
ofthedominantclosed-loop poles.Areasonablevalueisb=1/(ωT),
0 i
which places the zero at s = −ω. Notice also that in order to have
0
positivecontrollergainsitisnecessarythatthechosenfrequency(ω)
0
is larger than 1/(2ζT).It also follows that ifω is large, the integral
0
time T is given by
i
2ζ
T (cid:9)
i ω
0
andis,thus, independent of theprocess dynamics forlargeω.There
0
is no formal upper bound to the bandwidth. However, a simplified
model like Equation (4.60) will not hold for large frequencies. The
upper bound onthebandwidth isdetermined, therefore, bythevalid-
ity of the model.
EXAMPLE 4.14 System with two real poles
Suppose that the process is characterized by the second-order model
K
G = p (4.61)
p (1+sT )(1+sT )
1 2

4.7 Pole Placement 175
This model has three parameters. By using a PID controller, which
also has three parameters, it is possible toarbitrarily place the three
poles of the closed-loop system. The transfer function of the PID
controller can be written as
K(1+sT +s2TT )
G (s)= i i d
c sT
i
The characteristic equation of the closed-loop system becomes
(cid:20) (cid:21) (cid:20) (cid:21)
1 1 K KT 1 K K K K
s3+s2 + + p d +s + p + p =0 (4.62)
T T T T T T T T T T T
i 2 1 2 1 2 1 2 1 2 i
A suitable closed-loop characteristic equation of a third-order system
is
(s+αω)(s2+2ζωs+ω2)=0 (4.63)
0 0 0
which contains two dominant poles with relative damping (ζ) and
frequency (ω), and a real pole located in −αω. Identifying the
0 0
coefficients of equal powers of s in the Equations (4.62) and (4.63)
gives
1 1 K KT
+ + p d =ω(α+2ζ)
0
T T T T
i 2 1 2
1 K K
+ p =ω2(1+2ζω)
T T T T 0 0
1 2 1 2
K K
p =αω3
T T T 0
1 2 i
Solving these equations gives the following controller parameters
T T ω2(1+2αζ)−1
K = 1 2 0
K
p
T T ω2(1+2αζ)−1
T = 1 2 0
i T T αω3
1 2 0
T T ω(α+2ζ)−T −T
T = 1 2 0 1 2
d T T ω2(1+2αζ)−1
1 2 0
Provided that c = 0, the transfer function from setpoint to process
output has one zero at s=−1/(bT). To avoid excessive overshoot in
i
the setpoint response, parameter b can be chosen so that this zero
cancels the pole at s=−αω. This gives
0
1 ω2T T
b= = 0 1 2
αωT ω2T T (1+2αζ)−1
0 i 0 1 2
Also, notice that pure PI control is obtained for
T +T
ω =ω = 1 2
0 c (α+2ζ)T T
1 2

176 Chapter 4 Controller Design
The choice of ω may be critical. The derivative time is negative
0
for ω < ω. Thus, the frequency (ω) gives a lower bound to the
0 c c
bandwidth. The gain increases rapidly with ω. The upper bound
0
to the bandwidth is given by the validity of the simplified model
(Equation 4.61).
The methods BO and SO, discussed in the previous section, can
clearlybeinterpreted aspole placement methods. Thedesired closed-
loop characteristic polynomial is
√
A (s)= s2+ 2ωs+ω2
BO 0 0
for the modulus optimum and
A (s)=(s+ω)(s2+ωs+ω2)
SO 0 0 0
for the symmetrical optimum.
The calculations in Example 4.14 can be done for any linear sys-
tem. The algebraic formulas obtained, however, may be quite compli-
cated. Another useful example follows.
EXAMPLE 4.15 Second-order systems with a zero
Suppose that the process is characterized by the second-order model
b s+b
G = 1 2 (4.64)
p s2+a s+a
1 2
This model has four parameters. It has two poles that may be real
or complex, and it has one zero. The model given by Equation (4.64)
captures manyprocesses, oscillatory systems, andsystems withright
half-plane zeros. The right half-plane zerocan also be used asan ap-
proximation ofatime delay. Weassume thattheprocess iscontrolled
by a PID controller parameterized as
k
G (s)= k+ i +k s (4.65)
c d
s
The closed-loop system is of third order and has the characteristic
equation
s(s2+a s+a )+(b s+b )(k s2+ks+k)=0 (4.66)
1 2 1 2 d i
A suitable closed-loop characteristic equation of a third-order system
is
(s+αω)(s2+2ζωs+ω2)=0 (4.67)
0 0 0
Equating coefficients of equal power in s in Equations (4.66) and
(4.67) gives the following equations:
a +b k +b k=(αω +2ζω)(1+b k )
1 2 d 1 0 0 1 d
a +b k+b k =(1+2αζ)ω2(1+b k )
2 2 1 i 0 1 d
b k =αω3(1+b k )
2 i 0 1 d

4.7 Pole Placement 177
This is a set of linear equations in the controller parameters. The
solution is straightforward but tedious and is given by
a b2−a b b (α+2ζ)ω −(b −a b )(b (1+2αζ)ω2+αb ω3)
k= 2 2 2 1 2 0 2 1 1 2 0 1 0
b3−b b2(α+2ζ)ω +b2b (1+2αζ)ω2−αb3ω3
2 1 2 0 1 2 0 1 0
(−a b b +a b2+b2)αω3
k = 1 1 2 2 1 2 0
i b3−b b2(α+2ζ)ω +b2b (1+2αζ)ω2−αb3ω3
2 1 2 0 1 2 0 1 0
−a b2+a b b +b2(α+2ζ)ω −b b ω2(1+2αζ)+b2αω3
k = 1 2 2 1 2 2 0 1 2 0 1 0
d b3−b b2(α+2ζ)ω +b2b (1+2αζ)ω2−αb3ω3
2 1 2 0 1 2 0 1 0
These formulas are quite useful because many processes can be ap-
proximately described by the transfer function given by Equation
(4.64).
The formulas given in Example 4.15 are particularly useful in
cases when we are “stretching” the PID controller to extreme situa-
tions.Thestandardtuningruleswilltypicallynotworkinthesecases.
Typical examples are systems with zeros in the right half-plane and
systems with poorly damped oscillatory modes. To illustrate this we
will consider an example.
EXAMPLE 4.16 A difficult process
Consider a system with the transfer function
1−s
G(s)=
s2+1
Thissystemhasonerighthalf-planezeroandtwoundampedcomplex
poles. None of the standard methods for tuning PID controllers work
well for this system. To apply the pole-placement method we require
that the closed-loop system has the characteristic equation
s3+2s2+2s+1=0
The formulas in Example 4.15 give a controller with the parameters
k = 0, k = 1/3, and k = 2/3. This can also be verified with a
i d
simple calculation. Notice that the proporti√onal gain is zero and that
the controller has two complex zeros at ±i 2. Such a controller can
only be implemented with a PID controller having the parallel form.
Compare with section 3.4.
TheGeneralCase
The calculations in the examples can be extended to general linear
systems.Theyare,however,morecomplicated.Itisnecessarytospec-

178 Chapter 4 Controller Design
ify more closed-loop poles. Some pole patterns that are used are But-
terworth configurations, where the roots of the characteristic polyno-
mials are placed symmetrically in a circle, and the Bessel configura-
tions, which correspond to filters that attempt to preserve the shape
of the wave form. The order of the controllers also increases with the
complexity of the model. To obtain PID controllers it is necessary to
restrictthemodelstofirst-orsecond-ordersystems.Formorecomplex
processes, it is, therefore, necessary to make approximations so that
a process model in the form of a rational function of first or second
orderisobtained. Several waystoperform these approximations aree
given in Chapter 2. We illustrate the procedure with an example.
EXAMPLE 4.17 Pole placement with an approximate model
Consider a process described by the transfer function
1
G (s)= (4.68)
p (1+s)(1+0.2s)(1+0.05s)(1+0.01s)
This process has four lags with time constants 1, 0.2, 0.05, and 0.01.
The approximations canbe done in several different ways. If the con-
trol requirements are not too severe, we can attempt to approximate
the transfer function by
1
G (s)=
p 1+1.26s
where the time constant is the average residence time of the system.
As discussed in Section 2.9, this approximation is good at low fre-
○
quencies. The phase error is less than 10 for frequencies below 1.1
rad/s.Designing aPIcontroller withthepoleplacementmethodwith
ζ=0.5, the following controller parameters are obtained
K =1.26ω −1
0
1.26ω −1
T = 0
i 1.26ω2
0
1.26ω
b= 0
1.26ω −1
0
where b is chosen so that the zero becomes s = −ω. If the process
0
model would be correct, the phase margin withζ=0.5would be 50 ○ .
Becauseoftheapproximations made,thephasemarginwillbeless.It
will decrease withω. Forω =1 the phase margin isϕ =42 ○ .
0 0 m
Another way of applying pole placement design is given in the
next example.

4.8 DominantPole Design 179
EXAMPLE 4.18 Application to an approximate model
Consider the same process model as in the previous example (Equa-
tion 4.68). Approximate the transfer function by
1
G (s)=
p (1+s)(1+0.26s)
It is obtained by keeping the longest time constant and approximat-
ing the three shorter time constants with their sum. The phase error
is less than 10 ○ for frequencies below 5.1 rad/s. By making an ap-
proximation of the process model that is valid for higher frequencies
than in the previous example, we can thus design a faster controller.
Ifζ=0.5 andα=1 are chosen in Equation (4.67), the design calcu-
lations in Example 4.14 gives the following PID parameters:
K =0.52ω2−1
0
0.52ω2−1
T = 0
i 0.26ω3
0
0.52ω −1.26
T = 0
d 0.52ω2−1
0
0.26ω2
b= 0
0.52ω2−1
0
In this case, pure PI control is obtained forω =2.4. The derivative
0
gain becomes negative for lower bandwidths. The approximation ne-
glects the time constant 0.05. If the neglected dynamics are required
to give a phase error of, at most, 0.3 rad (17 deg) at the bandwidth,
ω < 6 rad/s can be obtained. In Figure 4.23, the behavior of the
0
control is demonstrated for ω =4,5, and 6.
0
The specification of the desired closed-loop bandwidth is crucial,
since the controller gain increases rapidly with the specified band-
width.Itisalsocrucialtoknowthefrequency rangewherethemodel
is valid. Alternatively, an upper bound to the controller gain can be
used to limit the bandwidth. Notice the effect of changing the design
frequency (ω). The system with ω = 6 responds faster and has a
0 0
smaller error when subjected to load disturbances. The design will
not work well whenω is increased above 8.
0
4.8 Dominant Pole Design
In pole placement design it is attempted to assign all closed-loop
poles. One difficulty with the method is that complex models lead to
complexcontrollers.Inthissectionwewillintroducearelatedmethod

| 180 Chapter | 4   | Controller | Design |     |     |     |     |
| ----------- | --- | ---------- | ------ | --- | --- | --- | --- |
ω =6
0
|     |     |     |     | ω   | =6  |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- |
0
1
| ω =5 |     |     |     |     | ω    | =5  |     |
| ---- | --- | --- | --- | --- | ---- | --- | --- |
| 0    |     |     |     |     | 0    |     |     |
| ω =4 |     |     |     |     | ω =4 |     |     |
| 0    |     |     |     |     | 0    |     |     |
0
| 0   |     | 2   |     | 4   |     | 6   | 8   |
| --- | --- | --- | --- | --- | --- | --- | --- |
5
−5
| 0   |     | 2   |     | 4   |     | 6   | 8   |
| --- | --- | --- | --- | --- | --- | --- | --- |
Figure 4.23 Setpoint and load disturbance responses of the pro-
cess(Equation4.68)controlledbyaPIDcontrollertunedaccording
| toExample4.18.Theresponsesforω |     |     |     |     | =4,5,and6areshown.The |     |     |
| ------------------------------ | --- | --- | --- | --- | --------------------- | --- | --- |
0
=
| upper diagram |     | shows | setpoint | y   | 1 and | process output | y, and |
| ------------- | --- | ----- | -------- | --- | ----- | -------------- | ------ |
sp
| the lower | diagram | shows | controlsignal |     | u.  |     |     |
| --------- | ------- | ----- | ------------- | --- | --- | --- | --- |
where it is attempted to assign only a few poles. With this method
it is possible to design simple controllers for complex processes. The
method is based on the assumption that the transfer function of the
process is known. The idea of positioning a few closed-loop poles was
used in several of the early papers on PID control. A complete design
methodology based on this idea is developed in this section. The
method makes it possible to consider many different specifications.
Itis also possible todesign controllers of many different types andto
| compare their | performances. |     |     |     |     |     |     |
| ------------- | ------------- | --- | --- | --- | --- | --- | --- |
TheCohen-CoonMethod
| The Cohen-Coon |     | method | is based | on  | the process | model |     |
| -------------- | --- | ------ | -------- | --- | ----------- | ----- | --- |
K
|     |     |     | =   | p   | −sL |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- |
|     |     |     | G p |     | e   |     |     |
1+sT
Themaindesigncriterionisrejectionofloaddisturbances.Itattempts
toposition dominant poles that give a quarter amplitude decay ratio.
For P and PD controllers the poles are adjusted to give maximum
gain, subject to the constraint on the decay ratio. This minimizes
the steady state error due to load disturbances. For PI and PID
|     |     |     | =   | K/T |     |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- |
control the integral gain k i i is maximized. This corresponds
to minimization of IE, the integral error due to a unit step load
disturbance. ForPID controllers three closed-loop poles areassigned;
two poles are complex, and the third real pole is positioned at the
same distance from the origin as the other poles. The pole pattern is

4.8 Dominant Pole Design 181
Table 4.8 Controller parametersfrom theCohen-Coon method.
Controller K T T
i d
(cid:5) (cid:6)
1 0.35τ
P 1+
a 1−τ
(cid:5) (cid:6)
0.9 0.92τ 3.3−3.0τ
PI 1+ L
a 1−τ 1+1.2τ
(cid:5) (cid:6)
1.24 0.13τ 0.27−0.36τ
PD 1+ L
a 1−τ 1−0.87τ
(cid:5) (cid:6)
1.35 0.18τ 2.5−2.0τ 0.37−0.37τ
PID 1+ L L
a 1−τ 1−0.39τ 1−0.81τ
adjusted to give quarter amplitude decay ratio, and the distance of
the poles to the origin are adjusted to minimize IE.
Since the process is characterized by three parameters (K , L,
p
and T), it is possible to give tuning formulas where controller pa-
rameters are expressed in terms of these parameters. Such formulas
were derived by Cohen and Coon based on analytical and numerical
computations. The formulas are given in Table 4.8. The parameters
a = K L/T andτ= L/(L+T) are used in the table. A comparison
p
withTable4.1showsthatthecontroller parametersareclosetothose
obtainedbytheZiegler-Nichols stepresponsemethodforsmallτ.Also
notice that the integral time decreases for increasing τwhich is de-
sirable as was found in Section 4.3.The method does suffer, however,
fromthedecayratiobeingtoosmall,whichmeansthattheclosed-loop
systems obtained have low damping and high sensitivity.
IntegratingControl
Consider a process with transfer function G (s) controlled by an
p
integrating controller. Such a controller has the transfer function
k
G (s)= i
c s
The closed-loop poles are given by
G (s)
1+k p =0
i
s
Since the controller has one adjustable parameter, it is possible to
assign one pole. To obtain a pole at s=−a the controller parameter
should be chosen as
a
k = (4.69)
i G (−a)
p

| 182 | Chapter | 4 Controller |     | Design |     |     |     |     |
| --- | ------- | ------------ | --- | ------ | --- | --- | --- | --- |
So far parameter a is a design parameter. To find suitable ways of
choosing a it is observed that gain k i is small when a is small. This
means that the closed-loop poles are the design pole at s=−a and a
number of poles thatareclose totheopen-loop poles. Iftheopen-loop
systemisstable, thedesign poleisthustheslowestpole.Increasing a
gives a faster closed-loop system. Notice that k becomes zero when a
i
IE=1/k,
is equal to a real process pole. Since i the integrated error
will also decrease with increasing a. One possible way to choose a is
| to use a | value | that | maximizes |     | k.  |     |     |     |
| -------- | ----- | ---- | --------- | --- | --- | --- | --- | --- |
i
PIControl
A PI controller has two parameters. Consequently, it is necessary to
(s)and
| assigntwopoles. |            | Consider |               | aprocess | withtransfer |     | function | G p |
| --------------- | ---------- | -------- | ------------- | -------- | ------------ | --- | -------- | --- |
| let the         | controller | be       | parameterized |          | as           |     |          |     |
k
|     |     |     |     | G (s)= | k+  | i   |     |     |
| --- | --- | --- | --- | ------ | --- | --- | --- | --- |
c
s
| The closed-loop |     | characteristic |     | equation |         | is  |     |     |
| --------------- | --- | -------------- | --- | -------- | ------- | --- | --- | --- |
|                 |     |                |     | (cid:2)  | (cid:3) |     |     |     |
k
|     |     |     | 1+  | k+  | i (s)=0 |     |     | (4.70) |
| --- | --- | --- | --- | --- | ------- | --- | --- | ------ |
G
|         |         |               |          |         | s p        |                 |     |     |
| ------- | ------- | ------------- | -------- | ------- | ---------- | --------------- | --- | --- |
| Require | that    | this equation |          | have    | roots at   |                 |     |     |
|         | (cid:5) |               | (cid:25) | (cid:6) |            |                 |     |     |
| p       | =ω      | −ζ ±i         | 1−ζ2     |         | =ω ei(π±γ) | =ω(−cosγ±isinγ) |     |     |
| 1,2     | 0       | 0             |          | 0       | 0          |                 | 0   |     |
(4.71)
| whereγ=arccosζ. |     |     | This | gives |     |     |     |     |
| --------------- | --- | --- | ---- | ----- | --- | --- | --- | --- |
0
|     |     |     |     | (cid:20) | k (cid:21) |     |     |     |
| --- | --- | --- | --- | -------- | ---------- | --- | --- | --- |
|     |     |     | 1+  | k+       | i (p       | )=0 |     |     |
|     |     |     |     |          | G p        | 1   |     |     |
p
1
| Introduce | a(ω) | andφ(ω)  |         | defined  | as      |        |     |     |
| --------- | ---- | -------- | ------- | -------- | ------- | ------ | --- | --- |
|           |      | 0        | (cid:2) | 0        | (cid:3) |        |     |     |
|           |      |          |         | ei(π−γ)  |         | )eiφ(ω | )   |     |
|           |      |          | G       | ω        | = a(ω   |        | 0   |     |
|           |      |          | p       | 0        |         | 0      |     |     |
|           |      | (cid:20) |         | (cid:21) |         |        |     |     |
Notice that G ω ei(π−γ) represents the value(cid:20)s of the tr(cid:21)ansfer func-
p 0
|          |         | ei(π−γ) | Whenγ=π/2, |     |           |     | ω ei(π−γ) | = (iω), |
| -------- | ------- | ------- | ---------- | --- | --------- | --- | --------- | ------- |
| tion on  | the ray |         | .          |     | then      | G   |           | G       |
|          |         |         |            |     |           | p   | 0         | p 0     |
| which is | the     | normal  | frequency  |     | response. |     |           |         |
(4.70)
| Equation |     |     | can      | be written | as       |     |     |     |
| -------- | --- | --- | -------- | ---------- | -------- | --- | --- | --- |
|          |     |     | (cid:20) |            | (cid:21) |     |     |     |
k
|     |     | 1+  | k+  |       | i a(ω | )eiφ(ω | 0 ) =0 |     |
| --- | --- | --- | --- | ----- | ----- | ------ | ------ | --- |
|     |     |     |     | ω ei( | π−γ)  | 0      |        |     |
0
This equation, which is linear in k and k, i has the solution
sin(φ(ω)+γ)
0
|     |     |     |     | k=− |     |     |     | (4.72) |
| --- | --- | --- | --- | --- | --- | --- | --- | ------ |
a(ω)sinγ
0
|     |     |     |     | ω   | sinφ(ω)  |     |     |        |
| --- | --- | --- | --- | --- | -------- | --- | --- | ------ |
|     |     |     | k   | =−  | 0        | 0   |     | (4.73) |
|     |     |     |     | i   | a(ω)sinγ |     |     |        |
0

|     |     |     |     |     | 4.8 Dominant |     | Pole Design | 183 |
| --- | --- | --- | --- | --- | ------------ | --- | ----------- | --- |
Notice that φ(ω) is zero for ω = 0 and typically negative as ω
|     | 0   |     |     | 0   |     |     |     | 0   |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
increases. This implies thattheproportional gainisnegative andthe
| integral | gainpositive | butsmallforsmallω.Whenω |     |     |     |     | increases | both |
| -------- | ------------ | ----------------------- | --- | --- | --- | --- | --------- | ---- |
|          |              |                         |     |     |     | 0   | 0         |      |
kandk willincreaseinitially.Forlargervaluesofω bothparameters
| i   |     |     |     |     |     |     | 0   |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
will decrease. Requiring that both parameters are positive, we find
| thatω | must be selected |     | so that |     |     |     |     |     |
| ----- | ---------------- | --- | ------- | --- | --- | --- | --- | --- |
0
γ<−φ(ω)<π
0
| The integral | time             | of the | controller | is          |         |     |     |        |
| ------------ | ---------------- | ------ | ---------- | ----------- | ------- | --- | --- | ------ |
|              |                  |        | k          | sin(φ(ω)+γ) |         |     |     |        |
|              |                  | T      | =          | =           | 0       |     |     | (4.74) |
|              |                  | i      |            | ω           | sinφ(ω) |     |     |        |
|              |                  |        | k i        | 0           |         | 0   |     |        |
| Notice that  | T is independent |        |            | of a(ω).    |         |     |     |        |
|              | i                |        |            |             | 0       |     |     |        |
PDControl
A PD controller has two parameters. To obtain these it is necessary
to specify two closed-loop poles. The controller is assumed to be pa-
| rameterized | as          |       |      |         |          |         |     |     |
| ----------- | ----------- | ----- | ---- | ------- | -------- | ------- | --- | --- |
|             |             |       | (s)= | k+k     |          |         |     |     |
|             |             |       | G c  |         | d s      |         |     |     |
| Specifying  | the desired | poles | as   |         |          |         |     |     |
|             |             |       |      | (cid:2) | (cid:25) | (cid:3) |     |     |
|             |             | p     | =ω   | −ζ ±i   | 1−ζ2     |         |     |     |
|             |             | 1,2   | 0    | 0       |          | 0       |     |     |
and proceeding as in the derivation of the PI controller we find
sin(φ(ω)−γ)
|     |     |     | k=  |     | 0   |     |     | (4.75) |
| --- | --- | --- | --- | --- | --- | --- | --- | ------ |
a(ω)sinγ
0
sinφ(ω)
0
|     |     |     | k = |     |     |     |     | (4.76) |
| --- | --- | --- | --- | --- | --- | --- | --- | ------ |
d ωa(ω)sinγ
0 0
Note that the expressions of k and k for PD controllers are similar
d
| to those | of PI controllers. |     |     |     |     |     |     |     |
| -------- | ------------------ | --- | --- | --- | --- | --- | --- | --- |
PIDControl
Now we consider PID control. For simplicity, it is assumed that the
| controller | is parameterized |     | as   |     |        |     |     |        |
| ---------- | ---------------- | --- | ---- | --- | ------ | --- | --- | ------ |
|            |                  |     | (s)= | k+  | k i +k |     |     | (4.77) |
|            |                  |     | G    |     |        | s   |     |        |
|            |                  |     | c    |     | s      | d   |     |        |
Modifications in the setpoint weighting and limitation of the deriva-
tivegainaretakencareoflater.Sincethecontroller hasthreeparam-
eters, it is necessary to specify three poles of the closed-loop system.

184 Chapter 4 Controller Design
We choose them as
(cid:5) (cid:25) (cid:6)
p =ω −ζ ±i 1−ζ2 (4.78)
1,2 0 0 0
p =−αω. (4.79)
3 0 0
Introduce the quantities a(ω), b(ω), andφ(ω) defined by
0 0 0
(cid:2) (cid:3)
G p ω 0 ei(π−γ) = a(ω 0 )eiφ(ω 0 )
G (−αω)=−b(ω)
p 0 0
The condition that p ,p , and p are roots of
1 2 3
1+G (s)G (s)=0 (4.80)
p c
gives the conditions
α2b(ω)sin(γ+φ)+b(ω)sin(γ−φ)+α a(ω)sin2γ
k=− 0 0 0 0 0
a(ω)b(ω)(α2−2α cosγ+1)sinγ
0 0 0 0
a(ω)sinγ+b(ω)(sin(γ−φ)+α sinφ)
k =−αω 0 0 0
i 0 0 a(ω)b(ω)(α2−2α cosγ+1)sinγ
0 0 0 0
α a(ω)sinγ+b(ω)(α sin(γ+φ)−sinφ)
k =− 0 0 0 0
d ωa(ω)b(ω)(α2−2α cosγ+1)sinγ
0 0 0 0 0
PID Controller Based on PI Controller
Another waytoobtain aPIDcontroller istostartwithaPIcontroller
and to add derivative action. This can be done as follows. Assume
that the controller
k
G (s)= k+ i +k s (4.81)
c d
s
is used and that it is desired to have two closed-loop poles in
(cid:5) (cid:25) (cid:6)
p =ω −ζ ±i 1−ζ2
1,2 0 0 0
The value of the controller transfer function at these poles can be
written as
k
G (p )= k+ i e −i(π−γ)+k ω ei(π−γ)
c 1 ω d 0
(cid:2)0 (cid:3) (cid:2) (cid:3)
k k
= k− k ω + i cosγ+i k ω − i sinγ
d 0 ω d 0 ω
0 0
This implies that
k= k (cid:8)+2k ζω
d 0 0
k = k (cid:8) +k ω2
i i d 0

4.8 Dominant Pole Design 185
(cid:8) (cid:8)
where k and k arethecontroller parameters for apure PIcontroller
i
givenbyEquations(4.72)and(4.73).Usingthisparameterizationthe
PID controller can be written
(cid:20) (cid:21)
k
G (s)= G (cid:8)(s)+ d s2+2ζωs+ω2 (4.82)
c c s 0 0 0
where G (cid:8)(s) is a pure PI controller, i.e., G (s) with k =0. The task
c c d
is now to choose ζ,ω, and k such that the system behaves well.
0 0 d
The characteristic equation of the closed-loop system becomes
(cid:5) (cid:2) (cid:3)(cid:6)
k
1+G (s)G (s)=1+G (s) G (cid:8)(s)+ d s2+2ζωs+ω2 (4.83)
p c p c s 0 0 0
For a system controlled by a PI controller we have
(cid:20) (cid:21)
1+G (s)G (cid:8)(s)= s2+2ζωs+ω2 R(s)
p c 0 0 0
The zeros of R(s) are the free poles of the system controlled by the
PI controller G
(cid:8)(s).
Thus,
c
(cid:5) (cid:6)
(cid:20) (cid:21)
k
1+G (s)G (s)= s2+2ζωs+ω2 R(s)+G (s) d (4.84)
p c 0 0 0 p s
The root locus of 1+G (s)G (s) with respect to k will start in the
p c d
zeros of R(s) and end in the zeros of G (s) or in infinity.
p
This parameterization offers a natural way to tune a PID con-
troller: start with a well tuned PI controller and add derivative ac-
tion. As k is increased the parameter ω may have to be modified,
d 0
e.g., in such a way that IE is maximized.
PID Controller Based on PD controller
AnotherwaytoobtainaPIDcontrolleristostartwithaPDcontroller
and to add integral action. Proceeding in the same way as previously
but starting with a PD controller we get
2kζ
k= k (cid:8)(cid:8)+ i 0
ω
0
k
k = k (cid:8)(cid:8) + i
d d ω2
0
(cid:8)(cid:8) (cid:8)(cid:8)
wherek andk arethecontrollerparametersforapurePDcontroller
d
given by Equations (4.75) and (4.76).
A DesignProcedure
We have shown that it is possible to find controllers that assign as
manyclosed-loop poles asthere arefreeparameters inthe controller.

186 Chapter 4 Controller Design
The calculations required are simply a solution of a set of linear
equations. ForaPIcontroller itispossible toassign apairofcomplex
poles with given frequencyω andrelative dampingζ.The assigned
0 0
poles will be dominating if the frequency is sufficiently small. We
can use this idea to develop systematic design procedures. To do
so we start with a set of specifications and design parameters. The
specifications considered are to express load disturbance rejection,
sensitivity tomeasurement noise andprocess variations andsetpoint
following as discussed in Section 4.2.
Method DPD1: Frequency and Damping as Design Parame-
ters
One possibility is to use frequency ω and relative damping ζ as
0 0
design parameters. Other specifications then have to be translated
to conditions on frequency and damping using the relations in Sec-
tion 4.2.
Method DPD2: Relative Damping as Design Parameter
Itiscomparatively easytogive reasonable values ofrelative damping
ζ. Good values are in the range of 0.4 to 1.0. It is much more
0
difficult to find reasonable values of frequency ω. This parameter
0
maychangebymanyordersofmagnitudedependingontheprocess.It
would beuseful, therefore, to determine parameterω automatically.
0
This can be done by selecting a value that gives good rejection of
load disturbances. Notice that the integrated error IE is related to
parameter k through
i
1
IE=
k
i
Hence, k should be maximized in order to minimize IE. The design
i
procedurethenbecomesabitmorecomplicatedbecausethecontroller
parametershavetobecomputedfordifferentvalues ofω,andanop-
0
timization has to be performed. Example 4.7. illustrates this. Notice
that if relative damping is specified in a reasonable way, the crite-
rion IE is a good measure of the rejection of load disturbances. An
alternative is to consider the criterion IAE instead. The computa-
tional burden then increases significantly and the improvement in
performance is marginal. When doing the optimization it must also
be checked that measurement noise does not generate too much con-
trol action. This can be expressed by the constraint
K = K(1+ N)< K (4.85)
hf max
It is straightforward to consider this constraint in the optimization.
The optimization then also tells if performance is limited by process
dynamics or measurement noise. This information is useful in order

|     |     |     |     | 4.8 Dominant | Pole Design | 187 |
| --- | --- | --- | --- | ------------ | ----------- | --- |
to direct redesign of the system. Also notice that the design gives the
frequency ω as a result. This indicates the frequency range where
0
| the process | model             | has to be | reasonably | accurate.        |     |     |
| ----------- | ----------------- | --------- | ---------- | ---------------- | --- | --- |
| Method      | DPD3: Sensitivity |           | as         | Design Parameter |     |     |
One drawback of the design methods given is that sensitivity is only
considered indirectly in the design through the specification of rela-
| tivedampingζ.Another |     | drawbackisthatforsomesystems |     |     |     | itispos- |
| -------------------- | --- | ---------------------------- | --- | --- | --- | -------- |
0
sible to obtain significantly better attenuation of load disturbances
by decreasing damping. One design method that takes this into ac-
count uses sensitivity M s as a design parameter. The design is then
ζ
carried out in the following way. We first fix and perform the de-
0
sign as in Method DPD2, but we also compute the sensitivity M .
s
ζ
The parameter 0 is then changed in order to maximize k i subject to
the constraints on sensitivity and measurement noise, see Equation
(4.85). This method requires more computations than the previous
methods, but has been shown to give very good results. One partic-
ular feature of this method is that the behaviors of the closed-loop
system areverysimilar formanydifferentprocesses. Another feature
is that it gives values of both frequency and damping as intermedi-
ateresults. Thefrequencygives anindication ofthefrequencyranges
where model accuracy is needed. By comparing the values of k, K ,
i hf
| andω,itisalsopossible |     | tomakeanassessment |     |     | oftheperformances |     |
| --------------------- | --- | ------------------ | --- | --- | ----------------- | --- |
0
ofcontrollers having different structures, e.g.,tocomparePIandPID
controllers.
Also notice that, if k can be maximized without violating the
i
constraintonmeasurementnoise,themethodisequivalenttotheloop
shaping procedure discussed inSection4.4,where IEwasminimized
| subject | to constraints | on sensitivity |     | M s . |     |     |
| ------- | -------------- | -------------- | --- | ----- | --- | --- |
Examples
| We illustrate | the design | method   |           | with a few examples. |     |     |
| ------------- | ---------- | -------- | --------- | -------------------- | --- | --- |
| EXAMPLE       | 4.19 A     | pure     | dead-time | process              |     |     |
| Consider      | a process  | with the | transfer  | function             |     |     |
|               |            |          | (s)=      | −sL                  |     |     |
|               |            |          | G         | e                    |     |     |
p
Using pure integral control, it follows from Equation (4.69) that
−aL
|     |     |     | k =ae |     |     |     |
| --- | --- | --- | ----- | --- | --- | --- |
i

| 188      | Chapter  | 4       | Controller | Design             |           |      |           |        |      |
| -------- | -------- | ------- | ---------- | ------------------ | --------- | ---- | --------- | ------ | ---- |
|          | Table    | 4.9     | Controller | parametersobtained |           |      | inExample | 4.19.  |      |
|          | ζ        |         | k          | kL T/L             |           | ωL   | M         | IAE/L  |      |
|          | 0        |         |            | i                  | i         | 0    |           | s      |      |
|          | 0.1      | 0.388   |            | 1.50 0.258         |           | 1.97 | 6.34      | 4.03   |      |
|          | 0.2      | 0.343   |            | 1.27 0.270         |           | 1.93 | 3.60      | 2.42   |      |
|          | 0.3      | 0.305   |            | 1.09 0.279         |           | 1.89 | 2.70      | 1.89   |      |
|          | 0.4      | 0.273   |            | 0.956 0.285        |           | 1.87 | 2.25      | 1.67   |      |
|          | 0.5      | 0.244   |            | 0.847 0.288        |           | 1.86 | 1.99      | 1.56   |      |
|          | 0.6      | 0.218   |            | 0.759 0.288        |           | 1.86 | 1.81      | 1.52   |      |
|          | 0.707    | 0.195   |            | 0.688 0.284        |           | 1.88 | 1.69      | 1.54   |      |
|          | 0.8      | 0.174   |            | 0.629 0.276        |           | 1.90 | 1.61      | 1.61   |      |
|          | 0.9      | 0.154   |            | 0.581 0.265        |           | 1.94 | 1.54      | 1.72   |      |
|          | 1.0      | 0.135   |            | 0.541 0.250        |           | 2.00 | 1.49      | 1.85   |      |
|          |          |         |            |                    | =         | −1/L |           | = 1/L. |      |
| The      | gain     | has its | largest    | value k            | i         | e    | for a     | The    | loop |
| transfer | function |         | for the    | system is          | then      |      |           |        |      |
|          |          |         |            | (s)=               | 1 −(sL+1) |      |           |        |      |
|          |          |         |            | G(cid:10)          | e         |      |           |        |      |
sL
The sensitivity of the system is M =1.39, which is a good value.
s
Let us now consider PI control of the process. To do this we first
π−γ
| must | evaluate | the | transfer | function | on  | the rayω | e   | . We have |     |
| ---- | -------- | --- | -------- | -------- | --- | -------- | --- | --------- | --- |
0
|     | (ω  | π−γ)= | (−ω | cosγ+iω |     | sinγ)= | ω 0Lcosγ | −iω 0Lsinγ |     |
| --- | --- | ----- | --- | ------- | --- | ------ | -------- | ---------- | --- |
|     | G   | e     | G   |         |     |        | e        | e          |     |
|     | p   | 0     | p   | 0       | 0   |        |          |            |     |
Hence,
ω 0Lcosγ
|     |     |     |     | a(ω )= | e   |     |     |     |     |
| --- | --- | --- | --- | ------ | --- | --- | --- | --- | --- |
0
|     |         |                |     | φ(ω)=−ω    | Lsinγ  |      |     |     |     |
| --- | ------- | -------------- | --- | ---------- | ------ | ---- | --- | --- | --- |
|     |         |                |     | 0          | 0      |      |     |     |     |
| It  | follows | from Equations |     | (4.72) and | (4.73) | that |     |     |     |
sin(ω Lsinγ−γ)
|     |     |     | k=   | 0            |     | −ω 0Lcosγ |     |     |     |
| --- | --- | --- | ---- | ------------ | --- | --------- | --- | --- | --- |
|     |     |     |      | sinγ         |     | e         |     |     |     |
|     |     |     |      | sin(ω Lsinγ) |     |           |     |     |     |
|     |     |     |      | 0            |     | −ω 0Lcosγ |     |     |     |
|     |     |     | k =ω |              |     | e         |     |     |     |
|     |     |     | i    | 0 s inγ      |     |           |     |     |     |
ω
| To  | minimize | IE, | we determine | the | value | of  | that | maximizes | k.  |
| --- | -------- | --- | ------------ | --- | ----- | --- | ---- | --------- | --- |
|     |          |     |              |     |       |     | 0    |           | i   |
Setting the derivative of k with respect toω equal to zero we get
|     |       |          |     | i       |         | 0      |     |             |     |
| --- | ----- | -------- | --- | ------- | ------- | ------ | --- | ----------- | --- |
|     | sin(ω | Lsinγ)=ω |     | L(sin(ω | Lsinγ)ζ | −cos(ω |     | Lsinγ)sinγ) |     |
|     | 0     |          | 0   | 0       |         | 0      | 0   |             |     |
|     |       |          |     |         |         | ω      |     |             | γ,  |
Solving this equation with respect to L for different values of
0
we find the controller parameters given in Table 4.9. Table 4.9 also

|     |     |     |     | 4.8 | Dominant | Pole Design |     | 189 |
| --- | --- | --- | --- | --- | -------- | ----------- | --- | --- |
ζ =0.2
|     | 0   |     |     |     | ζ =1.0 |     |     |     |
| --- | --- | --- | --- | --- | ------ | --- | --- | --- |
0
1
|     | ζ =1.0 |     |     |     | ζ =0.2 |     |     |     |
| --- | ------ | --- | --- | --- | ------ | --- | --- | --- |
| 0   | 0      |     |     |     | 0      |     |     |     |
| 0   |        | 10  |     | 20  |        | 30  |     | 40  |
1
−1
| 0   |     | 10  |     | 20  |     | 30  |     | 40  |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
Figure 4.24 Simulation of different controllers for a pure delay
process. The relative dampings are ζ=0.2, 0.4, 0.6, 0.8, and 1.0,
0
=
respectively. The upper diagram shows setpoint y sp 1, process
| output | y,and | the | lower diagram | shows | controlsignal | u.  |     |     |
| ------ | ----- | --- | ------------- | ----- | ------------- | --- | --- | --- |
gives the M values and the IAE. The M value is reasonable for
|        | s        |     |                 |       | s     |                    |      |     |
| ------ | -------- | --- | --------------- | ----- | ----- | ------------------ | ---- | --- |
| ζ ≥    |          |     |                 |       | ζ =   |                    |      |     |
| 0 0.5. | The      | IEA | has its minimum | for   | 0     | 0.6. In particular |      | we  |
|        |          |     |                 | −2    |       | −2/L.              |      |     |
| notice | that for | ζ = | 1 we get        | k = e | and k | = 4e               | This | can |
|        |          | 0   |                 |       |       | i                  |      |     |
be compared with k = e −1L for pure I control. With PI control the
i
integral gain can thus be increased by a factor of 1.5 compared with
an I controller. Notice that for a well-damped system (ζ = 0.707)
0
=
the gain is about 0.2 and the integral time is T i 0.28L. This
can be compared with the values 0.9 and 3.3L given by the Ziegler-
Nichols step response method, 0.45 and 2L by the Ziegler-Nichols
frequency response method, and0.083 and0.14L for the Cohen-Coon
method. Figure 4.24 shows a simulation of controllers with different
parameters. In summary, we find that a process with a pure delay
dynamics can be controlled quite well with a PI controller. Notice,
however, that the tuning cannot be done by the Ziegler-Nichols rules.
In the next example, the dominant pole design method is applied
to the same process as the Ziegler-Nichols methods in Section 4.3.
| EXAMPLE  | 4.20      | Three | equal | lags              |     |     |     |     |
| -------- | --------- | ----- | ----- | ----------------- | --- | --- | --- | --- |
| Consider | a process | with  | the   | transfer function |     |     |     |     |
1
G(s)=
(s+1)3
Table4.10givesthecontrollerparametersobtainedwiththedominant
pole design method that uses M as a tuning parameter for a PI
s
controller. Figure 4.25 shows simulations with controllers obtained

| 190   | Chapter | 4 ControllerDesign |      |                    |      |           |      |       |
| ----- | ------- | ------------------ | ---- | ------------------ | ---- | --------- | ---- | ----- |
| Table | 4.10    | PI controller      |      | parametersobtained |      | inExample |      | 4.20. |
|       | M       | ω                  | ζ    | K                  | k    | T         | IAE  |       |
|       | s       | 0                  |      | 0                  |      | i i       |      |       |
|       | 1.2     | 0.39               | 1.16 | 0.18               | 0.14 | 1.24      | 6.81 |       |
|       | 1.4     | 0.59               | 0.67 | 0.48               | 0.31 | 1.53      | 3.29 |       |
|       | 1.6     | 0.67               | 0.49 | 0.71               | 0.45 | 1.58      | 2.54 |       |
|       | 1.8     | 0.73               | 0.39 | 0.92               | 0.57 | 1.60      | 2.20 |       |
|       | 2.0     | 0.78               | 0.33 | 1.09               | 0.68 | 1.60      | 2.06 |       |
|       | 2.2     | 0.82               | 0.28 | 1.24               | 0.77 | 1.60      | 1.97 |       |
|       | 2.4     | 0.85               | 0.25 | 1.37               | 0.86 | 1.60      | 1.90 |       |
|       | 2.6     | 0.88               | 0.22 | 1.49               | 0.93 | 1.60      | 1.86 |       |
|       | 2.8     | 0.90               | 0.20 | 1.59               | 1.00 | 1.59      | 1.85 |       |
|       | 3.0     | 0.92               | 0.18 | 1.67               | 1.06 | 1.59      | 1.87 |       |
with different values of M s . The behavior is good for values of M s in
|     |     | ≤   | ≤   |     |     |     |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
the interval 1.4 M 2.0. For higher values of M , the responses
|     |     |     | s   |     |     |     | s   |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
become oscillatory. For M = 1.2, the value of ζ is greater than
|     |     |     |     | s   |     | 0   |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
one. This means thatthe twodominant poles arereal. Theweighting
| factor    | b=1isusedinthesimulation. |          |         |      | Asmaller  | valueof    | bwouldgive |     |
| --------- | ------------------------- | -------- | ------- | ---- | --------- | ---------- | ---------- | --- |
| responses | to                        | setpoint | changes | with | a smaller | overshoot. |            |     |
=1.2
|     | M   | =2.8 |     |     |     | M s |     |     |
| --- | --- | ---- | --- | --- | --- | --- | --- | --- |
s
1
=2.8
|     |     | M =1.2 |     |     | M   |     |     |     |
| --- | --- | ------ | --- | --- | --- | --- | --- | --- |
| 0   |     | s      |     |     | s   |     |     |     |
| 0   |     | 10     |     | 20  |     | 30  |     | 40  |
1
−1
| 0   |     | 10  |     | 20  |     | 30  |     | 40  |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
Figure 4.25 Simulation of different PI controllers for a process
|      |          |          | 1/(s+1)3. |     |       |            | M=1.2, |      |
| ---- | -------- | -------- | --------- | --- | ----- | ---------- | ------ | ---- |
| with | transfer | function |           |     | The M | values are |        | 1.6, |
|      |          |          |           |     |       | s          | s      |      |
2.0, 2.4, and 2.8. The upper diagram shows setpoint y = 1 and
sp
process output y, and the lower diagram shows controlsignal u.

|     |     |     |     |     |     | 4.8 DominantPole | Design | 191 |
| --- | --- | --- | --- | --- | --- | ---------------- | ------ | --- |
Table 4.11 PID controller parametersobtained in Example 4.20.
|     | M   | ω    | ζ    | KK   | kK   | T    | T IAE/K   |     |
| --- | --- | ---- | ---- | ---- | ---- | ---- | --------- | --- |
|     | s   | 0    | 0    |      | p i  | p i  | d         | p   |
|     | 1.2 | 0.83 | 0.85 | 0.99 | 0.43 | 2.27 | 0.57 2.93 |     |
|     | 1.4 | 1.07 | 0.55 | 2.05 | 0.93 | 2.21 | 0.54 1.08 |     |
|     | 1.6 | 1.22 | 0.42 | 2.89 | 1.37 | 2.11 | 0.50 0.74 |     |
|     | 1.8 | 1.33 | 0.34 | 3.61 | 1.77 | 2.04 | 0.47 0.60 |     |
|     | 2.0 | 1.42 | 0.29 | 4.24 | 2.14 | 1.98 | 0.44 0.52 |     |
|     | 2.2 | 1.49 | 0.26 | 4.80 | 2.47 | 1.94 | 0.42 0.48 |     |
|     | 2.4 | 1.54 | 0.23 | 5.29 | 2.77 | 1.91 | 0.41 0.44 |     |
|     | 2.6 | 1.59 | 0.21 | 5.74 | 3.04 | 1.89 | 0.40 0.42 |     |
|     | 2.8 | 1.64 | 0.19 | 6.14 | 3.29 | 1.87 | 0.39 0.41 |     |
|     | 3.0 | 1.67 | 0.17 | 6.51 | 3.52 | 1.85 | 0.38 0.40 |     |
In Example 4.3, Ziegler-Nichols methods were used to tune the
same process. The step response method gave the controller parame-
ters K =4.13and T =2.42,whereas the frequency response method
i
|      | =3.2and |     | =2.90.Comparing |     |     |       |                    |     |
| ---- | ------- | --- | --------------- | --- | --- | ----- | ------------------ | --- |
| gave | K       |     | T               |     |     | these | values withtheones | in  |
i
Table4.10showsthattheZiegler-Nichols methodgivesaPIcontroller
| with | a far                       | too high | gain | and a | too long                      | integral | time. |     |
| ---- | --------------------------- | -------- | ---- | ----- | ----------------------------- | -------- | ----- | --- |
|      | Table4.11givesthecontroller |          |      |       | parametersobtainedwiththedom- |          |       |     |
inant pole design method that uses M as a tuning parameter for a
s
PID controller, and Figure 4.26 shows the results of the simulation.
The load disturbance rejection is good for M values greater than
s
1.2. The IAE is significantly smaller than for corresponding PI con-
trollers. The setpoint responses give too large overshoots, since the
| setpoint | weighting |         | is chosen | to           | b=1.    |          |     |     |
| -------- | --------- | ------- | --------- | ------------ | ------- | -------- | --- | --- |
| EXAMPLE  |           | 4.21    | Multiple  | lag          | process |          |     |     |
| Consider | a         | process | with      | the transfer |         | function |     |     |
|          |           |         |           | G(s)=        |         | 1        |     |     |
(s+1)n
(4.69)
To design an integrating controller, it follows from Equation
that
|     |     |     |     | k   | =a(1−a)n |     |     |     |
| --- | --- | --- | --- | --- | -------- | --- | --- | --- |
i
| Taking | derivatives |     | with | respect | to a | gives |     |     |
| ------ | ----------- | --- | ---- | ------- | ---- | ----- | --- | --- |
dk
|     |     |     | i   | =(1−a)n−na(1−a)n−1 |     |     |     |     |
| --- | --- | --- | --- | ------------------ | --- | --- | --- | --- |
da

| 192            | Chapter | 4 ControllerDesign |     |     |     |     |     |
| -------------- | ------- | ------------------ | --- | --- | --- | --- | --- |
| The derivative |         | is zero            | for |     |     |     |     |
1
a=
n+1
| The gain | has | its largest | value |     |            |          |     |
| -------- | --- | ----------- | ----- | --- | ---------- | -------- | --- |
|          |     |             |       | 1   | (cid:20) n | (cid:21) |     |
|          |     |             | =     |     |            | n        |     |
k
|                 |     |                | i      | n+1            | n+1      |          |               |
| --------------- | --- | -------------- | ------ | -------------- | -------- | -------- | ------------- |
| The closed-loop |     | characteristic |        | equation       | is       |          |               |
|                 |     |                |        |                | (cid:20) | (cid:21) |               |
|                 |     |                |        | 1              | n        |          |               |
|                 |     | s(s+1)n+       |        |                |          | n =0     |               |
|                 |     |                |        | n+1            | n+1      |          |               |
| This equation   |     | has double     | roots  | at s=−1/(n+1). |          |          |               |
|                 | =   |                | (4.72) |                | (4.73)   |          |               |
| For             | n   | 1 Equations    |        | and            |          | give the | PI controller |
parameters
|     |     |     |     | k=2ζω | −1  |     |     |
| --- | --- | --- | --- | ----- | --- | --- | --- |
0
=ω2
k i
0
Since the closed-loop system is of second order the parameters are
the same as those obtained by the pole placement method. Compare
| with Section |     | 4.7.              |     |     |     |     |     |
| ------------ | --- | ----------------- | --- | --- | --- | --- | --- |
| Choosingthe  |     | SetpointWeighting |     |     |     |     |     |
It was shown in Chapter 3 that setpoint weighting is very useful in
order to shape the response to setpoint changes. To do this properly,
| wealsoneedaproceduretodetermineparameter |     |     |     |     |     | b.Forthedominant |     |
| ---------------------------------------- | --- | --- | --- | --- | --- | ---------------- | --- |
poledesignmethod,itiseasytofindsuchamethod.Withthismethod,
=2.8
|     | M s |     |     |     |     | =1.2 |     |
| --- | --- | --- | --- | --- | --- | ---- | --- |
M
s
1
|     |     |      |     | M   | =2.8 |     |     |
| --- | --- | ---- | --- | --- | ---- | --- | --- |
|     |     | =1.2 |     |     | s    |     |     |
| 0   | M s |      |     |     |      |     |     |
| 0   |     | 10   |     | 20  |      | 30  | 40  |
6
2
−2
| 0      |      | 10                                             |     | 20  |     | 30  | 40  |
| ------ | ---- | ---------------------------------------------- | --- | --- | --- | --- | --- |
| Figure | 4.26 | SimulationofdifferentPIDcontrollersforaprocess |     |     |     |     |     |
with transfer function 1/(s+1)3. The M values are M=1.2, 1.6,
|     |     |     |     |     | s   |     | s   |
| --- | --- | --- | --- | --- | --- | --- | --- |
2.0, 2.4, and 2.8. The upper diagram shows setpoint y = 1 and
sp
process output y, and the lower diagram shows controlsignal u.

|     |     |     | 4.9 | Designfor | Disturbance | Rejection | 193 |
| --- | --- | --- | --- | --------- | ----------- | --------- | --- |
the closed-loop system will have two complex poles and one pole −p
0
on the real axis. This pole may be slower than the dominant poles.
With setpoint weighting, the closed-loop system has a zero at
1
|     |     |     | s=−z | =−  |     |     |     |
| --- | --- | --- | ---- | --- | --- | --- | --- |
0
bT i
| Bychoosing | bsothat | z   | = p ,wemakesurethatthesetpointdoesnot |     |     |     |     |
| ---------- | ------- | --- | ------------------------------------- | --- | --- | --- | --- |
0 0
tothepolein−p
| excitethemodecorresponding |     |     |     |     | 0 .Thisworkswelland |     |     |
| -------------------------- | --- | --- | --- | --- | ------------------- | --- | --- |
gives good transient responses for systems where the dominant poles
are well damped, (ζ > 0.7). For systems where the poles are not so
0
=2p
well damped, the choice z 0 0 gives systems with less overshoot.
| A suitable |     | choice of | parameter | b is | thus |     |     |
| ---------- | --- | --------- | --------- | ---- | ---- | --- | --- |

|     |     |  | 0 . 5 |     |          |     |     |
| --- | --- | --------- | ----- | --- | -------- | --- | --- |
|     |     |           |       |     | if ζ<0.5 |     |     |
p 0 T i
0.5+2.5(ζ−0.5)
|     | b=  |           |     |     | ≤       | ζ ≤0.7 |     |
| --- | --- | --------- | --- | --- | ------- | ------ | --- |
|     |     |  |     |     | i f 0.5 |        |     |
p T
|     |     |     | 0 i |     |     |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- |
1
ζ >
|     |     |     |     |     | i f 0. | 7   |     |
| --- | --- | --- | --- | --- | ------ | --- | --- |
p T
0 i
| 4.9 Design |     | for | Disturbance |     | Rejection |     |     |
| ---------- | --- | --- | ----------- | --- | --------- | --- | --- |
The design methods discussed so far have been based on a character-
ization of process dynamics. The properties of the disturbances have
only influenced the design indirectly. A load disturbance in the form
of a step was used and in some cases a loss function based on the
error due to a load disturbance was minimized. Measurement noise
was also incorporated by limiting the high-frequency gain of the con-
troller.
In this section, we briefly discuss design methods that directly
attempttomakeatrade-off between attenuation ofloaddisturbances
| and amplification |     | of measurement |     | noise | due to feedback. |     |     |
| ----------------- | --- | -------------- | --- | ----- | ---------------- | --- | --- |
Consider the system shown in Figure 4.27. Notice that the mea-
surement signal is filtered before it is fed to the controller. Let V
and E be the Laplace transforms of the load disturbance and the
measurement error, respectively. The process output and the control
| signal are | then | given by |             |       |             |     |     |
| ---------- | ---- | -------- | ----------- | ----- | ----------- | --- | --- |
|            |      |          | G           |       | G(cid:10)   |     |     |
|            |      | X        | =           | p V − | E           |     |     |
|            |      |          | 1+G(cid:10) |       | 1+G(cid:10) |     |     |
(4.86)
|     |     |     | G(cid:10)   |     | G G         |     |     |
| --- | --- | --- | ----------- | --- | ----------- | --- | --- |
|     |     | U   | =−          | V − | c f E       |     |     |
|     |     |     | 1+G(cid:10) |     | 1+G(cid:10) |     |     |

194 Chapter 4 Controller Design
v e
Controller Process
u x y
G Σ G Σ
c p
Filter
−G
f
Figure 4.27 Block diagram of aclosed-loop system.
where G(cid:10) is the loop transfer function given by
G(cid:10) = G
p
G
c
G
f
Different assumptions about the disturbances and different design
criteria can now be given. We illustrate by an example.
EXAMPLE 4.22
Assume that the transfer functions in Figure 4.27 are given by
1 k
G = G =1 G = k+ i
p f c
s s
Furthermore, assume that eis stationary noise with spectral density
φ and that v is obtained by sending stationary noise with the spec-
e
trumφ through anintegrator. Thisisonewaytomodelthesituation
v
that the load disturbance is drifting and the measurement noise has
high frequency.
With the given assumptions, Equation (4.86) is simplified to
s 1 sk+k
X = V − i E
s2+ks+k s 1 s2+ks+k
i i (4.87)
sk+k 1 s2k+ks
U =− i V − i E
s2+ks+k s 1 s2+ks+k
i i
where we have assumed
1
V(s)= V (s)
1
s
If e and v are white noises, it follows that the variance of x is given
1
by (cid:5) (cid:6)
1 1 k
J = Ex2 = φ + k+ i φ
v e
2kk 2 k
i

|     |     |     |     | 4.9 Designfor | Disturbance | Rejection |     | 195 |
| --- | --- | --- | --- | ------------- | ----------- | --------- | --- | --- |
This equation clearly indicates the compromise in designing the con-
troller. The first term of the right-hand side is the contribution to
| thevarianceduetotheloaddisturbance. |     |     |     |     | Thesecondterm |     | represents |     |
| ----------------------------------- | --- | --- | --- | --- | ------------- | --- | ---------- | --- |
the contribution due to the measurement noise. Notice that the at-
tenuation of the load disturbances increases with increasing k and
k, but that large values of k and k also increase the contribution of
| i           |             |        |         |        | i        |        |          |     |
| ----------- | ----------- | ------ | ------- | ------ | -------- | ------ | -------- | --- |
| measurement |             | noise. |         |        |          |        |          |     |
| We          | can attempt |        | to find | values | of k and | k that | minimize | J.  |
i
| A straightforward |     | calculation |     | gives |     |     |     |     |
| ----------------- | --- | ----------- | --- | ----- | --- | --- | --- | --- |
(cid:5) (cid:6)
|     |     |     |     | √   | 1/4 |     |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
φ
|     |     |     |     | k=       | v   |     |     |     |
| --- | --- | --- | --- | -------- | --- | --- | --- | --- |
|     |     |     |     | 2        | φ   |     |     |     |
|     |     |     |     | (cid:10) | e   |     |     |     |
φ
|     |     |     |     | =   | v   |     |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
|     |     |     |     | k i | φ   |     |     |     |
e
This means that the controller parameters are uniquely given by the
ratio of the intensities of the process noise and the measurement
noise. Also notice that with these parameters the closed-loop charac-
| teristic | polynomial | becomes |     |     |     |     |     |     |
| -------- | ---------- | ------- | --- | --- | --- | --- | --- | --- |
√
|     |     |     |     | s2+ 2ωs+ω2 |     |     |     |     |
| --- | --- | --- | --- | ---------- | --- | --- | --- | --- |
|     |     |     |     |            | 0 0 |     |     |     |
(cid:7)
| with ω | = φ/φ. | The | optimal | system | thus has | a relative | damping |     |
| ------ | ------ | --- | ------- | ------ | -------- | ---------- | ------- | --- |
|        | 0      | v e |         |        |          |            |         |     |
ζ=0.707andabandwidththatisgivenbytheratiooftheintensities
| of load | disturbance | and | measurement |     | noise. |     |     |     |
| ------- | ----------- | --- | ----------- | --- | ------ | --- | --- | --- |
Notice that in Example 4.22 we have a controller that minimizes
the variance of the process output. With white measurement noise it
follows,however,fromEquation(4.87)thatthevarianceofthecontrol
signal is infinite. To obtain a control signal with finite variance, we
can introduce a filter as shown in Figure 4.27. The effect of that is
| illustrated | with | another | example. |     |     |     |     |     |
| ----------- | ---- | ------- | -------- | --- | --- | --- | --- | --- |
| EXAMPLE     | 4.23 |         |          |     |     |     |     |     |
Consider the same system as in the previous example, but assume
that
|     |     |     |      |     | 1 a |     |     |     |
| --- | --- | --- | ---- | --- | --- | --- | --- | --- |
|     |     |     | (s)= |     | =   |     |     |     |
G f
|     |     |     |     | 1+sT | s+a |     |     |     |
| --- | --- | --- | --- | ---- | --- | --- | --- | --- |
f
We get
|     |     | s(s+a) |     |     | aks+ak |     |     |     |
| --- | --- | ------ | --- | --- | ------ | --- | --- | --- |
1
| X   | =             |     |     | V   | −               | i   | E   |     |
| --- | ------------- | --- | --- | --- | --------------- | --- | --- | --- |
|     | s3+as2+aks+ak |     |     |     | 1 s3+as2+aks+ak |     |     |     |
|     |               |     |     | i s |                 |     | i   |     |
(4.88)
|      |               | aks+ak |     |     | aks2+ak         |     |     |     |
| ---- | ------------- | ------ | --- | --- | --------------- | --- | --- | --- |
|      |               |        |     | 1   |                 | s   |     |     |
| U =− |               |        | i   | V   | −               | i   | E   |     |
|      | s3+as2+aks+ak |        |     |     | 1 s3+as2+aks+ak |     |     |     |
|      |               |        |     | i s |                 |     | i   |     |

| 196 | Chapter | 4 ControllerDesign |     |     |     |     |     |     |
| --- | ------- | ------------------ | --- | --- | --- | --- | --- | --- |
Assuming that v and e are white noise, the variance of the process
1
output becomes
|     |     |       | (cid:5)  |       |           |     | (cid:6) |     |
| --- | --- | ----- | -------- | ----- | --------- | --- | ------- | --- |
|     |     |       | 1        | k +a2 | ak(k2+k)  |     |         |     |
|     | J = | Ex2 = |          | i     | φ + i     |     | i φ     |     |
|     |     |       | ak(ak−k) |       | v k(ak−k) |     | e       |     |
2
|                  |             |                                            |     | i   | i i |     | i   |     |
| ---------------- | ----------- | ------------------------------------------ | --- | --- | --- | --- | --- | --- |
| 4.10             | Conclusions |                                            |     |     |     |     |     |     |
| ThePIDcontroller |             | isbyfarthemostcommonlyusedcontrolstrategy. |     |     |     |     |     |     |
There are many different methods to find suitable parameters of the
controllers. The methods differ in complexity, flexibility, and in the
| amount | of process | knowledge |     | used. |     |     |     |     |
| ------ | ---------- | --------- | --- | ----- | --- | --- | --- | --- |
There is clearly a need to have several types of tuning methods.
We need simple, easy-to-use, intuitive methods that require little
informationandthatgivemoderateperformance.Thereisalsoaneed
for sophisticated methods that give the best possible performance
| even if | they require | more | information |     | and more | computations. |     |     |
| ------- | ------------ | ---- | ----------- | --- | -------- | ------------- | --- | --- |
To discuss the methods we must realize that there are many dif-
ferentapplications. Therearecaseswhereitisdesirabletohavetight
control of the process variable. There are other cases where signifi-
cant variations in the process variable is permitted. A typical case is
surgetanks wherethetank level isallowed tofluctuate considerably,
| as long         | as the         | vessel       | is neither  | flooded | nor empty. |      |          |        |
| --------------- | -------------- | ------------ | ----------- | ------- | ---------- | ---- | -------- | ------ |
| A               | good tuning    | method       |             | should  | be based   | on a | rational | design |
| method          | that considers |              | trade-offs  | between |            |      |          |        |
| • Load          | disturbance    |              | attenuation |         |            |      |          |        |
| • Effects       | of measurement |              |             | noise   |            |      |          |        |
| • Robustness    |                | to process   | variations  |         |            |      |          |        |
| • Response      | to             | setpoint     | changes     |         |            |      |          |        |
| • Model         | requirements   |              |             |         |            |      |          |        |
| • Computational |                | requirements |             |         |            |      |          |        |
A tuning method should also be widely applicable. It should contain
design parameters that influence the performance of the closed-loop
system, and it should admit assessment of the differences in perfor-
| mancebetweenPIandPIDcontrollers. |     |     |     |     | Themethodshouldalsomake |     |     |     |
| -------------------------------- | --- | --- | --- | --- | ----------------------- | --- | --- | --- |
it possible to judge whether controllers other than PID are more ap-
propriate, and it should be applicable to different types of a priori
data. Finally, it is desirable that the method be easy to use. Since
these requirements are conflicting, it is clear that we need several
methods.
| TheZiegler-Nichols |     |     | methodisinsufficientinspiteofbeingsimple |     |     |     |     |     |
| ------------------ | --- | --- | ---------------------------------------- | --- | --- | --- | --- | --- |
andwidelyused.Forthemorecomplexmodels,itisnecessarytohave

|     |     |     |     |     |     | 4.11 References | 197 |
| --- | --- | --- | --- | --- | --- | --------------- | --- |
more information about the process. This can be obtained by fitting
rational functions tofrequency responses orbyapplying system iden-
tification techniques. Methods based on cancellation of process poles
like the IMC give simple calculations, but they are not uniformly
applicable. Methods like the dominant pole design or the frequency
responsemethodsarebetterinthisrespect,buttheyarealsomorede-
manding computationally. Sincetheavailable computational capacity
is expected to increase over the next ten year period, we do not think
| that this | is a major | disadvantage. |     |     |     |     |     |
| --------- | ---------- | ------------- | --- | --- | --- | --- | --- |
| 4.11      | References |               |     |     |     |     |     |
ThereisaverylargeliteratureontuningofPIDcontrollers.Goodgen-
eralsourcesarethebooks(Smith,1972),(DeshpandeandAsh,1981),
(Shinskey,1988),(McMillan,1983),(Corripio,1990),and(Sudaetal.,
1992). The books clearly show the need for a variety of techniques,
simple tuning rules, as well as more elaborate procedures that are
based on process modeling, formulation of specifications, and control
design. Even if simple heuristic rules are used, it is important to
realize that they are not a substitute for insight and understanding.
Successfulcontrollertuningcannotbedonewithoutknowledgeabout
process modeling and control theory. It is also necessary to be aware
that there are many different types of control problems and conse-
quently many different design methods. To only use one method is as
| dangerous | as to only | believe        | in empirical |                 | tuning | rules. |             |
| --------- | ---------- | -------------- | ------------ | --------------- | ------ | ------ | ----------- |
| Control   | problems   | canbespecified |              | inmanydifferent |        |        | ways. Agood |
review of different ways to specify requirements on a control system
|          | (Truxal, | 1955), | (Maciejowski, |     | 1989), |     | (Boyd    |
| -------- | -------- | ------ | ------------- | --- | ------ | --- | -------- |
| is given | in       |        |               |     |        | and | and Bar- |
ratt, 1991). To formulate specifications it is necessary to be aware of
thefactorsthatfundamentally limittheperformanceofacontrol sys-
tem. Simple ways to asses the achievable performance of controllers
aregiven in(Shinskey, 1990),(Shinskey, 1991a),and(Åström, 1991).
Therearemanypapersoncomparisonsofcontrolalgorithmsandtun-
ing methods. The paper (McMillan, 1986) gives much sound advice;
|              |                |     | (Miller      | 1967) |     | (Gerry, | 1987).          |
| ------------ | -------------- | --- | ------------ | ----- | --- | ------- | --------------- |
| other useful | papers         | are | et           | al.,  | and |         |                 |
| The          | paper (Ziegler |     | and Nichols, | 1942) | is  | the     | classic work on |
controller tuning. An interesting perspective on this paper is given
|                 |      |          | (Blickley, |     | 1990). |     |             |
| --------------- | ---- | -------- | ---------- | --- | ------ | --- | ----------- |
| in an interview | with | Ziegler, | see        |     |        | The | CHR-method, |
described in (Chien et al., 1952), is a modification of the Ziegler-
Nichols method. This is one of the first papers where it is mentioned
that different tuning methods are required for setpoint response and
for load disturbance response. Good response to load disturbances is
often the relevant criteria in process control applications. In spite of
this, most papers concentrate on the setpoint response. Notice also

198 Chapter 4 ControllerDesign
thattheresponses canbetuned independently byhaving acontroller
that admits a two-degree-of-freedom structure. The usefulness of a
design parameter is also mentioned in the CHR-paper. In spite of
its shortcomings the Ziegler-Nichols method has been the foundation
for many tuning methods, see (Tan and Weber, 1985), (Mantz and
Tacconi,1989),and(Hangetal.,1991).Tuningchartswerepresented
in (Wills, 1962b), (Wills, 1962a), and (Fox, 1979).
The loop-shaping methods were inspired by classical control de-
signmethods basedonfrequency response, see(Truxal,1955).Appli-
cations to PID control are found in (Pessen, 1954), (Habel, 1980),
(Chen, 1989), (Yuwana and Seborg, 1982).
The analytical tuning method was originally proposed in (New-
ton et al., 1957); a more recent presentation is found in (Boyd and
Barratt, 1991). The original papers on the λ-tuning method are
(Dahlin, 1968) and (Higham, 1968). The method is sometimes called
the Dahlin method, see (Deshpande and Ash, 1981). This method
is closely related to the Smith predictor and the internal model con-
troller,see(Smith,1957),(Chien,1988),(ChienandFruehauf,1990),
and (Rivera et al., 1986). The PPI controller, which is described in
(Hägglund, 1992),andthemethod given in(Haalman,1965)arespe-
cial cases. The tuning technique developed in (Smith and Murrill,
1966), (Pemberton, 1972a), (Pemberton, 1972b), (Smith et al., 1975),
(Hwang and Chang, 1987) arealso based onthe analytical approach.
The analytical tuning method gives controllers that cancel poles
and zeros in the transfer function of the process. This leads to lack
of observability or controllability. There are severe drawbacks in this
as has been pointed out many times, e.g., in (Shinskey, 1991b) and
(Morari and Lee, 1991). The response to load disturbances will be
very sluggish for processes with dominating, long time constants.
Many methods for control design are based on optimization tech-
niques.Thisapproachhastheadvantagethatitcapturesmanydiffer-
entaspectsofthedesignproblem.Thereisalsopowerfulsoftwarethat
canbeused.Ageneraldiscussionoftheuseofoptimizationforcontrol
designisfoundin(BoydandBarratt,1991).Thepapers(Roviraetal.,
1969)and(Lopez etal.,1969)give controllers optimized with respect
to the criteria ISE, IAE and ITAE. Other applications to PID control
are given in (Hazebroek and van der Waerden, 1950), (Wolfe, 1951),
(Oldenburg and Sartorius, 1954), (van der Grinten, 1963a), (Lopez
etal.,1967),(Marsili-Libelli, 1981),(YuwanaandSeborg,1982),(Pat-
wardhanetal.,1987),(WongandSeborg,1988),(Polonoyi,1989),and
(Zhuang and Atherton, 1991). The methods BO and SO were intro-
duced in (Kessler, 1958a) and (Kessler, 1958b). A discussion of these
methods with many examples are found in (Fröhr, 1967) and (Fröhr
and Orttenburger, 1982).
Pole placement is a straightforward design method much used

|     |     |     |     | 4.11 References | 199 |
| --- | --- | --- | --- | --------------- | --- |
in control engineering, see (Truxal, 1955). It has the advantage that
the closed-loop poles are specified directly. Many other design meth-
odscanalsobeinterpretedaspoleplacement.Thepapers(Elgerdand
| Stephens, | 1959) | and (Graham | and Lathrop, | 1953) show | how many |
| --------- | ----- | ----------- | ------------ | ---------- | -------- |
properties of the closed-loop system can be deduced from the closed-
loop poles. This gives good guidance for choosing the suitable closed-
(Cohen
| loop poles. | An  | early example | of pole placement | is  | and Coon, |
| ----------- | --- | ------------- | ----------------- | --- | --------- |
1953),(Coon, 1956a),and(Coon, 1956b).Itmaybedifficulttochoose
desired closed-loop poles for high-order systems. This is avoided by
specifying only a few poles, as in the dominant pole design method
described in(Persson, 1992),(Persson and Åström, 1992), and(Pers-
1993).
son and Åström,
There are comparatively few papers on PID controllers that con-
sider the random nature of disturbances. The papers (van der Grin-
| 1963b), | (Goff, | 1966a), | (Fertik, 1975) |                 |     |
| ------- | ------ | ------- | -------------- | --------------- | --- |
| ten,    |        |         | and            | are exceptions. |     |

New Tuning Methods
5.1 Introduction
Manymethods for designing PIDcontrollers werepresented inChap-
ter 4. From this we can conclude that there are many issues that
have to be taken into account when designing a controller, e.g., load
disturbance response, measurement noise, setpoint following, model
requirements, and model uncertainty. It is also clear that there is a
need for a variety of tuning methods; simple techniques that require
little process knowledge as well as more elaborate methods that use
more information about the process.
InthischapterweusetheinsightobtainedinChapter4todevelop
new methods for controller tuning. In Section 5.2 we discuss the key
requirements on a good design method. In addition to the issues
mentioned above, we consider the choice of design parameters and
the process knowledge required. The method used todevelop the new
rulesisquitestraightforward.Firstweapplyareliabledesignmethod
withthedesiredcharacteristicstoalargetestbatchofrepresentative
processes.Thenwetrytocorrelatethecontrollerparametersobtained
with simple features that characterize the process dynamics.
InSections5.3and5.4wepresenttuningrulesthatcanbeviewed
asextensions oftheZiegler-Nichols rules. Themaindifference isthat
we are using three parameters to characterize process dynamics in-
steadoftwoparameters usedbyZiegler andNichols. Itisshown that
the new methods give substantial improvements in control perfor-
mance while retaining much of the simplicity of the Ziegler-Nichols
rules.
Methods based on the step response of the process are presented
in Section 5.3. In this case we characterize process dynamics with
theparameters aand Lused byZiegler andNichols and,inaddition,
thenormalized deadtimeτ.Theseparametersareeasilydetermined.
The tuning rules obtained give the normal PID parameters and, in
addition, the setpoint weighting.
In Section 5.4 we present frequency-domain methods. They are
based on the parameters ultimate gain K , ultimate period T and
u u
200

5.2 ASpectrum ofTools 201
gainratioκ.Theseparameterscanbeobtainedfromtheconventional
Ziegler-Nichols experiment or an experiment with relay tuning com-
bined with a determination of the static gain of the process.
The methods used in Sections 5.3 and 5.4 are based on approxi-
mateprocessmodels.InSection5.5wepresentanefficientmethod of
computing controller gains when the transfer function of the process
in known. These results make it possible to judge the advantage in
obtaining more process information.
In Section 5.6 we explore some consequences of the results of
the previous sections. The closed-loop systems obtained with the new
tuning rules may have many poles and zeros. The behavior of the
closed-loop system, however, is dominated by a few poles and zeros.
These can be related to the key features of the process. By investi-
gating these relations we get interesting insight into the properties
of the closed-loop system, which can be used to judge achievable per-
formance directly from the process features.
Examples of using the new tuning rules are given in Section 5.7.
5.2 A Spectrum of Tools
The results of Chapter 4 clearly indicate that a sound tuning method
shouldconsidermanydifferentissuessuchasloaddisturbances,mea-
surementnoise,modelrequirements,andmodelaccuracy.Agoodtun-
ing method should also have design parameters so that the desired
performancecanbechangedeasily.Unfortunately,itisnotpossibleto
find a single tuning method that satisfies all requirements. Instead,
we develop a spectrum of methods that differ in the effort required
to use them and in the performance obtained.
The wide-spread use of the Ziegler-Nichols methods and its vari-
ants clearly indicates the need for simple methods that use minimal
process information, but there is also a need for more complex meth-
ods that require more effort but, in return, give better control perfor-
mance.
To develop the simple methods we must first find out if it is at
all possible to obtain reliable tuning rules based on a simple charac-
terization of process dynamics. We must also find features that are
useful for characterizing the process dynamics. We have approached
this in an empirical way by trial and error.
Westartwithatest batchof processes withknown transfer func-
tions. Controllers for these processes are then designed using a good
tuning method, e.g., dominant pole design. We then attempt to find
process features that admit simple description of the controller pa-
rameters. The choice of parameters that are useful to characterize
process dynamics is guided by the analysis in Chapter 2. After sev-

| 202 Chapter |     | 5 New | Tuning | Methods |     |     |     |
| ----------- | --- | ----- | ------ | ------- | --- | --- | --- |
eral attempts we find that it is possible to obtain reasonable tuning
| rulesbasedonthreeparameters, |      |          |     | andthatthedimension-free |          |         | param- |
| ---------------------------- | ---- | -------- | --- | ------------------------ | -------- | ------- | ------ |
| eters relative               | dead | timeτand |     | relative                 | gainκare | useful. |        |
parametersκandτ,
| Since | the method |     | is based | on the |     |     | it is called |
| ----- | ---------- | --- | -------- | ------ | --- | --- | ------------ |
Kappa-Tau tuning, which we also abbreviate as KTtuning. For more
accurate tuning, it is suggested to use dominant pole design. This
| method will, | however, |     | require | more | process | knowledge. |     |
| ------------ | -------- | --- | ------- | ---- | ------- | ---------- | --- |
TheTestBatch
The results of an investigation depend critically on the chosen test
batch. We have chosen processes that are representative for the dy-
namics of typical industrial processes. The following systems were
| used for | stable | processes. |     |     |     |     |     |
| -------- | ------ | ---------- | --- | --- | --- | --- | --- |
−s
e
| G (s)= |         |     |     |     |     | T =0.1,...,10 |     |
| ------ | ------- | --- | --- | --- | --- | ------------- | --- |
| 1      | (1+sT)2 |     |     |     |     |               |     |
1
| (s)= |        |     |     |     |     | n=3,4,8 |     |
| ---- | ------ | --- | --- | --- | --- | ------- | --- |
| G 2  | (s+1)n |     |     |     |     |         |     |
(5.1)
| (s)= |     |     |     | 1   |     | α=0.2,0.5,0.7 |     |
| ---- | --- | --- | --- | --- | --- | ------------- | --- |
G
| 3   | (1+s)(1+αs)(1+α2s)(1+α3s) |     |     |     |     |     |     |
| --- | ------------------------- | --- | --- | --- | --- | --- | --- |
1−αs
| G (s)= |        |     |     |     |     | α=0.1,0.2,0.5,1,2 |     |
| ------ | ------ | --- | --- | --- | --- | ----------------- | --- |
| 4      | (s+1)3 |     |     |     |     |                   |     |
To cover processes with integration we also include models obtained
| by adding | an integrator |       | to   | the systems | listed | above.       |          |
| --------- | ------------- | ----- | ---- | ----------- | ------ | ------------ | -------- |
| The test  | batch         | (5.1) | does | not include |        | the transfer | function |
e −sL
|     |     |     | G(s)= |     |     |     | (5.2) |
| --- | --- | --- | ----- | --- | --- | --- | ----- |
K
p 1+sT
because this model is not representative for typical industrial pro-
cesses. Tuning based on the model (5.2) typically give a controller
gain that is too high. This is remarkable because tuning rules have
| traditionally | been | based | on  | this model. |     |     |     |
| ------------- | ---- | ----- | --- | ----------- | --- | --- | --- |
SimpleTuningRules
Toobtain the simple tuning rules weuse the Ziegler-Nichols rules as
astarting point. These rules arebased on process data inthe form of
two parameters: a and L for the step-response method, and T and
u
K for the frequency-response method. The properties of the Ziegler-
u
Nichols rules were discussed extensively in Section 4.3. The results
| can be summarized |     | as  | follows. |     |     |     |     |
| ----------------- | --- | --- | -------- | --- | --- | --- | --- |

5.3 Step-ResponseMethods 203
| A. The responses | are too | oscillatory. |
| ---------------- | ------- | ------------ |
B. Different tuning rules are required for setpoint response and for
| load disturbance | response. |     |
| ---------------- | --------- | --- |
C. Therulesgivepoorresultsforsystemswithlongnormalizeddead
time.
| D. There is | no tuning parameter. |     |
| ----------- | -------------------- | --- |
Drawback A is easy to deal with. It is sufficient to modify the pa-
rameters in the tables. Item B can be dealt with by tuning for load
disturbances and using setpoint weighting to obtain the desired set-
point response. Item C is more difficult to deal with because it is
necessary to have more process information. A first step is to char-
acterize the process by three parameters instead of two. It turns out
| that this gives | a substantial | improvement. |
| --------------- | ------------- | ------------ |
Asatuningparameterweusethemaximumsensitivity M .Recall
s
| that this parameter | is defined | as  |
| ------------------- | ---------- | --- |
(cid:11) (cid:11)
(cid:11) 1 (cid:11)
|     | =m  | (cid:11) (cid:11)    |
| --- | --- | -------------------- |
|     | M   | ax (cid:11) (cid:11) |
|     | s   | ω 1+G (iω )G (iω)    |
p c
where G (s) is the controller transfer function and G (s) the process
c p
transferfunction.Theparameteralsohasanicegeometricalinterpre-
tationintheNyquistdiagram.Theshortestdistance fromthecritical
−1 1/M
point to the Nyquist curve of G p G c is s . This admits a direct
interpretation as a robustness measure, because it tells how much
the process can change without causing instability. Typical values of
M s areinthe rangeof 1.2to2.Largervalues of M s give systems that
are faster but less robust. It is also useful that the range to consider
| is not too large. |     |         |
| ----------------- | --- | ------- |
| 5.3 Step-Response |     | Methods |
Inthissectionwedescribesimpletuningrulesbasedonstep-response
data. The need for such techniques are clear in anhistorical perspec-
tive. A simple tuning method of this type is useful for manual tuning
and it can also be incorporated into automatic tuners. It turns out
that it is possible to obtain substantial improvements compared to
other approaches at the cost of a modest increase in complexity.
Stable Processes
First we consider the case when the processes are stable. Process
dynamics are characterized by three parameters: the static gain K ,
p
the apparent lag T, and the apparent dead time L. In Chapter 2 we

| 204 Chapter | 5 New | Tuning | Methods |     |     |     |     |
| ----------- | ----- | ------ | ------- | --- | --- | --- | --- |
discussed different ways to determine these parameters experimen-
tally. In that section we also found that it is difficult to determine
more than three parameters from a step response. There is some ar-
bitrariness in the determination of L and T. Here we determine L
as the intersection of the tangent with the steepest slope with the
time axis. Parameter T is determined as the time when the step re-
sponse reaches 63% of its final value. An alternative is to determine
the average residence time, T , by the method of moments and to
ar
| determine | T from |     |     |     |     |     |     |
| --------- | ------ | --- | --- | --- | --- | --- | --- |
|           |        |     | =   | −   |     |     |     |
|           |        |     | T   | T   | L   |     |     |
ar
To present the results it is convenient to reparameterize the process.
| Guided by | the Ziegler-Nichols |     | formula |     | we use the | parameter |     |
| --------- | ------------------- | --- | ------- | --- | ---------- | --------- | --- |
L
|     |     |     | a=  | K   |     |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- |
p
T
| instead of | K p and the | relative | dead | time |     |     |     |
| ---------- | ----------- | -------- | ---- | ---- | --- | --- | --- |
|            |             |          |      | L    | L   |     |     |
|            |             | τ=       |      | =    |     |     |     |
|            |             |          | L+T  |      | T   |     |     |
ar
| instead of  | T.        |     |     |     |     |     |     |
| ----------- | --------- | --- | --- | --- | --- | --- | --- |
| Integrating | Processes |     |     |     |     |     |     |
Parameters a and L can be determined from a step-response exper-
iment for processes with integration. Since the process is not stable
it will, however, not reach a steady state. The initial part of the re-
sponse can be determined, but the experiment has to be interrupted
| after some | time. |     |     |     |     |     |     |
| ---------- | ----- | --- | --- | --- | --- | --- | --- |
The relative dead time τis zero for processes with integration.
It can thus be attempted to use the formulas derived for stable pro-
τ=
cesses with 0. It is, however, useful to base the tuning on more
information about the initial part of the step response. This can be
obtained from the impulse response of the system, which can be ap-
proximated by the pulse response if the pulse is sufficiently short. If
| the transfer | function | of the | process | is  | G(s), we have |     |     |
| ------------ | -------- | ------ | ------- | --- | ------------- | --- | --- |
1
|     |     |     | G(s)= | H(s) |     |     |     |
| --- | --- | --- | ----- | ---- | --- | --- | --- |
s
H(s)isa
| where | stable | transfer |     | function. | Astep-response | experiment |     |
| ----- | ------ | -------- | --- | --------- | -------------- | ---------- | --- |
performed on H(s)is equivalent to a pulse-response experiment per-
|             | G(s).Thus,wecandeterminethesteady-stategain |      |         |         |                   |      | (cid:8) |
| ----------- | ------------------------------------------- | ---- | ------- | ------- | ----------------- | ---- | ------- |
| formedon    |                                             |      |         |         |                   |      | K p and |
|             |                                             |      | (cid:8) |         |                   | H(s) |         |
| the average | residence                                   | time | T       | for the | transfer function |      | using   |
ar
| the methods | discussed | in  | Chapter         | 2. It       | can be shown       | that |     |
| ----------- | --------- | --- | --------------- | ----------- | ------------------ | ---- | --- |
|             |           |     | (cid:8) (cid:8) | (cid:8)(L   | (cid:8)+T (cid:8)) |      |     |
|             |           | a=  | K T             | = K         |                    |      |     |
|             |           |     | p ar            | p           |                    |      |     |
|             |           | L=T | (cid:8) =       | L (cid:8)+T | (cid:8)            |      |     |
ar

|     |     |     | 5.3 Step-ResponseMethods |     | 205 |
| --- | --- | --- | ------------------------ | --- | --- |
Parameters a and L are therefore easy to obtain from the pulse
τ(cid:8)
experiment. The normalized dead time , associated with transfer
function H(s), can be used as an additional parameter. Tuning rules
basedon a, L,andτ(cid:8) canbedeveloped for processes withintegration.
| They are | similar to the | rules for stable | processes. |     |     |
| -------- | -------------- | ---------------- | ---------- | --- | --- |
Intheoldliteratureoncontrollertuningtheexpression“processes
with self-regulation” was used to describe stable processes and “pro-
cesses without self-regulation” was used to describe processes with
integration. Itisinteresting toobservethattheseclassesalwayswere
| treated       | separately in | classical papers | on controller | tuning. |     |
| ------------- | ------------- | ---------------- | ------------- | ------- | --- |
| Normalization | of Controller | Parameters       |               |         |     |
The PI controller has three parameters: the gain K, the integration
time T, and the setpoint weighting b. It is convenient to represent
i
these parameters in dimension-free form by suitable normalization.
| Thenormalizedcontroller            |     | gainisaK,andthenormalizedintegration |                          |     |     |
| ---------------------------------- | --- | ------------------------------------ | ------------------------ | --- | --- |
| timeT/L.Thisisthesamenormalization |     |                                      | usedintheZiegler-Nichols |     |     |
i
rules.(ComparewithSection4.3.)Insomecasestheintegration
time
will be normalized by T instead of L. Notice that parameter T is not
defined for processes with integration. This is the reason why it is
| better to | base the tuning | on L than | on T. |     |     |
| --------- | --------------- | --------- | ----- | --- | --- |
The Method
An empirical method is used to find the new tuning rules. Controller
parametersarecomputedforthedifferentprocesses inthetestbatch,
using dominant pole design. We then attempt to find relations be-
tween the normalized controller parameters and the normalized pro-
cess parameters. This is done by plotting the normalized controller
parameters asa function of normalized dead timeτ. For example, we
investigate whether the normalized controller gain can be expressed
as
|     |     | =   | f(τ) |     |     |
| --- | --- | --- | ---- | --- | --- |
aK
andanalogous expressions fortheother parameters. Itturns outthat
itisindeedpossibletofindapproximations ofthistype.Thefunctions
obtained can be well approximated by functions having the form
|     |     | f(τ)= | τ+a2 τ2 |     | (5.3) |
| --- | --- | ----- | ------- | --- | ----- |
|     |     | a     | ea1     |     |       |
0
| Many other   | functions       | can also be | used. |     |     |
| ------------ | --------------- | ----------- | ----- | --- | --- |
| PIControlfor | StableProcesses |             |       |     |     |
The simplified tuning rules for PI controllers are treated first. Fig-
ure 5.1 shows the normalized controller parameters as a function of

| 206 Chapter | 5 New Tuning | Methods |     |     |     |
| ----------- | ------------ | ------- | --- | --- | --- |
normalized deadtimefor PIcontrol of stable processes. Thisfigureis
batch(5.1).The
| based onthe | systems inthe | test |     | curves drawn | corre- |
| ----------- | ------------- | ---- | --- | ------------ | ------ |
spondtotheresults obtainedbycurvefitting. Thetuning obtained by
theZiegler-Nichols rules areshown bythe dashed lines in thefigure.
| To get | some insight | we consider | the results | for M = | 2, which |
| ------ | ------------ | ----------- | ----------- | ------- | -------- |
s
correspondstothedatalabeled (cid:14)inthefigure.Figure5.1showsthat
thenormalizedcontrollergainrangesfrom0.35to1.5,thenormalized
integration timefrom 0.2to9,andthesetpoint weighting from0.4to
0.6.Thisshowsclearlythatitisimpossibletoobtaingoodtuningrules
τ.
that do not depend on The deviations from the solid lines in the
figure is about ±20%. With tuning rules based on three parameters
it is thus possible to obtain reasonable tuning rules, at least for the
classes of systems given in the test batch (5.1). If the range of τis
restrictedtovaluesbetween0.2and0.6,thegainratiovariesbetween
0.35 and 0.50, but the normalized integration time varies between
0.6 and 3. The behavior for M =1.4 is similar but the ranges of the
s
|     | vs.τ |     |     | bvs.τ |     |
| --- | ---- | --- | --- | ----- | --- |
aK
10
10
1
1
0.1
| 0   | 0.5      |     | 1 0 | 0.5      | 1   |
| --- | -------- | --- | --- | -------- | --- |
|     | T/L vs.τ |     |     | T/T vs.τ |     |
|     | i        |     |     | i        |     |
| 10  |          |     | 10  |          |     |
| 1   |          |     | 1   |          |     |
| 0.1 |          |     | 0.1 |          |     |
| 0   | 0.5      |     | 1 0 | 0.5      | 1   |
Figure 5.1 Tuning diagrams for PI control of stable processes.
Controller parameters are obtained by applying dominant pole de-
○
| signwith                          | M =1.4, markedwith |       | ,and M                  | =2, markedwith(cid:14)to |     |
| --------------------------------- | ------------------ | ----- | ----------------------- | ------------------------ | --- |
|                                   | s                  |       | s                       |                          |     |
| thesystemsinthetestbatch(5.1).The |                    |       | dashedlinescorrespondto |                          |     |
| the Ziegler-Nichols               | tuning             | rule. |                         |                          |     |

5.3 Step-ResponseMethods 207
normalized parameters are even larger. Itis thus not possible to find
a good tuning rule that does not depend on τ even for a restricted
range of values. This explains why tuning rules for PI control of the
Ziegler-Nichols type have performed so poorly.
The figure also shows that there is a significant difference be-
tween the controller gains obtained when the design parameter M
s
has the values 1.4 and 2. Notice, however, that the integral time ap-
pearstobeindependent ofthedesignparameter M .Thismeansthat
s
for PI control of stable processes we can choose integration time in-
dependent of M and simply use the gain to adjust M . The setpoint
s s
weighting does not vary much with τwhen M = 2, but it changes
s
significantly when M =1.4.
s
Figure 5.1 illustrates the well-known difficulties with Ziegler
Nichols tuning of PI controllers. It indicates that the gain obtained
from the Ziegler-Nichols rule should be reduced. It also shows that
control of processes with small and largeτis very different. For lag-
dominated processes, i.e., small values of τ, the proportional gain
and the integral time should be smaller. Another way to express this
is that proportional action should be stronger and integral action
weaker. For dead-time dominated process we have the reverse situ-
ation. Also, recall that in both extremes there are other controllers
that will perform better than PI controllers.
Figure 5.1 also suggests that if the integral time is normalized
with apparent time constant T instead of apparent dead time L, the
Ziegler-Nichols methodcanbereplacedbythefollowingsimpletuning
rule, aK = 0.4, T = 0.7T, and b=0.5. This gives quite good tuning
i
forrelativedeadtimesintherange0.1<τ<0.7.Thismeansthatthe
ratio of apparent dead time to apparent time constant is between 0.1
and2.Table5.1givesthecoefficients a ,a ,anda offunctionsofthe
0 1 2
form(5.3)thatarefittedtothedatainFigure5.1.Thecorresponding
graphs are shown in solid lines in the figure.
Table 5.1 Tuning formula for PI control obtained by the step-
response method. The table gives parameters of functions of the
form f(τ)=a exp(aτ+aτ2)forthenormalizedcontrollerparam-
0 1 2
eters.
M =1.4 M =2.0
s s
a a a a a a
0 1 2 0 1 2
aK 0.29 −2.7 3.7 0.78 −4.1 5.7
T/L 8.9 −6.6 3.0 8.9 −6.6 3.0
i
T/T 0.79 −1.4 2.4 0.79 −1.4 2.4
i
b 0.81 0.73 1.9 0.44 0.78 −0.45

| 208 Chapter | 5 New Tuning | Methods |     |       |     |
| ----------- | ------------ | ------- | --- | ----- | --- |
|             | aK vs.τ      |         |     | bvs.τ |     |
10
10
1
1
0.1
| 0               | 0.5                                               | 1 0      |             | 0.5       | 1     |
| --------------- | ------------------------------------------------- | -------- | ----------- | --------- | ----- |
|                 | T/L vs.τ                                          |          |             | T/T vs.τ  |       |
|                 | i                                                 |          |             | i         |       |
| 10              |                                                   | 10       |             |           |       |
| 1               |                                                   | 1        |             |           |       |
| 0.1             |                                                   | 0.1      |             |           |       |
| 0               | 0.5                                               | 1 0      |             | 0.5       | 1     |
|                 | T /L vs.τ                                         |          |             | T /T vs.τ |       |
|                 | d                                                 |          |             | d         |       |
| 1               |                                                   | 1        |             |           |       |
| 0.1             |                                                   | 0.1      |             |           |       |
| 0.01            |                                                   | 0.01     |             |           |       |
| 0               | 0.5                                               | 1 0      |             | 0.5       | 1     |
| Figure          | 5.2 TuningdiagramsforPIDcontrol.Controllerparame- |          |             |           |       |
| tersareobtained | byapplying                                        | dominant | pole design | with M    | =1.4, |
s
|        | ○            | =                | (cid:14), |                 |     |
| ------ | ------------ | ---------------- | --------- | --------------- | --- |
| marked | with , and M | s 2, marked with |           | to the syst ems | in  |
testbatch(5.1).ThedashedlinescorrespondtotheZiegler-Nichols
| tuning rule. |     |     |     |     |     |
| ------------ | --- | --- | --- | --- | --- |

5.3 Step-ResponseMethods 209
PIDControlfor StableProcesses
Tuning rules for PID control are developed in the same way as the
rulesforPIcontrol.Processdynamicsarecharacterizedbytheparam-
eters a, L, andτwhich were also used for PI control. The controller
parameters are normalized as aK, T/L, and T /L. The parameters
i d
aredetermined for the systems in thetest batch(5.1)using the dom-
inant pole design method. The controller parameters are then nor-
malized and plotted against normalized dead timeτ. The results are
given in Figure 5.2,where curves fitted to the data are given in solid
lines and the Ziegler-Nichols tuning is shown in dashed lines.
Consider the values obtained for M = 2, i.e., the points marked
s
(cid:14) in Figure 5.2. The normalized gain varies from 0.8 to 3, the nor-
malized integration time from 0.55 to 2.5, the normalized derivation
time from 0.15 to 0.55, and the setpoint weighting from 0.2 to 0.4.
Notice that the ranges of parameters are significantly smaller than
for PI control. This explains why it is easier to find tuning rules that
do not depend onτfor PID than for PI controllers. With tuning rules
based on three parameters, like those illustrated by full lines in Fig-
ure5.2,it ispossible toobtain controller parameters witha precision
of about 25% for the processes in the test batch.
The Ziegler-Nichols tuning rules are represented by dashed lines
inthefigure. Thereisreasonable agreement withtheZiegler-Nichols
rules when τis between 0.2 and 0.4. This is in sharp contrast with
Figure 5.1, where no agreement with the Ziegler-Nichols rule was
obtained for any τ. This corresponds well with the observation that
the Ziegler-Nichols step-response rules work better for PID than for
PI control. The general pattern indicated in Figure 5.2 is that both
integration time T and derivative time T should be decreased with
i d
increasing τ. The value of the normalized gain depends on M . It is
s
slightly less than the value obtained with the Ziegler-Nichols rule
for M = 2. Both the integral time and the derivative time, however,
s
should depend on τ. The figure also shows that proportional action
dominates for smallτand integral action for largeτ. In Table 5.2 we
give the results of curve fitting for Figure 5.2. Figure 5.2 shows that
constant gain can be used for values ofτbetween 0.2 and 0.7, if the
normalization is performed with T instead of L.
IntegratingProcesses
Tuning rules for processes with integration were developed by apply-
ing the dominant pole design method to processes with the transfer
functions
1
G (s)= H(s)
i i
s

210 Chapter 5 New Tuning Methods
Table 5.2 Tuning formula for PID control obtained by the step-
response method. The table gives parameters of functions of the
form f(τ)=a exp(aτ+aτ2)forthenormalizedcontrollerparam-
0 1 2
eters.
M =1.4 M =2.0
s s
a a a a a a
0 1 2 0 1 2
aK 3.8 −8.4 7.3 8.4 −9.6 9.8
T/L 5.2 −2.5 −1.4 3.2 −1.5 −0.93
i
T/T 0.46 2.8 −2.1 0.28 3.8 −1.6
i
T /L 0.89 −0.37 −4.1 0.86 −1.9 −0.44
d
T /T 0.077 5.0 −4.8 0.076 3.4 −1.1
d
b 0.40 0.18 2.8 0.22 0.65 0.051
where H (s) are the transfer functions given in the test batch (5.1).
i
(cid:8) (cid:8)
The apparent dead time L, the apparent time constant T , and the
gain K (cid:8) of the transfer functions H(s) were determined. The nor-
p i
malizedcontroller parameters aK, T/L, T /L,and bhave then been
i d
plotted as functions of the normalized dead time for G (s).
i
PI Control for Integrating Processes
Figure5.3givestheresultsforPIcontrol.Thefigureshowsthatthere
is some variation in the normalized parameters aK and T/L with
i
τ(cid:8) . For M =2, the values of aK varies between 0.5 and 0.7, and the
s
values of T/L are between 3 and 5. The parameter b changes more,
i
from 0.3 to 0.7. The variation is larger for M = 1.4. The parameter
s
values given bythe Ziegler-Nichols rule areshown bydashed lines in
Figure 5.3. Our rules give controller gains that are about 30 % lower
and integration times that are about 50% longer than the values
obtained by the Ziegler-Nichols method. The functions fitted to the
data in Figure 5.3 are given in Table 5.3.
For PI control it appears that reasonable tuning can be based on
formulasforτ=0,andthattherewillbeamodestimprovement from
knowledge
ofτ(cid:8)
. A comparison with Figure 5.1 shows that the curve
for T/L has to be modified a little for small values ofτ.
i
PID Control for Integrating Processes
Figure 5.4 shows the results obtained for PID control of processes
with integration. Notice that the normalized controller parameters
vary significantly withτ(cid:8) in this case. Forthe case M =2 parameter
s
aK varies between 0.8 and 5, parameter T/L is in the range of 1 to
i

5.3 Step-Response Methods 211
aK vs.τ bvs.τ
1 1
0.1 0.1
0 0.5 1 0 0.5 1
Ti/L vs.τ
100
10
1
0 0.5 1
Figure 5.3 Tuning diagrams for PI control for processes with
integration. Controller parameters are obtained by applying domi-
nantpoledesignwithM =1.4,markedwith ○ ,andM =2,marked
s s
with (cid:14) to the systems in the test batch (5.1) complemented with
an integrator. The dashed lines correspond to the Ziegler-Nichols
tuning rule.
Table 5.3 Tuning formula for PI control obtained by the step-
response method for processes with integration. The table gives
parameters of functions of the form f(τ) = a exp(aτ+aτ2) for
0 1 2
the normalized controller parameters.
M =1.4 M =2.0
s s
a a a a a a
0 1 2 0 1 2
aK 0.41 −0.23 0.019 0.81 −1.1 0.76
T/L 5.7 1.7 −0.69 3.4 0.28 −0.0089
i
b 0.33 2.5 −1.9 0.78 −1.9 1.2

| 212 | Chapter | 5 New | Tuning Methods |     |     |     |     |     |
| --- | ------- | ----- | -------------- | --- | --- | --- | --- | --- |
/L
3.5, and T d is in the range of 0.25 to 0.4. There are even larger
variations for M =1.4. To obtain good PID control of processes with
s
| integration | it is | therefore | essential | to knowτ(cid:8) | .   |     |     |     |
| ----------- | ----- | --------- | --------- | --------------- | --- | --- | --- | --- |
The controller parameters obtained by the Ziegler-Nichols rule
areshown withdashed lines inthefigure. Itisinteresting toobserve
that the gain given by our rules is larger and the integration time is
smallτ(cid:8)
| smaller | for | . The | parameters | obtained |     | when | fitting functions |     |
| ------- | --- | ----- | ---------- | -------- | --- | ---- | ----------------- | --- |
of the form (5.3) to the data are given in Table 5.4. The ratio T/T
|     |     |     |     |          |     |     |     | i d |
| --- | --- | --- | --- | -------- | --- | --- | --- | --- |
|     |     |     |     | τ(cid:8) |     | =   |     |     |
varies significantly with parameter . For M 2 it increases from
s
2.5forτ(cid:8) =0to12forτ(cid:8) =1.Thevariations intheratioisevenlarger
=1.4.
| for designs | with | M s |     |     |     |     |     |     |
| ----------- | ---- | --- | --- | --- | --- | --- | --- | --- |
Summary
The results show that for PI control we can obtain tuning formulas
basedonτthatcanbeapplied
|     |     |     | alsotoprocesses |     |     | withintegration. |     | The |
| --- | --- | --- | --------------- | --- | --- | ---------------- | --- | --- |
formulas are obtained simply by extending the formulas for stable
processes to τ= 0. A small improvement can be obtained for small
|        | ofτby |             |     | parameterτ(cid:8) |     |     |     |     |
| ------ | ----- | ----------- | --- | ----------------- | --- | --- | --- | --- |
| values | also  | determining |     |                   | .   |     |     |     |
For PID control it is necessary to have separate tuning formulas
forstableprocessesandprocesseswithintegration.Forprocesseswith
integration good tuning cannot be obtained by tuning formulas that
are only based on parameter τ. It is necessary to provide additional
theparameterτ(cid:8)
| information, | e.g.,byproviding |     |     |     |     | .Thetuning | formulas |     |
| ------------ | ---------------- | --- | --- | --- | --- | ---------- | -------- | --- |
derived for processes with integration can also be applied whenτis
| small, | sayτ<0.2,          | which | corresponds | to  | T >4L.  |     |     |     |
| ------ | ------------------ | ----- | ----------- | --- | ------- | --- | --- | --- |
| 5.4    | Frequency-Response |       |             |     | Methods |     |     |     |
In this section, the tuning rules based on frequency-domain methods
aredeveloped. Inthetradition of Ziegler andNichols wecharacterize
the process by the ultimate gain K , the ultimate period T , and the
|            |     |            |          | u     |         |     | u              |        |
| ---------- | --- | ---------- | -------- | ----- | ------- | --- | -------------- | ------ |
|            | κ = | 1/K        | (Compare |       |         | 2.) |                |        |
| gain ratio |     | p          | K u .    | with  | Chapter |     | The controller |        |
| parameters | are | normalized | as K/K   | , T/T | and     | T   | /T . The       | tuning |
|            |     |            |          | u     | i u     | d   | u              |        |
rules are obtained in the same way as for the step-response method.
Controllers for the different processes are designed using the domi-
nant pole design with two values of the design parameter, M = 1.4
s
=2.Ithasthen
| and M | s   |     | beenattempted | tofindrelations |     |     | between | the |
| ----- | --- | --- | ------------- | --------------- | --- | --- | ------- | --- |
normalized controller parametersandthenormalized processparam-
eters. The results can be conveniently represented as graphs where
normalized controller parameters are given as functions of the gain
ratioκ.

|     |     |      | 5.4 | Frequency-Response |     | Methods |     | 213 |
| --- | --- | ---- | --- | ------------------ | --- | ------- | --- | --- |
|     | aK  | vs.τ |     |                    |     | bvs.τ   |     |     |
10
1
1
0.1
0.1
| 0   | 0.5  |      | 1   | 0   |     | 0.5       |     | 1   |
| --- | ---- | ---- | --- | --- | --- | --------- | --- | --- |
|     | Ti/L | vs.τ |     |     |     | Td/L vs.τ |     |     |
10
10
1
1
0.1
| 0      | 0.5        |          | 1   | 0   |         | 0.5          |      | 1   |
| ------ | ---------- | -------- | --- | --- | ------- | ------------ | ---- | --- |
| Figure | 5.4 Tuning | diagrams | for | PID | control | of processes | with |     |
integration. Controller parameters are obtained by applying domi-
|                     |          |            | =1.4,markedwith |       | ○            | =2,marked |      |     |
| ------------------- | -------- | ---------- | --------------- | ----- | ------------ | --------- | ---- | --- |
| nantpoledesignwithM |          | s          |                 |       | ,andM        | s         |      |     |
|                     | (cid:14) |            |                 |       | (5.1)        |           |      |     |
| with                | to the   | systems in | the test        | batch | complemented |           | with |     |
an integrator. The dashed lines correspond to the Ziegler-Nichols
tuning rule.
| Table | 5.4 Tuning | formula | for | PID control | based | on  | the step- |     |
| ----- | ---------- | ------- | --- | ----------- | ----- | --- | --------- | --- |
response method for processes with integration. The table gives
| parameters     | of  | functions  | of the form | f(τ) | = a exp(aτ+aτ2) |      | for |     |
| -------------- | --- | ---------- | ----------- | ---- | --------------- | ---- | --- | --- |
|                |     |            |             |      | 0               | 1    | 2   |     |
| the normalized |     | controller | parameters. |      |                 |      |     |     |
|                |     |            | =1.4        |      | =2.0            |      |     |     |
|                |     | M          | s           |      | M s             |      |     |     |
|                |     | a          | a a         | a    | a               | a    |     |     |
|                |     | 0          | 1 2         | 0    | 1               | 2    |     |     |
|                |     | −8.8       |             |      | −7.1            |      |     |     |
|                | aK  | 5.6        | 6.8         | 8.6  |                 | 5.4  |     |     |
|                | T/L | 1.1        | 6.7 −4.4    | 1.0  | 3.3             | −2.3 |     |     |
i
|     | T /L | 1.7 −6.4 | 2.0 | 0.38 | 0.056 | −0.60 |     |     |
| --- | ---- | -------- | --- | ---- | ----- | ----- | --- | --- |
d
|     |     |      | −6.6 |      | −2.2 |     |     |     |
| --- | --- | ---- | ---- | ---- | ---- | --- | --- | --- |
|     | b   | 0.12 | 6.9  | 0.56 |      | 1.2 |     |     |

214 Chapter 5 New TuningMethods
K/K
u
vs.κ bvs.κ
1 10
0.1 1
0.01 0.1
0 0.5 1 0 0.5 1
T/T vs.κ
i u
1
0.1
0 0.5 1
Figure 5.5 Tuning diagrams for PIcontrolbased on K , T , and
u u
κ. Controller parameters are obtained by applying dominant pole
designwith M =1.4,markedwith ○ ,and M =2,markedwith(cid:14),
s s
to the systems in test batch (5.1). The dashed lines correspond to
the Ziegler-Nichols tuning rule.
Table 5.5 Tuning formula for PI controlbased onthe frequency-
response method. The table gives parameters of functions of the
form f(κ) = a exp(a κ+a κ2) for the normalized controller pa-
0 1 2
rameters.
M =1.4 M =2.0
s s
a a a a a a
0 1 2 0 1 2
K/K 0.053 2.9 −2.6 0.13 1.9 −1.3
u
Ti/Tu 0.90 −4.4 2.7 0.90 −4.4 2.7
b 1.1 −0.0061 1.8 0.48 0.40 −0.17

|              |                 | 5.4 | Frequency-Response | Methods | 215 |
| ------------ | --------------- | --- | ------------------ | ------- | --- |
| PIControlfor | StableProcesses |     |                    |         |     |
Figure 5.5 shows the normalized parameters of a PI controller as a
|     | κ.  |     | =   |     |     |
| --- | --- | --- | --- | --- | --- |
function of Consider the case of M s 2, i.e., the points marked
(cid:14)
in Figure 5.5. The normalized gain ranges from 0.15 to 0.3, the
normalizedintegrationtimefrom0.15to1,andthesetpointweighting
from 0.4 to 0.6. The ranges of variation are smaller than for the
step-response method (compare with Figure 5.1). The variations are,
κ.
however, too large to admit tuning rules that do not depend on
κ,
If we choose tuning rules that do depend on e.g., those shown in
straight lines in Figure 5.5, we can find rules that give controller
|            | within±20%for |            | inthetestbatch(5.1).Ifwe |     |     |
| ---------- | ------------- | ---------- | ------------------------ | --- | --- |
| parameters |               | thesystems |                          |     |     |
are satisfied with less precision it suffices to let the integration time
depend on κ. The behavior for M = 1.4 is similar, but the setpoint
s
| weighting | changes | over a wider range. |     |     |     |
| --------- | ------- | ------------------- | --- | --- | --- |
Thenormalizedcontrollergainandthesetpointweightingdepend
on the design parameter M s , but the same value of the integral time
can be used for all M . This is similar to what we found for the step-
s
response method. A comparison with Figure 5.1 shows that there is
slightly less scatter with the step-response method than with the
| frequency-domain | method. |     |     |     |     |
| ---------------- | ------- | --- | --- | --- | --- |
Thevariationoftheintegrationtimewithκisparticularlynotice-
able in Figure 5.5. This reflects the situation that the proportional
action is larger than integral action for processes that are lag domi-
nant. The reverse situation occurs for processes where the dynamics
| are dominated | by dead | time. |     |     |     |
| ------------- | ------- | ----- | --- | --- | --- |
The Figure 5.5 also shows why Ziegler-Nichols tuning is not very
good in this case. Thecontroller gainis too high for all values of gain
| ratioκ,andtheintegral |     | timeistooshortexceptforverysmallvalues |     |     |     |
| --------------------- | --- | -------------------------------------- | --- | --- | --- |
κ.
of This agrees well with the observation that the Ziegler-Nichols
| rules for | PI control | do not work | well. |     |     |
| --------- | ---------- | ----------- | ----- | --- | --- |
Table5.5givesthecoefficientsoffunctionsoftheform(5.3)fitted
tothedatainFigure5.5.Thecorrespondinggraphsareshowninsolid
| lines in      | the figure.     |     |     |     |     |
| ------------- | --------------- | --- | --- | --- | --- |
| PIDControlfor | StableProcesses |     |     |     |     |
Figure 5.6 shows the normalized parameters of a PID controller as a
|          | ofκ.Consider |              | =2.Thenormalized |     |      |
| -------- | ------------ | ------------ | ---------------- | --- | ---- |
| function |              | thesituation | for M            |     | gain |
s
variesfrom0.45to0.9,thenormalized integral timefrom0.2to0.55,
thederivative timefrom0.06to0.15,andthesetpoint weighting from
0.2 to 0.4. Notice that the ranges are significantly smaller than for
PI control. The situation is similar for M = 1.4, with the exception
s
that the setpoint weighting varies over a larger range in this case.
Thus, it is easier, in this case, to find tuning rules that only depend

| 216 | Chapter | 5 New | Tuning | Methods |     |     |     |     |
| --- | ------- | ----- | ------ | ------- | --- | --- | --- | --- |
on two parameters. With tuning rules based on three parameters it
is,however,possibletofindtuningrulesthatgiveanaccuracyof25%,
| at  | least for | the test batch | (5.1). |     |     |     |     |     |
| --- | --------- | -------------- | ------ | --- | --- | --- | --- | --- |
The figure shows that different values of gain K and setpoint
|           |     |              |       | =1.4and | =2.Thecurves |        |     |     |
| --------- | --- | ------------ | ----- | ------- | ------------ | ------ | --- | --- |
| weighting |     | bareobtained | for   | M       | M            |        | for | the |
|           |     |              |       | s       | s            |        |     |     |
| integral  | and | derivative   | times | do not  | vary so much | with M | .   |     |
s
A comparison with Figure 5.5 shows that the range of parameter
variations with κare much less for PID control than for PI control.
This supports the well-known observation that rules of the Ziegler-
Nichols type work better for PID than for PI control. Figure 5.6 also
| showsthatthenormalized |     |     | gainobtained |     | with M | =2isquitecloseto |     |     |
| ---------------------- | --- | --- | ------------ | --- | ------ | ---------------- | --- | --- |
s
the gain given by the Ziegler-Nichols rule, whereas the integral and
ofκ.
| derivative |     | times are smaller |     | for most | values |     |     |     |
| ---------- | --- | ----------------- | --- | -------- | ------ | --- | --- | --- |
Table 5.6 gives the parameters a , a , and a of functions of the
|     |     |     |     |     | 0 1 | 2   |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
(5.3)
| form |     | fitted to the | data | in Figure | 5.6. |       |     |     |
| ---- | --- | ------------- | ---- | --------- | ---- | ----- | --- | --- |
|      |     | K/K vs.κ      |      |           |      | bvs.κ |     |     |
u
10
1
1
0.1
0.1
| 0   |     | 0.5      |     | 1   | 0   | 0.5     |     | 1   |
| --- | --- | -------- | --- | --- | --- | ------- | --- | --- |
|     |     | T/T vs.κ |     |     |     | /T vs.κ |     |     |
T
|     |     | i u |     |     |     | d u |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
1
1
0.1
0.1
0.01
| 0   |        | 0.5                                    |     | 1   | 0   | 0.5    |       | 1   |
| --- | ------ | -------------------------------------- | --- | --- | --- | ------ | ----- | --- |
|     | Figure | 5.6 TuningdiagramsforPIDcontrolbasedon |     |     |     | K u ,T | u and |     |
κ.
|     | Controller | parameters | are | obtained | by applying | dominant | pole |     |
| --- | ---------- | ---------- | --- | -------- | ----------- | -------- | ---- | --- |
○
design with M =1.4, marked with , and M =2marked with (cid:14),
|     |     | s   |     |     | s   |     |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
to the systems in test batch (5.1). The dashed lines correspond to
|     | the Ziegler-Nichols |     | tuning | rule. |     |     |     |     |
| --- | ------------------- | --- | ------ | ----- | --- | --- | --- | --- |

5.4 Frequency-Response Methods 217
Table 5.6 TuningformulaforPIDcontrolbasedonthefrequency-
response method. The table gives parameters of functions of the
form f(κ) = a exp(a κ+a κ2) for the normalized controller pa-
0 1 2
rameters.
M =1.4 M =2.0
s s
a a a a a a
0 1 2 0 1 2
K/K 0.33 −0.31 −1.0 0.72 −1.6 1.2
u
T/T 0.76 −1.6 −0.36 0.59 −1.3 0.38
i u
T /T 0.17 −0.46 −2.1 0.15 −1.4 0.56
d u
b 0.58 −1.3 3.5 0.25 0.56 −0.12
TheRelationBetween T and T
i d
In many tuning rules the ratio of T and T is fixed. In Figure 5.7
i d
we show the ratio of T/T obtained with the new tuning rules. The
i d
figure shows that the design for M = 2 gives ratios that are close
s
to 4. This is the same ratio as in the Ziegler-Nichols method. For
M = 1.4, the ratio is close to 4 for κ< 0.6. For higher values of κ
s
the ratio becomes larger.
Processeswith Integration
For integrating processes, the ultimate gain and the ultimate period
can be determined as described in Section 2.6, but static gain K is
p
not defined. Processes with integration have κ=0. For PI control it
is possible to extrapolate the previous formulas toκ=0 but for PID
control itis necessary to have additional information. One possibility
is to provide information about other points on the Nyquist curve of
the process. A good choice isω , i.e., the frequency where the phase
90
T/T
i d
6
4
2
κ
0
0 0.2 0.4 0.6 0.8 1
Figure 5.7 Ratio of T to T obtained with the new tuning rule
i d
based on frequency response. The full line corresponds to M = 2
s
and the dotted line to M = 1.4. The dashed line shows the ratio
s
givenby theZiegler-Nichols methods T/T =4.
i d

| 218       | Chapter  | 5 New | Tuning  | Methods |           |     |     |
| --------- | -------- | ----- | ------- | ------- | --------- | --- | --- |
| lag is 90 | ○ .      |       |         |         |           |     |     |
| 5.5       | Complete |       | Process |         | Knowledge |     |     |
ThemethodspresentedinSections5.3and5.4areapproximatemeth-
ods based on partial knowledge of the process. These methods are
sufficient in many cases. There are, however, situations where more
accuracy is required. This can be achieved either by on-line refine-
ment or by using a more accurate model. There are many empirical
rules for on-line tuning that can be refined further by selecting dif-
ofτorκ.
| ferent rule | sets     | depending | on  | the values |          |                 |       |
| ----------- | -------- | --------- | --- | ---------- | -------- | --------------- | ----- |
| A more      | accurate | model     | can | be         | obtained | by using system | iden- |
tification. This will typically give a model in the form of a pulse
transfer function. This model can be transformed into an ordinary
transfer function in several different ways. Since the tuning methods
are based on the transfer function of the process, it is attractive to
use frequency response techniques. The multifrequency method is a
technique where a signal that is a sum of sinusoids is chosen as the
input. The phases of the sinusoids are chosen so that the amplitude
of the signal is minimized. The frequencies chosen can be based on
frequencyω
| theknowledge |     | of the ultimate |     |     |     | .Inthis wayitis | possible |
| ------------ | --- | --------------- | --- | --- | --- | --------------- | -------- |
u
to obtain the value of the transfer function for several frequencies
in one test. A transfer function can then be fitted to the data, and
the dominant pole design technique can then be used. In this sec-
tion we present alternative methods of performing the computations
required for dominant pole design. An alternative to this is to deter-
mine a pulse transfer function by applying the system identification
methods discussed in Section 2.7 and to develop a design procedure
that is based on the pulse transfer function. Such a method can be
obtained using ideas similar to those discussed in this chapter.
PIControl
G(s).
Consider a process with the transfer function Let the PI con-
| troller be | parameterized |     | as  |     |     |     |     |
| ---------- | ------------- | --- | --- | --- | --- | --- | --- |
k
|     |     |     | G   | (s)= k+ | i   |     | (5.4) |
| --- | --- | --- | --- | ------- | --- | --- | ----- |
c
s
In this particular case the design problem can be formulated as fol-
| lows.Findtheparameters |          |                    | kand              | k suchthat |       | k isaslargeaspossible |       |
| ---------------------- | -------- | ------------------ | ----------------- | ---------- | ----- | --------------------- | ----- |
|                        |          |                    |                   | i          |       | i                     |       |
| and so                 | that the | robustness         | constraint        |            |       |                       |       |
|                        |          | (cid:2)1+G(cid:10) | (iω)(cid:2)=a(k,k |            | ,ω)≥m |                       | (5.5) |
|                        |          |                    |                   |            | i     | 0                     |       |

|     |     |         |     | 5.5 | Complete | Process | Knowledge | 219 |
| --- | --- | ------- | --- | --- | -------- | ------- | --------- | --- |
|     |     | = G(s)G | (s) |     |          |         |           |     |
where G(cid:10) c is the loop transfer function. The problem is a
constrained optimization problem that, unfortunately, is not convex.
To solve it we use an iterative method with good initial conditions.
|     | The | idea of the | algorithm            | is  | to evaluate | the | function |       |
| --- | --- | ----------- | -------------------- | --- | ----------- | --- | -------- | ----- |
|     |     |             | m(k,k)=mina(k,k,ω)=m |     |             |     |          | (5.6) |
|     |     |             | i                    |     | i           |     | 0        |       |
ω∈Ω
for several values of the controller parameters and then todetermine
| the | value | of k, which | maximizes |     | k subject | to the | constraint. |     |
| --- | ----- | ----------- | --------- | --- | --------- | ------ | ----------- | --- |
i
Determination of the function m requires minimization with re-
|       |     | ω.      |         |          |        |     |                   | Ω = |
| ----- | --- | ------- | ------- | -------- | ------ | --- | ----------------- | --- |
| spect | to  | This is | done by | a simple | search |     | over the interval |     |
[ω,ω].
1 2
|     | The | function m | can be | locally | approximated |     | by       |     |
| --- | --- | ---------- | ------ | ------- | ------------ | --- | -------- | --- |
|     |     |            |        |         | (cid:20)     |     | (cid:21) |     |
1
|     | m(k,k)=a+b |     | k +b | k+  | c k2+2c |     | kk +c k2 | (5.7) |
| --- | ---------- | --- | ---- | --- | ------- | --- | -------- | ----- |
|     |            | i   | 0 i  | 1   | 2 0     | i 1 | i 2      |       |
Maximizing k with respect to k subject to the constraint (5.6) gives
i
|     |     |     |     | +c  | +c k=0 |     |     | (5.8) |
| --- | --- | --- | --- | --- | ------ | --- | --- | ----- |
b k
|      |       |               |          | 1 1 | i 2     |       |     |     |
| ---- | ----- | ------------- | -------- | --- | ------- | ----- | --- | --- |
| This | gives | the following | relation |     | between | k and | k:  |     |
i
|     |     |     |     |     | b +c k |     |     |       |
| --- | --- | --- | --- | --- | ------ | --- | --- | ----- |
|     |     |     |     | k=− | 1 1    | i   |     | (5.9) |
c
2
Inserting this into Equation (5.7) and using the condition m(k,k)=
i
m 0 gives
|     |     |     | k2+2A |     | +A    | =0  |     | (5.10) |
| --- | --- | --- | ----- | --- | ----- | --- | --- | ------ |
|     |     |     | A 0   |     | 1 k i | 2   |     |        |
i
where
c2
|     |     |     |     | = − | 1   |     |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
A c
|     |     |     | 0   | 0   | c   |     |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
2
|     |     |     |     | = − | b 1 c 1 |     |     |     |
| --- | --- | --- | --- | --- | ------- | --- | --- | --- |
A b
|     |     |     | 1   | 0   | c   |     |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
2
b2
|     |     |     | A   | =2(a | −m )− | 1   |     |     |
| --- | --- | --- | --- | ---- | ----- | --- | --- | --- |
|     |     |     | 2   | 0    | 0     |     |     |     |
c
2
(5.10)
| Solving |     | Equation | gives |     |     |     |     |     |
| ------- | --- | -------- | ----- | --- | --- | --- | --- | --- |
(cid:25)
|     |     |     |     | −A ± | A2−A | A   |     |        |
| --- | --- | --- | --- | ---- | ---- | --- | --- | ------ |
|     |     |     |     | 1    | 1    | 0 2 |     |        |
|     |     |     | k = |      |      |     |     | (5.11) |
|     |     |     | i   |      | A    |     |     |        |
0
Having obtained k the value of k is then given by Equation (5.9).
i
Parameters for PID controllers can be determined in a similar
way.

| 220 | Chapter 5 New | Tuning Methods |       |     |     |
| --- | ------------- | -------------- | ----- | --- | --- |
|     | Ims           |                |       | Ims |     |
| A   |               |                | B     |     |     |
|     | ω             |                |       | ω   |     |
|     | o             |                |       | o   |     |
| −z  | −p            | Res            | −p −z |     | Res |
| o   | o             |                | o o   |     |     |
Figure 5.8 Configuration of dominant poles and zeros for a sys-
temwithPIcontrol.CaseAcorrespondstosystemswheretheopen-
loop poles are clusteredandcase B isthe case when the open-loop
| poles | are widely spread. |                |     |     |     |
| ----- | ------------------ | -------------- | --- | --- | --- |
| 5.6   | Assessment         | of Performance |     |     |     |
In this section we explore some properties of the closed-loop sys-
tems obtained with the design methods discussed in the previous
sections. The closed-loop systems obtained with PID control typically
have many poles and zeros. The behavior of the system is, however,
(Compare
| characterized | by only | a small number | of poles. | with | Fig- |
| ------------- | ------- | -------------- | --------- | ---- | ---- |
ure 4.4.) The key idea with the dominant pole design procedure was
actually to position a few of the dominant poles. In this section we
explore the dominant poles further. In particular we investigate how
they are related to features of the open loop system and the design
parameters.
A preliminary assessment of the nature of the control problem
can be made based on the value of the normalized dead time or the
gainratio.Forsmallvalues(τ<0.1orκ<0.06)itisoftenpossibleto
obtainimprovedcontrol bymorecomplexstrategies thanPIDcontrol.
|           |                 |               | (τ >   | κ      | > 0.7) |
| --------- | --------------- | ------------- | ------ | ------ | ------ |
| Similarly | when the values | are close     | to one | 0.7 or |        |
| consider  | using dead-time | compensation. |        |        |        |
PIControl
Many systems with PI control can be characterized by the closed-
loop poles that are closest to the origin in the complex plane. It is
often sufficient to consider only three closed-loop poles. In a typical
|            |                 |         | (see      | 5.8).  |     |
| ---------- | --------------- | ------- | --------- | ------ | --- |
| case there | are two complex | and one | real pole | Figure | The |
responses of a system with three poles is a linear combination of the

|     |     |     |     | 5.6 | Assessmentof |     | Performance | 221 |
| --- | --- | --- | --- | --- | ------------ | --- | ----------- | --- |
| 1.0 |     | y   |     |     |              |     |             |     |
e
0.5
0.0
|     | 0   | 2   |     | 4   | 6   |     | 8   | 10  |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
y
c
0.5
−0.5
|     | 0   | 2   |     | 4   | 6   |     | 8   | 10  |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
y
s
0.5
−0.5
|     | 0      | 2          |       | 4     | 6      |          | 8         | 10  |
| --- | ------ | ---------- | ----- | ----- | ------ | -------- | --------- | --- |
|     | Figure | 5.9 Signal | modes | for a | system | with one | real pole | and |
one complex pole pair. The modes are a damped exponential y, a
e
|     | damped | cosine y, c and | adamped | sine | function | y. s |     |     |
| --- | ------ | --------------- | ------- | ---- | -------- | ---- | --- | --- |
signals
|     |     |     | y = e −α | 0t  |     |     |     |     |
| --- | --- | --- | -------- | --- | --- | --- | --- | --- |
e
(cid:7)
|     |     |     | = −ζω     | 0tsinω | 1−ζ2     |     |     |     |
| --- | --- | --- | --------- | ------ | -------- | --- | --- | --- |
|     |     |     | y e       |        |          |     |     |     |
|     |     |     | s         |        | 0(cid:7) |     |     |     |
|     |     |     | y = e −ζω | 0tcosω | 1−ζ2     |     |     |     |
|     |     |     | c         |        | 0        |     |     |     |
The signal y is a decaying exponential, y and y are exponentially
|     |     | e   |     |     | s   |     | c   |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
damped sine and cosine functions. The responses may also contain a
component due to the excitation, e.g., a constant for the step distur-
bances. The signals are illustrated in Figure 5.9. The damped sine
andcosine waves areoftenthe dominating components andthe expo-
nential function corresponds to the creeping behavior found on some
occasions.
Sincetheresponsesarewellapproximatedbythefunctionsshown
| inFigure5.9,itiseasytovisualize |     |     |     |     | responses | ifweknowtheparame- |     |     |
| ------------------------------- | --- | --- | --- | --- | --------- | ------------------ | --- | --- |
tersα,ω,andζ,andtheamplitudes
|     | 0   | 0   |     |     | ofthesignals. |     | Theamplitudes |     |
| --- | --- | --- | --- | --- | ------------- | --- | ------------- | --- |
of the different components depend on the parameters and the exci-
| tation | of   | the system in | a fairly | complicated |     | way. |     |     |
| ------ | ---- | ------------- | -------- | ----------- | --- | ---- | --- | --- |
| The    | Real | Pole          |          |             |     |      |     |     |
Therealpoleats=−α
|     |     |     | determines |     | thedecayrateoftheexponential |     |     |     |
| --- | --- | --- | ---------- | --- | ---------------------------- | --- | --- | --- |
0
function. The time constant is T =1/α, whereα is approximately
|     |     |     |     | 0   | 0   |     | 0   |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |

| 222 | Chapter | 5 New | Tuning | Methods |     |     |     |     |
| --- | ------- | ----- | ------ | ------- | --- | --- | --- | --- |
equal to 1/T. This explains the sluggish response obtained when T
|        |        | i            |        |      |     |     |     | i   |
| ------ | ------ | ------------ | ------ | ---- | --- | --- | --- | --- |
| is too | large, | compare with | Figure | 5.9. |     |     |     |     |
For processes, where the open-loop poles are clustered together,
the configuration of the poles is as shown in Figure 5.8A. The pole
|         |     | −α      |        |       |        |      | −z = −1/T. |     |
| ------- | --- | ------- | ------ | ----- | ------ | ---- | ---------- | --- |
| located | in  | is thus | to the | right | of the | zero |            | For |
|         |     | 0       |        |       |        |      | 0          | i   |
systems where the open-loop poles are widely separated, the pole
configuration is as shown in Figure 5.8B, where the real pole is to
the left of the zero −z . The cases can approximately be separated
0
| through | the | inequality |          |     |          |     |     |     |
| ------- | --- | ---------- | -------- | --- | -------- | --- | --- | --- |
|         |     |            | (cid:23) |     | (cid:24) |     |     |     |
(cid:12)n
|     |     | T >2 | L+  | T   | =2(T | −T  | )   | (5.12) |
| --- | --- | ---- | --- | --- | ---- | --- | --- | ------ |
|     |     | 0    |     | k   |      | ar  | 0   |        |
k=1
where T is the time constant associated with the slowest pole (α),
|     | 0   |     |     |     |     |     |     | 0   |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
T k are the time constants associated with the remaining poles, and
|     |        |                   |      | (see |         | 2.4). |                |     |
| --- | ------ | ----------------- | ---- | ---- | ------- | ----- | -------------- | --- |
| T   | is the | average residence | time |      | Section |       | The inequality | is  |
ar
| obtained      | by  | analyzing | the root | locus | of the        | system. |               |     |
| ------------- | --- | --------- | -------- | ----- | ------------- | ------- | ------------- | --- |
| Complex       |     | Poles     |          |       |               |         |               |     |
| Thedampedsine |     | andcosine | modes    |       | aredetermined |         | byparametersω |     |
0
andζ.
|     | The | period of the | oscillation |     | is  |     |     |     |
| --- | --- | ------------- | ----------- | --- | --- | --- | --- | --- |
2π
= (cid:7)
T
|     |     |     | p   | ω   | 1−ζ2 |     |     |     |
| --- | --- | --- | --- | --- | ---- | --- | --- | --- |
0
| and | the ratio | of two successive |     | peaks | are |     |     |     |
| --- | --------- | ----------------- | --- | ----- | --- | --- | --- | --- |
√
|     |     |     | d=  | −2πζ/ | 1−ζ2 |     |     |     |
| --- | --- | --- | --- | ----- | ---- | --- | --- | --- |
e
| (ComparewithSection4.2.)Knowingparametersω |     |     |     |     |     |     | andζ,itisthus |     |
| ------------------------------------------ | --- | --- | --- | --- | --- | --- | ------------- | --- |
0
| easy | to visualize | the shape | of  | the mode. |     |     |     |     |
| ---- | ------------ | --------- | --- | --------- | --- | --- | --- | --- |
If the parameters of the controller are determined by the dom-
inant pole design, we can determine how ω, ζ, and α depend on
|     |     |     |     |     |     | 0   | 0   |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
the system and the specifications. In this way it is possible to relate
theproperties of theclosed-loop system directly tothefeatures of the
process.
ω
To find good relations we use the normalized quantities 0 L and
α T. The relative damping is dimension free by itself. Figure 5.10
0 i
shows the relations obtained for the test batch (5.1). For M =2 the
s
|     | ω   |     |     |     | ζ   |     |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
quantity L ranges from 0.5 to 1.5; ranges from 0.3 to 0.6, and
0
α T from 0.8 to 1.2. The value of ω L is less than one for small τ
| 0   | i   |     |     |     | 0   |     |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
|     | κ   |     |     |     |     |     |     | τ   |
or and larger than one for large values. The variation with or
κis larger for M = 1.4 than for M = 2. For M = 1.4 the relative
|     |     | s   |     |     | s   |     | s   |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
damping depends strongly on τor κ; it is larger than one for large
τor κ.
| values | of  | This | means | that | the closed-loop |     | system | has three |
| ------ | --- | ---- | ----- | ---- | --------------- | --- | ------ | --------- |
real poles. The value ofα T is smaller than one in most cases. This
0 i

|     |        |     | 5.6 Assessment |     | ofPerformance |     | 223 |
| --- | ------ | --- | -------------- | --- | ------------- | --- | --- |
|     | ω vs.τ |     |                |     | ωL vs.κ       |     |     |
L
|             | 0          |        |      |        | 0       |         |     |
| ----------- | ---------- | ------ | ---- | ------ | ------- | ------- | --- |
| 2           |            |        | 2    |        |         |         |     |
| 1           |            |        | 1    |        |         |         |     |
| 0           |            |        | 0    |        |         |         |     |
| 0           | 0.5        |        | 1 0  |        | 0.5     |         | 1   |
|             | ζvs.τ      |        |      |        | ζvs.κ   |         |     |
| 1           |            |        | 1    |        |         |         |     |
| 0.2         |            |        | 0.2  |        |         |         |     |
| 0           | 0.5        |        | 1 0  |        | 0.5     |         | 1   |
|             | αT vs.τ    |        |      |        | αT vs.κ |         |     |
|             | 0 i        |        |      |        | 0 i     |         |     |
| 1           |            |        | 1    |        |         |         |     |
| 0           |            |        | 0    |        |         |         |     |
| 0           | 0.5        |        | 1 0  |        | 0.5     |         | 1   |
| Figure 5.10 | Dependence | ofω,ζ, | andα | on the | system  | charac- |     |
|             |            |        | 0    | 0      |         |         |     |
teristicsandthespecifications M s onclosed-loopsensitivity.Points
|             |              |     | =1.4, |            |        |      | (cid:14) |
| ----------- | ------------ | --- | ----- | ---------- | ------ | ---- | -------- |
| marked with | o correspond | to  | M     | and points | marked | with |          |
s
| correspond | to M =2.0. |     |     |     |     |     |     |
| ---------- | ---------- | --- | --- | --- | --- | --- | --- |
s
indicatesthatthepole-zero configuration showninFigure5.8Aisthe
α
most common case. Figure 5.10 also shows that the quantity 0 T i is
close to one independently of τor κfor M = 2, but that the value
s
| varies significantly | withτorκfor |     | M =1.4. |     |     |     |     |
| -------------------- | ----------- | --- | ------- | --- | --- | --- | --- |
s
By using the relations in Figure 5.10, we can reach a reasonable
estimate of the properties of the closed-loop systems obtained by the

| 224 | Chapter | 5 New | TuningMethods |     |     |     |     |     |     |
| --- | ------- | ----- | ------------- | --- | --- | --- | --- | --- | --- |
Table 5.7 Characterization of the closed-loop poles obtained in
| Example | 5.1. |       |     |      |      |      |           |      |     |
| ------- | ---- | ----- | --- | ---- | ---- | ---- | --------- | ---- | --- |
| α       | τ    | κ     |     | ω    | ζ    | α    | ω         | αT   |     |
|         |      |       | M   |      |      |      | z L       |      |     |
|         |      |       |     | s 0  |      | 0    | 0 0       | 0 i  |     |
| 0.2     | 0.12 | 0.033 | 1.4 | 2.5  | 0.70 | 1.9  | 1.4 0.38  | 1.4  |     |
| 0.5     | 0.25 | 0.15  | 1.4 | 1.0  | 0.70 | 0.93 | 0.97 0.51 | 0.96 |     |
| 0.7     | 0.31 | 0.21  | 1.4 | 0.69 | 0.74 | 0.67 | 0.68 0.57 | 0.81 |     |
| 0.2     | 0.12 | 0.033 | 2.0 | 4.0  | 0.36 | 2.1  | 1.8 0.60  | 1.2  |     |
| 0.5     | 0.25 | 0.15  | 2.0 | 1.3  | 0.35 | 1.0  | 1.02 0.67 | 1.0  |     |
| 0.7     | 0.31 | 0.21  | 2.0 | 0.86 | 0.36 | 0.77 | 0.81 0.71 | 0.94 |     |
design procedures directly from the process characteristics. This is
| illustrated | by       | a simple | example. |          |           |     |     |     |     |
| ----------- | -------- | -------- | -------- | -------- | --------- | --- | --- | --- | --- |
| EXAMPLE     | 5.1      |          |          |          |           |     |     |     |     |
| Consider    | a system | with     | the      | transfer | function. |     |     |     |     |
|             |          | G(s)=    |          |          | 1         |     |     |     |     |
(s+1)(1+αs)(1+α2s)(1+α3s)
In this case it is easy to vary the spread of the process poles by
parameterα.Theprocess
| varying  |       |     |         |           | hasone | dominating | pole | withtime |     |
| -------- | ----- | --- | ------- | --------- | ------ | ---------- | ---- | -------- | --- |
| constant | T =1. | The | average | residence |        | time is    |      |          |     |
0
|     |     |     | T   | =1+α+α2+α3 |     |     |     |     |     |
| --- | --- | --- | --- | ---------- | --- | --- | --- | --- | --- |
ar
(5.12)
Thus, the inequality gives the value where the poles are con-
sidered as clustered to a=0.3425. In Table 5.7 we summarize some
parameters for the system. The table shows that the approximate es-
timates from Figure 5.10 give reasonably good estimates in this case.
Systems with PID control can be analyzed in a similar manner.
In this case it is necessary to consider more closed-loop poles. There
|          |           |               |     |     | 1/T | (cid:8) | 1/T (cid:8) | (cid:8) | (cid:8) |
| -------- | --------- | ------------- | --- | --- | --- | ------- | ----------- | ------- | ------- |
| are also | two zeros | corresponding |     |     | to  | and     | , where     | T and   | T       |
|          |           |               |     |     |     | i       | d           | i       | d       |
are the integral and derivative time constants for the series repre-
| sentation | of the | PID | controller | (compare |     | with | Section 3.4). |     |     |
| --------- | ------ | --- | ---------- | -------- | --- | ---- | ------------- | --- | --- |
5.7 Examples
To illustrate the effectiveness of the tuning methods we apply them
in a few examples.

|     |     |      |     |     |        | 5.7 | Examples | 225 |
| --- | --- | ---- | --- | --- | ------ | --- | -------- | --- |
|     |     | =2.0 |     |     | M =1.4 |     |          |     |
|     | M   |      |     |     | s      |     |          |     |
s
1
M =2.0
|     | M =1.4 |     |     | s   |     |     |     |     |
| --- | ------ | --- | --- | --- | --- | --- | --- | --- |
s
0
| 0   |     | 10  |     | 20  |     | 30  |     | 40  |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
1
−1
| 0   |     | 10  |     | 20  |     | 30  |     | 40  |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
Figure 5.11 Setpoint and load-disturbance response of aprocess
withtransferfunction1/(s+1)3controlledbyaPIDcontrollertuned
| withthenewsimpletuningruleswith |     |     |     |     | M =1.4and2.0.Theupper |     |     |     |
| ------------------------------- | --- | --- | --- | --- | --------------------- | --- | --- | --- |
s
| diagramshowssetpoint |     |     | y   | =1andprocessoutput |     | y,andthelower |     |     |
| -------------------- | --- | --- | --- | ------------------ | --- | ------------- | --- | --- |
sp
| diagram | shows | controlsignal |       | u.   |     |     |     |     |
| ------- | ----- | ------------- | ----- | ---- | --- | --- | --- | --- |
| EXAMPLE | 5.2   | Three         | equal | lags |     |     |     |     |
InExamples 4.1and4.2,theZiegler-Nichols methods wereapplied to
| the process | model |     |     |         |     |     |     |     |
| ----------- | ----- | --- | --- | ------- | --- | --- | --- | --- |
|             |       |     |     | G(s)= 1 |     |     |     |     |
(s+1)3
|                 |     |      | =8, |                 |     | =3.6, |     |            |
| --------------- | --- | ---- | --- | --------------- | --- | ----- | --- | ---------- |
| It has ultimate |     | gain | K u | ultimate period | T   | u     | and | gain ratio |
κ = 0.125. The new frequency-response method gives the following
| parameters | for | a PID | controller: |      |      |     |     |     |
| ---------- | --- | ----- | ----------- | ---- | ---- | --- | --- | --- |
|            |     |       |             | =1.4 | =2.0 |     |     |     |
|            |     |       |             | M    | M    |     |     |     |
|            |     |       |             | s    | s    |     |     |     |
|            |     |       | K           | 2.5  | 4.8  |     |     |     |
|            |     |       | T           | 2.2  | 1.8  |     |     |     |
i
|     |     |     | T   | 0.56 | 0.46 |     |     |     |
| --- | --- | --- | --- | ---- | ---- | --- | --- | --- |
d
|     |     |     | b   | 0.52 | 0.27 |     |     |     |
| --- | --- | --- | --- | ---- | ---- | --- | --- | --- |
The step-response method gives parameters that differ less than
| 10% from | these | values. |     |     |     |     |     |     |
| -------- | ----- | ------- | --- | --- | --- | --- | --- | --- |
Figure 5.11 shows the response of the closed-loop systems to a
step change in setpoint followed by a step change in the load. The
control is significantly better than in Examples 4.1 and 4.2, where
the Ziegler-Nichols methods were used. Compare with Figures 4.7
and 4.8.
| In      | the next | example,      |     | the new design | methods |     | are applied | to a |
| ------- | -------- | ------------- | --- | -------------- | ------- | --- | ----------- | ---- |
| process | with     | a significant |     | dead time.     |         |     |             |      |

| 226 | Chapter | 5 New | Tuning | Methods |     |     |
| --- | ------- | ----- | ------ | ------- | --- | --- |
=2.0
M s
| M   | =2.0 |     |     |     | M =1.4 |     |
| --- | ---- | --- | --- | --- | ------ | --- |
s s
1
=1.4
| 0   | M   | s   |     |     |     |     |
| --- | --- | --- | --- | --- | --- | --- |
| 0   |     |     | 50  |     | 100 | 150 |
1
−1
| 0   |     |     | 50  |     | 100 | 150 |
| --- | --- | --- | --- | --- | --- | --- |
Figure 5.12 Setpoint and load-disturbance response of aprocess
with transfer function e−5s/(s+1)3 controlled by a PID controller
| tunedwiththenewsimpletuningruleswith |     |     |     |     | M =1.4and2.0.The |     |
| ------------------------------------ | --- | --- | --- | --- | ---------------- | --- |
s
| upper | diagram | shows | setpoint | y   | = 1 and process output | y, and |
| ----- | ------- | ----- | -------- | --- | ---------------------- | ------ |
sp
| the     | lower diagram | shows     | controlsignal |     | u.      |     |
| ------- | ------------- | --------- | ------------- | --- | ------- | --- |
| EXAMPLE | 5.3           | Dead-time | dominant      |     | process |     |
The Ziegler-Nichols methods were applied to the process model
e −5s
G(s)=
(s+1)3
in Example 4.4, which showed that the Ziegler-Nichols methods are
τ
not suitable for processes with large normalized dead time and
| largegainratioκ.Theprocess |     |     |     | hasultimate | gain K =1.25,ultimate |     |
| -------------------------- | --- | --- | --- | ----------- | --------------------- | --- |
u
| period | T =15.7,andgainratioκ=0.8.Thenew |     |     |     | frequency-response |     |
| ------ | -------------------------------- | --- | --- | --- | ------------------ | --- |
u
| method | gives | the following | parameters |      | for a PID controller: |     |
| ------ | ----- | ------------- | ---------- | ---- | --------------------- | --- |
|        |       |               | M          | =1.4 | M =2.0                |     |
|        |       |               |            | s    | s                     |     |
|        |       | K             |            | 0.17 | 0.54                  |     |
|        |       | T             |            | 2.6  | 4.2                   |     |
i
|     |     | T   |     | 0.48 | 1.1 |     |
| --- | --- | --- | --- | ---- | --- | --- |
d
|     |     | b   |     | 1.9 | 0.36 |     |
| --- | --- | --- | --- | --- | ---- | --- |
The step-response method gives controller parameters that differ
| less than | 10% | from these | parameters. |     |     |     |
| --------- | --- | ---------- | ----------- | --- | --- | --- |
Figure 5.12 shows the response of the closed-loop systems to a
step change in setpoint followed by a step change in the load. The
control is significantly better than in Example 4.4 (compare with
4.12).The
| Figure |     | new | design | method | gives ahigher gainand | shorter |
| ------ | --- | --- | ------ | ------ | --------------------- | ------- |
integralandderivative timesthantheZiegler-Nichols method.Notice
thatthe value of design parameter M iscrucial inthis example.
s
The next example illustrates the new design method applied on
| an integrating |     | process. |     |     |     |     |
| -------------- | --- | -------- | --- | --- | --- | --- |

5.7 Examples 227
M s =2.0 M s =1.4
1
M =2.0
s
M =1.4
0 s
0 50 100 150
0.2
−0.2
0 50 100 150
Figure 5.13 Setpoint and load-disturbance response of aprocess
with transfer function 1/s(s+1)3 controlled by a PID controller
tunedwiththenewsimpletuningruleswith M =1.4and2.0.The
s
upper diagram shows setpoint y = 1 and process output y, and
sp
the lower diagram shows controlsignal u.
EXAMPLE 5.4 Integrating process
Consider the integrating process
1 1
G(s)= H(s)=
s s(s+1)3
The stable process H(s) has static gain K = 1, apparent dead time
p
L (cid:8) = 0.81, apparent time constant T (cid:8) = 3.7, and relative dead time
τ(cid:8) =0.18. This gives the following parameters for process G(s):
a= K (cid:8)(L (cid:8)+T (cid:8))=4.5
p
L= L (cid:8)+T (cid:8) =4.5
Table 5.4 gives the following PID controller parameters:
M =1.4 M =2.0
s s
K 0.32 0.67
T 14 7.6
i
T 2.6 1.7
d
b 0.33 0.39
Figure5.13showstheresponseoftheclosed-loopsystemstoastep
change in setpoint followed by a step change in the load. The figure
shows that the responses are in accordance with the specifications.

228 Chapter 5 New Tuning Methods
5.8 Conclusions
In this section we have developed new methods for tuning PID con-
trollers.Themethodsarebasedonspecifications intermsofrejection
of load disturbances and measurement noise, sensitivity to model-
ing errors, and setpoint response. Rejection of load disturbances is
the primary design criterion that is optimized by minimizing the in-
tegrated error. Modeling errors are captured by requiring that the
maximum sensitivity be less than a specified value M . This value
s
is a design variable that can be chosen by the user. Reasonable vari-
ables range from M =1.4 to M =2. The standard value is M = 2,
s s s
but smaller values can be chosen if responses without overshoot are
desired.
The method is based on the dominant pole design, wich requires
that the transfer function of the process is known. The methods de-
scribed in this section require the same parameters as the Ziegler-
Nicholsmethods,and,inaddition,κforthefrequencydomainmethod
andτfor the step response method. The tuning method, therefore, is
calledtheKappa-Taumethod ortheKTmethod forshort.Thetuning
method works for processes that are typically encountered in process
control. TheKT-tuning techniques maybeviewed asageneralization
of the Ziegler-Nichols method.
For the step-response method the process is characterized by the
apparent dead time, the apparent time constant, and the static gain.
For the frequency-domain method, the parameters ultimate gain, ul-
timate period, and static gain characterize the process. The tuning
rules areconveniently expressed using the normalized variables gain
ratioκand normalized dead timeτ.
TheKTmethodgivesinsightintotheshortcomingsoftheZiegler-
Nichols rules. First, they avoid the poor damping obtained with the
Ziegler-Nicholsrule.Secondly,theygivegoodtuningalsoforprocesses
with long dead time. The results also show that knowledge about
the gain ratio or the normalized dead time is required for tuning
a PI controller. For PID control with small values of κ and τ, e.g.,
processes withintegration, itisshown thatimproved tuning requires
additionalknowledge.Thiscanbeobtainedfromtheimpulseresponse
of the system. The results admit assessment of the performance that
can be achieved with the new tuning rules based on simple process
characteristics.
5.9 References
The results given in this chapter were motivated by the desire to
obtain tuning rules that are simple and significantly better than the

5.9 References 229
Ziegler-Nichols rules. The chapter is based on the ideas in (Hang
et al., 1991), (Åström et al., 1992). The idea to use dimension-free
parameters was used there. Notice, however, that the definitions of
normalized dead time τ, and gain ratio κ are different. The reason
for making changes is that it is helpful to have parameters that
range from zero toone. Much moreprimitive tuning procedures were
used in the previous work. The dominant pole design, which is the
basis for the work, is given in (Persson, 1992), see also (Persson and
Åström,1992),(PerssonandÅström,1993),and(Persson,1992).The
ideaofusingdimension-free quantitiesforperformanceassessmentis
discussed in (Åström, 1991). They are also useful for an autonomous
controller, see (Åström, 1992).

| Automatic |            |     | Tuning |     |     |
| --------- | ---------- | --- | ------ | --- | --- |
| and       | Adaptation |     |        |     |     |
6.1 Introduction
| Bycombiningthemethodsfordetermination |                                           |     |            | ofprocessdynamics(de- |               |
| ------------------------------------- | ----------------------------------------- | --- | ---------- | --------------------- | ------------- |
| scribedinChapter                      | 2)withthemethodsforcomputingtheparameters |     |            |                       |               |
|                                       | (described                                |     |            | 4),                   |               |
| of a PID                              | controller                                |     | in Chapter | methods               | for automatic |
tuning of PID controllers can be obtained. By automatic tuning (or
auto-tuning)
|     | we mean | a method | where the | controller | is tuned auto- |
| --- | ------- | -------- | --------- | ---------- | -------------- |
matically on demand from a user. Typically the user will either push
a button or send a command to the controller. An automatic tuning
| procedure | consists of | three steps: |     |     |     |
| --------- | ----------- | ------------ | --- | --- | --- |
•
| Generation | of a process | disturbance. |     |     |     |
| ---------- | ------------ | ------------ | --- | --- | --- |
•
| Evaluation | of the | disturbance | response. |     |     |
| ---------- | ------ | ----------- | --------- | --- | --- |
•
| Calculation | of controller | parameters. |     |     |     |
| ----------- | ------------- | ----------- | --- | --- | --- |
This is the same procedure that an experienced operator uses when
tuning a controller manually. The process must be disturbed in some
way in order to determine the process dynamics. This can be done
in many ways, e.g., by adding steps, pulses, or sinusoids to the pro-
cess input. The evaluation of the disturbance response may include a
determination of a process model or a simple characterization of the
response.
Industrial experience hasclearlyindicated thatautomatic tuning
is a highly desirable and useful feature. Automatic tuning is some-
times called tuning on demand or one-shot tuning. Commercial PID
controllers with automatic tuning facilities have only been available
sincethebeginning oftheeighties. Thereareseveral reasonsforthis.
The recent development of microelectronics has made it possible to
incorporate the additional program code needed for the automatic
tuning at a reasonable cost. The interest in automatic tuning at uni-
versitiesisalsoquitenew.Mostoftheresearchefforthasbeendevoted
to the related, but more difficult, problem of adaptive control.
230

6.1 Introduction 231
Automatic tuning can also be performed using external equip-
ment. These devices are connected to the control loop only during
the tuning phase. When the tuning experiment is finished, the prod-
uctssuggestcontrollerparameters.Sincetheseproductsaresupposed
to work together with controllers from different manufacturers, they
must be provided with quite a lot of information about the controller
inordertogiveanappropriateparametersuggestion.Theinformation
required includes controller structure (standard, series, or parallel
form), sampling rate, filter time constants, and units of the different
controllerparameters(gainorproportionalband,minutesorseconds,
time or repeats/time). The fact that PID controllers are parameter-
ized in so many ways creates unnecessary difficulties.
Tuning facilities are also starting to appear in the distributed
control systems. In this case it is possible to have a very powerful
interaction of the user because of the graphics and computational
capabilities available in the system.
Even when automatic tuning devices are used, it is important to
obtain a certain amount of process knowledge. This is discussed in
the next section. Automatic tuning is only one way to use the adap-
tivetechnique. Section 6.3gives anoverview ofseveral adaptive tech-
niques, as well as a discussion about the use of these techniques.
The automatic tuning approaches can be divided into two categories,
namely model-based approaches and rule-based approaches. In the
model-based approaches, amodeloftheprocess isobtained explicitly,
and the tuning is based on this model. Section 6.4 treats approaches
werethe model is obtained from transient response experiments, fre-
quencyresponse experiments, andparameter estimation. Intherule-
basedapproaches,noexplicitprocessmodelisobtained.Thetuningis
based instead on rules similar to those rules that an experienced op-
erator uses to tune the controller manually. The rule-based approach
is treated in Section 6.5.
Some industrial products with adaptive facilities are presented
in Section 6.6. Four single-station controllers are presented: Foxboro
EXACT (760/761), Alfa Laval Automation ECA400, Honeywell UDC
6000,and Yokogawa SLPC-181 and 281. Three tuning packages to be
used within DCS systems, Fisher-Rosemount Intelligent Tuner and
Gain Scheduler, Honeywell Looptune, and ABB DCS Tuner are also
presented, as well as the process analyzer Techmation Protuner.
Adaptive techniques are closely related to diagnosis procedures.
Section 6.7 gives an overview of both manual and automatic on-line
diagnosis procedures. The chapter ends with conclusions and refer-
ences in Sections 6.8 and 6.9

232 Chapter 6 Automatic Tuningand Adaptation
6.2 Process Knowledge
Inthis chapter wewill discuss several methods for automatic tuning.
Before going into details we must remark that poor behavior of a
control loop cannot alwaysbecorrected bytuning the controller. Itis
absolutely necessary to understand the reason for the poor behavior.
The process may be poorly designed so that there are long dead
times,longtimeconstants,nonlinearities,andinverseresponses.Sen-
sors and actuators may be poorly placed or badly mounted, and they
may have bad dynamics. Typical examples are thermocouples with
heavy casings that make their response slow, or on-off valve motors
with long travel time. Valves may be oversized so that they only act
over a small region. The sensor span may be too wide so that poor
resolution isobtained, oritmayalsohave excessive sensor noise. The
procedure of investigating whether a process is well designed from a
control point of view is called loop auditing.
There may also be failure and wear in the process equipment.
Valves may have excessive stiction. There may be backlash due to
wear. Sensors may drift and change their properties because of con-
tamination.
If a control loop is behaving unsatisfactorily, it is essential that
we first determine the reason for this before tuning is attempted. It
would,ofcourse,behighly desirable tohaveaidsfortheprocessengi-
neertodothediagnosis. Automatictuningmayactuallydothewrong
thing if it is not applied with care. For example, consider a control
loop that oscillates because of friction in the actuator. Practically all
tuningdeviceswillattempttostabilizetheoscillation byreducingthe
controller gain. This will only increase the period of the oscillation!
Remember—no amount of so called “intelligence” in equipment
can replace real process knowledge.
6.3 Adaptive Techniques
Techniquesforautomatictuninggrewoutofresearchinadaptivecon-
trol. Adaptation was originally developed to deal with processes with
characteristics that were changing with time or with operating con-
ditions. Practically all adaptive techniques can be used for automatic
tuning. The adaptive controller is simply run until the parameters
haveconvergedandtheparametersarethenkeptconstant.Thedraw-
backwiththisapproachisthatadaptivecontrollersmayrequireprior
information. There are many special techniques that can be used for
this purpose. Industrial experience has shown that this is probably
themostusefulapplicationofadaptivetechniques.Gainschedulingis
alsoaveryeffectivetechniquetocopewithprocessesthatchangetheir

|     |     |     |     | 6.3 | Adaptive | Techniques | 233 |
| --- | --- | --- | --- | --- | -------- | ---------- | --- |
Self-tuning regulator
| Specifications |     |            | Parameter estimates |     |     |            |     |
| -------------- | --- | ---------- | ------------------- | --- | --- | ---------- | --- |
|                |     | Controller |                     |     |     | Parameter  |     |
|                |     | design     |                     |     |     | estimation |     |
Controller
parameter
y
  sp
|     |        | Controller        |     |            |          | Process     |     |
| --- | ------ | ----------------- | --- | ---------- | -------- | ----------- | --- |
|     |        |                   |     | u          |          | y           |     |
|     | Figure | 6.1 Block diagram | of  | anindirect | adaptive | controller. |     |
characteristics with operating conditions. An overview of these tech-
niques will be given in this section. In this book the phrase adaptive
techniqueswillincludeauto-tuning, gainscheduling, andadaptation.
AdaptiveControl
By adaptive control we mean a controller whose parameters are con-
tinuously adjusted to accommodate changes in process dynamics and
disturbances. Adaptation canbeapplied bothtofeedbackandfeedfor-
wardcontrolparameters.Ithasprovenparticularlyusefulforfeedfor-
ward control. The reason for this is that feedforward control requires
good models. Adaptation is, therefore, almost aprerequisite for using
feedforward control. Adaptive control is sometimes called continuous
adaptation to emphasize that parameters are changed continuously.
There are two types of adaptive controllers based on direct and
indirect methods. In a direct method, controller parameters are ad-
justeddirectlyfromdatainclosed-loopoperation.Inindirectmethods,
the parameters of a process model are updated on-line by recursive
(Compare
| parameter |     | estimation. |     | with Section |     | 2.7 where parameter |     |
| --------- | --- | ----------- | --- | ------------ | --- | ------------------- | --- |
estimation wasdiscussed briefly.)Thecontroller parametersarethen
obtained by some method for control design. In direct adaptive con-
trol the parameters of the controller are updated directly. The self-
tuning regulator is a typical example of a direct adaptive controller;
themodelreferencesystem isanexampleofanindirect adaptive con-
troller. There is a large number of methods available both for direct
andindirect methods. They canconveniently bedescribed interms of
| the | methods | used for modeling | and | control | design. |     |     |
| --- | ------- | ----------------- | --- | ------- | ------- | --- | --- |
A block diagram of a direct adaptive controller is shown in Fig-

234 Chapter 6 Automatic Tuning and Adaptation
ure 6.1. There is a parameter estimator that determines the param-
eters of the model based on observations of process inputs and out-
puts.Thereisalsoadesignblockthatcomputescontrollerparameters
from the model parameters. If the system is operated as a tuner, the
process is excited by an input signal. The parameters can either be
estimated recursively or in batch mode. Controller parameters are
computed and the controller is commissioned. If the system is oper-
ated as an adaptive controller, parameters are computed recursively
and controller parameters are updated when new parameter values
are obtained.
AutomaticTuning
Byautomatictuning(orauto-tuning)wemeanamethodwhereacon-
troller is tuned automatically on demand from a user. Typically the
user will either push a button or send a command to the controller.
Industrial experience hasclearly indicated thatthis isahighly desir-
ableanduseful feature. Automatic tuning issometimes called tuning
on demand or one-shot tuning. Auto-tuning can bebuilt into the con-
trollers.Practicallyallcontrollerscanbenefitfromtoolsforautomatic
tuning.Thiswilldrasticallysimplifytheuseofcontrollers.Singleloop
controllers and distributed systems for process control are important
application areas. Most of these controllers are of the PID type. This
is a vast application area because there are millions of controllers of
this type in use. Automatic tuning is currently widely used in PID
controllers.
Auto-tuning canalso beperformed withexternal devices thatare
connected to a process. Since these systems have to work with con-
trollers from different manufacturers, they must be provided with
information about the controller structure in order to give an ap-
propriateparameter suggestion. Suchinformation includes controller
structure (standard, series, or parallel form), sampling rate, filter
timeconstants, andunits ofthedifferent controller parameters (gain
or proportional band, minutes or seconds, time or repeats/time).
GainScheduling
Gain scheduling is a technique that deals with nonlinear processes,
processes with time variations, or situations where the requirements
on the control change with the operating conditions. To use the
techniqueitisnecessarytofindmeasurablevariables,calledschedul-
ing variables, that correlate well with changes in process dynam-
ics. The scheduling variable can be, for instance, the measured sig-
nal, the control signal, or an external signal. For historical reasons
the phrase gain scheduling is used even if other parameters than

6.3 Adaptive Techniques 235
the gain, e.g., derivative time or integral time, are changed. Gain
scheduling is a very effective way of controlling systems whose dy-
namics change with the operating conditions. Gain scheduling has
not been used much because of the effort required to implement it.
When combined with auto-tuning, however, gain scheduling is very
easy to use.
A block diagram of a system with gain scheduling is shown in
Fig. 6.2. The system can be viewed as having two loops. There is an
inner loop, composed of the process and the controller, and an outer
loop, which adjusts the controller parameters based on the operating
conditions.
Thenotionofgainschedulingwasoriginallyusedforflightcontrol
systems, but it is being used increasingly in process control. It is, in
fact, a standard ingredient in some single-loop PID controllers. For
processcontrolapplicationssignificantimprovementscanbeobtained
by using just a few sets of controller parameters.
Gain scheduling is often an alternative to adaptation. It has the
advantage that it can follow rapid changes in the operating condi-
tions. Thekeyproblem istofindsuitable scheduling variables. Possi-
blechoices arethecontrol signal, theprocess variable, oranexternal
signal. Production rate is often a good choice in process control ap-
plications, since time constants and time delays are often inversely
proportional to production rate.
Development ofaschedulemaytakeasubstantialengineering ef-
fort.Theavailability ofautomatic tuning cansignificantly reduce the
effort because the schedules can then be determined experimentally.
A scheduling variable is first determined. Its range is quantitized
into a number of discrete operating conditions. The controller pa-
rameters are then determined by automatic tuning when the sys-
temisrunning inoneoperating condition. Theparameters arestored
in a table. The procedure is repeated until all operating conditions
are covered. In this way it is easy to install gain scheduling into a
Controller
parameters
Table
Scheduling
variable
y
sp
u
Controller Process y
Figure 6.2 Block diagram of asystem withgainscheduling.

| 236 | Chapter 6 | Automatic Tuningand | Adaptation |     |
| --- | --------- | ------------------- | ---------- | --- |
computer-controlled system by programming a table for storing and
recalling controller parameters andappropriate commands toaccom-
plish this.
UsesofAdaptiveTechniques
We have described three techniques that are useful in dealing with
processes that have properties changing with time or with operating
conditions. In Figure 6.3 is a diagram that guides the choice among
| the different | techniques. |     |     |     |
| ------------- | ----------- | --- | --- | --- |
Controller performance is the first thing to consider. If the re-
quirements are modest, a controller with constant parameters and
conservative tuning can be used. With higher demands on perfor-
mance, other solutions should be considered. If the process dynamics
are constant, a controller with constant parameters should be used.
The parameters of the controller can be obtained using auto-tuning.
If the process dynamics or the nature of the disturbances are
changing,itisusefultocompensateforthesechangesbychangingthe
controller. If the variations can be predicted from measured signals,
gain scheduling should be used because it is simpler and gives su-
perior and more robust performance than the continuous adaptation.
Typical examples are variations caused by nonlinearities in the con-
trol loop. Auto-tuning can be used to build up the gain schedules.
There are also cases where the variations in process dynamics
Process dynamics
|     |                       | Varying | Constant              |     |
| --- | --------------------- | ------- | --------------------- | --- |
|     | Use a controller with |         | Use a controller with |     |
|     | varying parameters    |         | constant parameters   |     |
|     | Unpredictable         |         | Predictable           |     |
|     | variations            |         | variations            |     |
Use an adaptive
Use gain scheduling
controller
|     | Figure 6.3 | When touse | different adaptive | techniques. |
| --- | ---------- | ---------- | ------------------ | ----------- |

6.4 Model-BasedMethods 237
are not predictable. Typical examples are changes due to unmeasur-
able variations in raw material, wear, fouling etc. These variations
cannot be handled by gain scheduling, since no scheduling variable
is available, but must be dealt with by adaptation. An auto-tuning
procedure is often used to initialize the adaptive controller. Itis then
sometimes called pre-tuning or initial tuning.
Feedforwardcontroldeservesspecialmentioning.Itisaverypow-
erful method for dealing with measurable disturbances. Use of feed-
forward control, however, requires good models of process dynamics.
It is difficult to tune feedforward control loops automatically on de-
mand, since the operator often cannot manipulate the disturbance
used for the feedforward control. To tune the feedforward controller
it is necessary to wait for an appropriate disturbance. Adaptation,
therefore, is particularly useful for the feedforward controller.
6.4 Model-Based Methods
This section gives an overview of automatic tuning approaches that
arebased on an explicit derivation of a process model. Models can be
obtained in many ways, as seen in Chapter 2. In this section we dis-
cuss approaches based on transient responses, frequency responses,
and parameter estimation.
TransientResponseMethods
Auto-tuners can be based on open-loop or closed-loop transient re-
sponseanalysis.Methodsfordeterminingthetransientresponsewere
discussedinSection2.3.Themostcommonmethodsarebasedonstep
or pulse responses, but there are also methods that can use many
other types of perturbations.
Open-Loop Tuning
A simple process model can be obtained from an open-loop transient
responseexperiment.Asteporapulseisinjectedattheprocessinput,
and the response is measured. To perform such an experiment, the
processmustbestable.Ifapulsetestisused,theprocessmayinclude
anintegrator. Itisnecessary thattheprocessbeinequilibrium when
the experiment is begun.
There are, in principle, only one or two parameters that must
be set a priori, namely the amplitude and the signal duration. The
amplitude should be chosen sufficiently large, so that the response
is easily visible above the noise level. On the other hand, it should

| 238 Chapter | 6 Automatic |     | Tuningand | Adaptation |     |     |     |     |
| ----------- | ----------- | --- | --------- | ---------- | --- | --- | --- | --- |
be as small as possible in order not to disturb the process more than
necessary and to keep the dynamics linear. The noise level can be
determined automatically atthe beginning of the tuning experiment.
However, even ifthenoise level isknown, wecannotdecide asuitable
magnitude ofastepinthecontrol signal without knowing thegainof
the process. Therefore, it must be possible for the operator to decide
the magnitude.
| The duration | of the | experiment |     | is  | the second | parameter |     | that |
| ------------ | ------ | ---------- | --- | --- | ---------- | --------- | --- | ---- |
normally is set a priori. If the process is unknown, it is very difficult
todetermine whether a step response has settled or not. An intuitive
approach is to say that the measurement signal has reached its new
steady state if its rate of change is sufficiently small. The rate of
changeisrelated,however,tothetimeconstantsoftheprocess,which
areunknown. If a pulse test is used, the duration of the pulse should
| also be related                                     | to the | process | time | constants. |     |     |     |      |
| --------------------------------------------------- | ------ | ------- | ---- | ---------- | --- | --- | --- | ---- |
| Manymethodscanbeusedtoextractprocesscharacteristics |        |         |      |            |     |     |     | from |
a transient response experiment. Most auto-tuners determine the
static gain,the dominant timeconstant, andtheapparent deadtime.
The static gain is easy to find accurately from a step-response exper-
iment by comparing the stationary values of the control signal and
the measurement signal before and after the step change. The time
(see
constant and the dead time canbe obtained in several ways Sec-
2.3).
| tion | The method | of moments, |     | presented | in  | Section | 2.4, | is an |
| ---- | ---------- | ----------- | --- | --------- | --- | ------- | ---- | ----- |
appealing method, which is relatively insensitive to high-frequency
disturbances.
The transient response methods are often used in a pre-tuning
mode in more complicated tuning devices. The main advantage of
the methods, namely that they require little prior knowledge, is then
exploited. It is also easy to explain the methods to plant personnel.
| Themaindrawbackwiththe |     |     | transient | response | methods |     | isthatthey |     |
| ---------------------- | --- | --- | --------- | -------- | ------- | --- | ---------- | --- |
aresensitive todisturbances. This drawback is less important if they
| are used only | in the pre-tuning |     | phase. |     |     |     |     |     |
| ------------- | ----------------- | --- | ------ | --- | --- | --- | --- | --- |
| Closed-Loop   | Tuning            |     |        |     |     |     |     |     |
Automatic tuning based on transient response identification can also
be performed on line. The steps or pulses are then added either to
the setpoint or to the control signal. There are also auto-tuners that
donot introduce anytransient disturbances. Perturbations caused by
setpointchangesorloaddisturbancesareusedinstead.Inthesecases
it is necessary to detect that the perturbations are sufficiently large
| compared    | to the noise | level.  |        |     |         |            |     |      |
| ----------- | ------------ | ------- | ------ | --- | ------- | ---------- | --- | ---- |
| Closed-loop | tuning       | methods | cannot |     | be used | on unknown |     | pro- |
cesses. Some kind of pre-tuning must always be performed in order
toclose theloop in asatisfactory way.Onthe other hand, they donot
usuallyrequireanyadditional aprioriinformation. Themagnitude of

|     |     |     | 6.4 Model-BasedMethods |     | 239 |
| --- | --- | --- | ---------------------- | --- | --- |
y
|    sp |     |     | u   |     |  y  |
| ----- | --- | --- | --- | --- | --- |
Σ
Process
PID
−1
| Figure              | 6.4 The relayauto-tuner.Inthetuning |           |     | modetheprocess |     |
| ------------------- | ----------------------------------- | --------- | --- | -------------- | --- |
| is connectedtorelay |                                     | feedback. |     |                |     |
the step changes in setpoint are easily determined from the desired,
| or accepted, | change in | the measurement | signal. |     |     |
| ------------ | --------- | --------------- | ------- | --- | --- |
Since a proper closed-loop transient response is the goal for the
design, it is appealing to base tuning on closed-loop responses. It is
easytogivedesignspecifications intermsoftheclosed-loop transient
response, e.g., damping, overshoot, closed-loop time constants, etc.
The drawback is that the relation between these specifications and
the PID parameters is normally quite involved. Heuristics and logic
| are required | therefore. |     |     |     |     |
| ------------ | ---------- | --- | --- | --- | --- |
FrequencyResponseMethods
There are also auto-tuners that are based on frequency response
methods. In Section 2.5, it was shown how frequency response tech-
| niques could | be used to   | determine | process dynamics. |     |     |
| ------------ | ------------ | --------- | ----------------- | --- | --- |
| Use of the   | Relay Method |           |                   |     |     |
In traditional frequency response methods, the transfer function of
a process is determined by measuring the steady-state responses to
sinusoidal inputs. A difficulty with this approach is that appropri-
ate frequencies of the input signal must be chosen a priori. A special
method, where an appropriate frequency of the input signal is gener-
atedautomatically, wasdescribedinSection2.5.Theidea wassimply
to introduce a nonlinear feedback of the relay type in order to gen-
erate a limit cycle oscillation. With an ideal relay the method gives
an input signal to the process with a period close to the ultimate
| frequency | of the open-loop | system. |     |     |     |
| --------- | ---------------- | ------- | --- | --- | --- |
A block diagram of an auto-tuner based on the relay method is
shown in Figure 6.4. Notice that there is a switch that selects ei-
ther relay feedback or ordinary PID feedback. When it is desired to
tune the system, the PID function is disconnected and the system is
connected to relay control. The system then starts to oscillate. The

240 Chapter 6 Automatic Tuning and Adaptation
periodandtheamplitudeoftheoscillationisdeterminedwhensteady-
state oscillation is obtained. This gives the ultimate period and the
ultimate gain. The parameters of a PID controller can then be de-
termined from these values, e.g., using the Ziegler-Nichols frequency
response method. The PID controller is then automatically switched
in again, and the control is executed with the new PID parameters.
This tuning device has one parameter that must be specified in
advance, namely, the initial amplitude of the relay. A feedback loop
from measurement of the amplitude of the oscillation to the relay
amplitude canbeusedtoensure thattheoutput iswithin reasonable
bounds during the oscillation. Itisalso useful tointroduce hysteresis
in the relay. This reduces the effects of measurement noise and also
increases the period of the oscillation. With hysteresis there is an
additional parameter. This can be set automatically, however, based
ona determination of the measurement noise level. Notice that there
is no need to know time scales a priori since the ultimate frequency
is determined automatically.
In the relay method, an oscillation with suitable frequency is
generated by a static nonlinearity. Even the order of magnitude of
the time constant of the process can be unknown. Therefore, this
method is not only suitable as a tuning device; it can also be used in
pre-tuning. It is also suitable for determination of sampling periods
in digital controllers.
The relay tuning method also can be modified to identify several
points on the Nyquist curve. This can be accomplished by making
several experiments with different values of the amplitude and the
hysteresis of the relay. A filter with known characteristics can also
be introduced in the loop to identify other points on the Nyquist
curve.Ifthe static process gainisdetermined, theKTtuning method
presented in Chapter 5 can be used.
On-Line Methods
Frequencyresponseanalysiscanalsobeusedforon-linetuningofPID
controllers. The relay feedback technique can be used, as described
in Section 2.5. By introducing bandpass filters, the signal content
at different frequencies can be investigated. From this knowledge, a
process model given in terms of points on the Nyquist curve can be
identified on line. In this auto-tuner the choice of frequencies in the
bandpass filters is crucial. This choice can be simplified by using the
tuning procedure described above in a pre-tuning phase.

6.5 Rule-BasedMethods 241
ParameterEstimationMethods
Acommontuning procedure istouse recursive parameter estimation
to determine a low-order discrete time model of the process. The
| parametersofthelow-ordermodelobtained |     |     | arethenusedinadesign |
| ------------------------------------- | --- | --- | -------------------- |
scheme to calculate the controller parameters. An auto-tuner of this
type can also be operated as an adaptive controller that changes the
controller parameters continuously. Auto-tuners based on this idea,
| therefore, | often have an | option for continuous | adaptation. |
| ---------- | ------------- | --------------------- | ----------- |
Themainadvantageofauto-tunersofthistypeisthattheydonot
require any specific type of excitation signal. The control signal can
| beasequencyofmanualchangesofthecontrolsignal, |     |     | forexample,or |
| --------------------------------------------- | --- | --- | ------------- |
thesignals obtained during normaloperation. Adrawbackwithauto-
tuners of this type is that they require significant prior information.
A sampling period for the identification procedure must be specified;
it should be related to the time constants of the closed-loop system.
Sincetheidentification isperformed online,acontroller thatatleast
manages to stabilize the system is required. Systems based on this
identification procedure needapre-tuning phase,whichcanbebased
| on the methods | presented | earlier in this section. |     |
| -------------- | --------- | ------------------------ | --- |
| 6.5 Rule-Based |           | Methods                  |     |
This section treats automatic tuning methods that do not use an
explicit model of the process. Tuning is based instead on the idea
of mimicking manual tuning by an experienced process engineer.
Controller tuning is a compromise between the requirement for
fast control and the need for stable control. Table 6.1 shows how
stability and speed change when the PID controller parameters are
changed. Note that the table only contains rules of thumb. There
are exceptions. For example, an increased gain often results in more
stable control when the process contains an integrator. The same
rules can also be illustrated in tuning maps. See, for example, the
| tuning map | for PI control | in Figure 4.13. |     |
| ---------- | -------------- | --------------- | --- |
Table 6.1 Rules ofthumbfor the effectsof thecontroller param-
| etersonspeed | and stability | inthe controlloop. |           |
| ------------ | ------------- | ------------------ | --------- |
|              |               | Speed              | Stability |
|              | K increases   | increases          | reduces   |
|              | T increases   | reduces            | increases |
i
|     | T increases | increases | increases |
| --- | ----------- | --------- | --------- |
d

| 242 Chapter | 6 Automatic | Tuning | and Adaptation |     |     |
| ----------- | ----------- | ------ | -------------- | --- | --- |
y sp
1
0.5 y
0
| 0   | 10  | 20  | 30  | 40  | 50  |
| --- | --- | --- | --- | --- | --- |
1
u
0.5
0
| 0                                          | 10                                                 | 20  | 30  | 40           | 50  |
| ------------------------------------------ | -------------------------------------------------- | --- | --- | ------------ | --- |
| Figure                                     | 6.5 Asetpointresponsewhereacorrectruleistoincrease |     |     |              |     |
| thegainanddecreasetheintegraltime.Theupper |                                                    |     |     | diagramshows |     |
setpoint y sp and process output y, and the lower diagram shows
| controlsignal | u.  |     |     |     |     |
| ------------- | --- | --- | --- | --- | --- |
The rule-based automatic tuning procedures wait for transients,
| setpoint changes,orloaddisturbances, |     |     | inthesamewayasthemodel- |     |     |
| ------------------------------------ | --- | --- | ----------------------- | --- | --- |
based methods. When such a disturbance occurs, the behavior of
the controlled process is observed. If the control deviates from the
specifications, the controller parameters are adjusted based on some
rules.
Figures 6.5 and 6.6show setpoint changes of control loops with a
poorlytunedPIcontroller.TheresponseinFigure6.5isverysluggish.
Here,acorrectruleistoincreasethegainandtodecreasetheintegral
| time.Figure6.6alsoshowsasluggish |     |     | response | becauseofatoolarge |     |
| -------------------------------- | --- | --- | -------- | ------------------ | --- |
integral time. The response is also oscillatory because of a too high
gain. A correct rule, therefore, is to decrease both the gain and the
integral time.
| Ifgraphs | like those | inFigures | 6.5and6.6areprovided, |     | itiseasy |
| -------- | ---------- | --------- | --------------------- | --- | -------- |
for an experienced operator to apply correct rules for controller tun-
ing. To obtain a rule-based automatic tuning procedure, the graphs
mustbereplaced byquantities thatcharacterize theresponses. Com-
monly used quantities are overshoot and decay ratio to characterize
the stability of the control loop, and time constant and oscillation
| frequency | to characterize | the speed | of the control | loop. |     |
| --------- | --------------- | --------- | -------------- | ----- | --- |
It is rather easy to obtain relevant rules that tell whether the
different controller parameters should be decreased or increased.
However, it is more difficult to determine how much they should
be decreased or increased. The rule-based methods are, therefore,
more suitable for continuous adaptation where rather small succes-
sive changes in the controller parameters are performed after each
transient.
The rule-based methods have a great advantage compared to the

|     |     | 6.6 | CommercialProducts | 243 |
| --- | --- | --- | ------------------ | --- |
y sp
1
0.5 y
0
| 0   | 10  |     | 20  | 30  |
| --- | --- | --- | --- | --- |
1
u
0.5
0
| 0                                          | 10                                                 |     | 20           | 30  |
| ------------------------------------------ | -------------------------------------------------- | --- | ------------ | --- |
| Figure                                     | 6.6 Asetpointresponsewhereacorrectruleistodecrease |     |              |     |
| thegainanddecreasetheintegraltime.Theupper |                                                    |     | diagramshows |     |
setpoint y sp and process output y, and the lower diagram shows
| controlsignal | u.  |     |     |     |
| ------------- | --- | --- | --- | --- |
model-based approaches when they are used for continuous adapta-
tion, namely, that they handle load disturbances efficiently and in
the same way as setpoint changes. The model-based approaches are
well suited for setpoint changes. However, when a load disturbance
occurs, the transient response is caused by an unknown input signal.
Toobtainaninput-output process modelunder suchcircumstances is
not so easy.
A drawback with the rule-base approaches is that they normally
assume that the setpoint changes or load disturbances are isolated
steps or pulses. Two setpoint changes or load disturbances applied
shortly after each other may result in a process output that invokes
| an erroneous   | controller tuning | rule. |     |     |
| -------------- | ----------------- | ----- | --- | --- |
| 6.6 Commercial | Products          |       |     |     |
In this section, some industrial products with automatic tuning fa-
cilities will be presented. Four controllers are presented; the Foxboro
EXACT (760/761), which uses step-response analysis for automatic
tuning, and pattern recognition technique and heuristic rules for its
adaptation;theAlfaLavalAutomationECA400controller,whichuses
relay auto-tuning and model-based adaptation; the Honeywell UDC
6000controller, which uses step-response analysis for automatic tun-
ing and a rule base for adaptation; and the Yokogawa SLPC-181 and
281, which use step-response analysis for auto-tuning and a model-
based adaptation.
Four tuning devices are also described. Intelligent Tuner and

| 244 Chapter | 6 Automatic | Tuning | and Adaptation |     |     |
| ----------- | ----------- | ------ | -------------- | --- | --- |
Gain Scheduler is a software package used in distributed control
| systemsbyFisher-Rosemount. |     | Looptuneisatuningprogrampackage |     |     |     |
| -------------------------- | --- | ------------------------------- | --- | --- | --- |
to be used within the DCS system Honeywell TDC 3000. DCS Tuner
isasoftwarepackageforcontrollertuningintheABBMastersystem.
TheTechmationProtunerisaprocessanalyzer,thatisonlyconnected
| to the control | loop | during the tuning | and analyzing | phase. |     |
| -------------- | ---- | ----------------- | ------------- | ------ | --- |
FoxboroEXACT(760/761)
The single-loop adaptive controller EXACT was released by Foxboro
in October 1984. The reported application experience in using this
controllerhasbeenfavorable.Theadaptivefeaturesarealsoavailable
in DCS products.
| Process Modeling |     |     |     |     |     |
| ---------------- | --- | --- | --- | --- | --- |
Foxboro’ssystem isbasedonthedetermination ofdynamic character-
istics from a transient, which results in a sufficiently large error. If
the controller parameters are reasonable, a transient error response
of the type shown in Figure 6.7 is obtained. Heuristic logic is used to
detect that a proper disturbance has occurred and todetect peaks e ,
1
| e 2 , e 3 , and       | oscillation | period T p .                      |     |     |     |
| --------------------- | ----------- | --------------------------------- | --- | --- | --- |
| Control Design        |             |                                   |     |     |     |
| Theuserspecifications |             | aregivenintermsofmaximumovershoot |     |     | and |
| maximum               | damping.    | They are defined                  | as  |     |     |
e −e
|     |     | damping= | 3 2 |     |     |
| --- | --- | -------- | --- | --- | --- |
−e
e
|     |     |     | (cid:11) 1 (cid:11) 2 |     | (6.1) |
| --- | --- | --- | --------------------- | --- | ----- |
(cid:11) (cid:11)
=(cid:11) e 2(cid:11)
overshoot
(cid:11) (cid:11)
e
1
forbothsetpoint changesandloaddisturbances. Notethatthedefini-
tion of damping here is different from the damping factor associated
| with a standard | second-order | system. |     |     |     |
| --------------- | ------------ | ------- | --- | --- | --- |
The controller structure is of the series form. From the response
to a setpoint change or a load disturbance, the actual damping and
overshoot pattern of the error signal is recognized, and the period
of oscillation T measured. This information is used by the heuristic
p
rules to directly adjust the controller parameters to give the speci-
fied damping and overshoot. Examples of heuristics are to decrease
proportional band PB,integral time T andderivative time T ,if dis-
|     |     |     | i   |     | d   |
| --- | --- | --- | --- | --- | --- |
tinct peaks arenot detected. Ifdistinct peaks have occurredand both
damping and overshoot are less than the maximum values, PB is
decreased.

|     |     |     |     |     | 6.6 | CommercialProducts |     | 245 |
| --- | --- | --- | --- | --- | --- | ------------------ | --- | --- |
Error
e
1
e
3
t
e
2
Error
e
1
e
3
t
e
2
T
    p
Figure 6.7 Response to a step change of setpoint (upper curve)
| and   | load        | (lower | curve). |            |     |     |     |     |
| ----- | ----------- | ------ | ------- | ---------- | --- | --- | --- | --- |
| Prior | Information |        | and     | Pre-Tuning |     |     |     |     |
The controller has a set of required parameters that must be given
either by the user from prior knowledge of the loop or estimated
using the pre-tune function (Pre-Tune is Foxboro’s notation for auto-
tuning).
|           | The | required | parameters |       | are |     |     |     |
| --------- | --- | -------- | ---------- | ----- | --- | --- | --- | --- |
| • Initial |     | values   | of PB,     | T and | T . |     |     |     |
|           |     |          |            | i     | d   |     |     |     |
(NB).
| • Noise   | band   |         | The  | controller | starts | adaptation | whenever  | the       |
| --------- | ------ | ------- | ---- | ---------- | ------ | ---------- | --------- | --------- |
| error     | signal | exceeds |      | two times  | NB.    |            |           |           |
| • Maximum |        | wait    | time | (W         | ). The | controller | waits for | a time of |
max
| W   | max for | the occurrence |     | of  | the second | peak. |     |     |
| --- | ------- | -------------- | --- | --- | ---------- | ----- | --- | --- |
If the user is unable to provide the required parameters, a pre-tune
function thatestimates these quantities canbeactivated. Toactivate
the pre-tune function, the controller must first be put in manual.
When the pre-tune function is activated, a step input is generated.
The process parameters static gain K , dead time L and time con-
p

| 246 | Chapter | 6 Automatic | Tuning | and Adaptation |     |
| --- | ------- | ----------- | ------ | -------------- | --- |
stant T are then obtained from a simple analysis of the process reac-
tion curve. The controller parameters are calculated using a Ziegler-
| Nichols-like |     | formula: |         |     |     |
| ------------ | --- | -------- | ------- | --- | --- |
|              |     |          | PB=120K | L/T |     |
p
|     |     |     | T =1.5L |     | (6.2) |
| --- | --- | --- | ------- | --- | ----- |
i
=T/6
T
d i
Notice that the controller is parameterized in the series form. Max-
imum wait time, W , is also determined from the step response
max
as:
=5L
W
max
The noise band is determined during the last phase of the pre-tune
mode. The control signal is first returned to the level before the step
change.Withthecontrollerstillinmanualandthecontrolsignalheld
constant, the output is passed through a high-pass filter. The noise
band is calculated as an estimate of the peak-to-peak amplitude of
| the output                                  | from | the high-pass | filter. |               |     |
| ------------------------------------------- | ---- | ------------- | ------- | ------------- | --- |
| Theestimatednoiseband(NB)isusedtoinitialize |      |               |         | thederivative |     |
term. Derivative action is decreased when the noise level is high in
order to avoid large fluctuations in the control signal. The derivative
| term is | initialized | using | the following | logic: |     |
| ------- | ----------- | ----- | ------------- | ------ | --- |
=(3.0−2NB)/2.5;
| 1. Calculate |     | a quantity | Z         |     |     |
| ------------ | --- | ---------- | --------- | --- | --- |
|              | >1  |            | = T/6;    |     |     |
| 2. if Z      |     | then set   | T         |     |     |
|              |     |            | d i       |     |     |
|              | <0  |            | =0;       |     |     |
| 3. if Z      |     | then set   | T d       |     |     |
| 0<           |     | <1         | = ⋅T/6.   |     |     |
| 4. if        | Z   | then       | set T d Z | i   |     |
Apart from the set of required parameters, there is also a set of
optional parameters. If these are not supplied by the user then the
default values will be used. The optional parameters are as follows
| (default |        | parenthesis): |     |     |     |
| -------- | ------ | ------------- | --- | --- | --- |
|          | values | in            |     |     |     |
(0.3)
| • Maximum |     | allowed | damping |     |     |
| --------- | --- | ------- | ------- | --- | --- |
(0.5)
| • Maximum |     | allowed | overshoot |     |     |
| --------- | --- | ------- | --------- | --- | --- |
(1).
| • Derivative |     | factor | The derivative | term is multiplied | by the |
| ------------ | --- | ------ | -------------- | ------------------ | ------ |
derivative factor. This allows the derivative influence to be ad-
justed by the user. Setting the derivative factor to zero results in
PI control.
• Change Limit (10). This factor limits the controller parameters
| toacertainrange.Thus,thecontroller |     |     |     | willnotsetthePB,T | and |
| ---------------------------------- | --- | --- | --- | ----------------- | --- |
i
T values higher than ten times or lower than one tenth of their
d
initial values if the default of 10 is used for the change limit.

|     |     | 6.6 | CommercialProducts | 247 |
| --- | --- | --- | ------------------ | --- |
Alfa LavalAutomationECA400
This controller was announced by Alfa Laval Automation in 1988. It
has the adaptive functions of automatic tuning, gain scheduling, and
continuousadaptationoffeedbackandfeedforwardcontrol.Anearlier
| product,ECA40,whichonlyhasauto-tuning |          |     | andgainscheduling | was |
| ------------------------------------- | -------- | --- | ----------------- | --- |
| announced                             | in 1986. |     |                   |     |
| Automatic                             | Tuning   |     |                   |     |
Theauto-tuning isperformed using therelaymethod inthefollowing
way. The process is brought to a desired operating point, either by
the operator in manual mode or by a previously tuned controller in
automatic mode. When the loop is stationary, the operator presses a
tuning button. After ashortperiod, whenthe noise level ismeasured
automatically, a relay with hysteresis is introduced in the loop, and
the PID controller is temporarily disconnected (see Figure 6.4). The
hysteresis of the relay is determined automatically from the noise
level. During the oscillation, the relay amplitude is adjusted so that
a desired level of the oscillation amplitude is obtained. When an
oscillation with constant amplitude and period is obtained, the relay
experiment is interrupted and G (iω), i.e., the value of the transfer
p 0
frequencyω,iscalculatedusingdescribing
| function | G p atoscillation | 0   |     |     |
| -------- | ----------------- | --- | --- | --- |
| function | analysis.         |     |     |     |
| Control  | Design            |     |     |     |
The PID algorithm in the ECA400 controller is of series form. The
identification procedure provides a process model in terms of one
pointG (iω)ontheNyquistcurve.ByintroducingthePIDcontroller
| p   | 0   |     |     |     |
| --- | --- | --- | --- | --- |
(iω)
G in the control loop, it is possible to give the Nyquist curve of
c
the compensated system G G a desired location at frequency ω.
|     |     | p c |     | 0   |
| --- | --- | --- | --- | --- |
(iω)
For most purposes, the PID parameters are chosen so that G p 0
| is moved | to the point where |           |            |       |
| -------- | ------------------ | --------- | ---------- | ----- |
|          | G (iω)G            | (iω)=0.5e | −i135π/180 | (6.3) |
|          | p 0                | c 0       |            |       |
This design method can be viewed as a combination of phase- and
amplitude-margin specification. Since there are three adjustable pa-
rameters, K, T, and T , and the design criterion (6.3) only specifies
|                 | i d             |              |      |       |
| --------------- | --------------- | ------------ | ---- | ----- |
| two parameters, | it is required, | furthermore, | that |       |
|                 |                 | T =4T        |      | (6.4) |
i d
Forsomesimplecontrolproblems,wheretheprocessisapproximately
a first-order system, the derivative action is switched off and only a
PI controller is used. This kind of process is automatically detected.

| 248 | Chapter | 6 Automatic | Tuning          | and         | Adaptation |       |
| --- | ------- | ----------- | --------------- | ----------- | ---------- | ----- |
| For | this PI | controller, | the following   | design      | is         | used: |
|     |         |             | K =0.5/(cid:2)G | (iω)(cid:2) |            |       |
p 0
(6.5)
T =4/ω
i 0
There is also another situation in which it is desirable to switch off
the derivative part, namely for processes with long dead time. If the
operator tells the controller that the process has a long dead time, a
PIcontroller withthefollowing designwillreplacethePIDcontroller.
|     |     |     | K =0.25/(cid:2)G | (iω)(cid:2) |     |     |
| --- | --- | --- | ---------------- | ----------- | --- | --- |
p 0
(6.6)
=1.6/ω
T
|     |     |     | i   | 0   |     |     |
| --- | --- | --- | --- | --- | --- | --- |
Gain Scheduling
The ECA400 controller also has gain scheduling. Three sets of con-
troller parameters canbestored. Theparameters areobtained byus-
ingtheauto-tunerthreetimes,onceateveryoperating condition. The
actual value of the scheduling variable, which can be the controller
output, the measurement signal, or an external signal, determines
which parameter set to use. The ranges of the scheduling variable
where different parameters are used can also be given by the user.
| Adaptive | Feedback |     |     |     |     |     |
| -------- | -------- | --- | --- | --- | --- | --- |
The ECA400 controller uses the information from the relay feedback
experiment to initialize the adaptive controller. Figure 6.8 shows the
principle of the adaptive controller. The key idea is to track the point
ontheNyquistcurveobtainedbytherelayauto-tuner.Itisperformed
inthefollowingway.Thecontrolsignaluandthemeasurementsignal
|     |     | Design |     |           | Estimator |           |
| --- | --- | ------ | --- | --------- | --------- | --------- |
|     |     |        |     | BP filter |           | BP filter |
y
  sp  y
|     |     | Controller |     |     | Process |     |
| --- | --- | ---------- | --- | --- | ------- | --- |
 u
|     | Figure | 6.8 The | adaptive | controlprocedure |     | in ECA400. |
| --- | ------ | ------- | -------- | ---------------- | --- | ---------- |

|     |     |     |     | 6.6 | CommercialProducts |     | 249 |
| --- | --- | --- | --- | --- | ------------------ | --- | --- |
yarefiltered through narrow band-pass filters centered atfrequency
ω.Thisfrequencyisobtainedfromtherelayexperiment.Thesignals
0
are then analyzed in a least-squares estimator which, provides an
(iω).
| estimate | of the      | point | G p     | 0   |     |     |     |
| -------- | ----------- | ----- | ------- | --- | --- | --- | --- |
| Adaptive | Feedforward |       | Control |     |     |     |     |
Adaptive feedforward is another feature in ECA400. The adaptive
feedforward control procedure is initialized by the relay auto-tuner.
A least-squares algorithm is used to identify parameters a and b in
the model
|     |     |     | y(t)=au(t−4h)+bv(t−4h) |     |     |     | (6.7) |
| --- | --- | --- | ---------------------- | --- | --- | --- | ----- |
where yisthemeasurementsignal,uisthecontrolsignalandvisthe
disturbance signal that should be fed forward. The sampling interval
|                 |     |      |           |            | h=  | /8, |            |
| --------------- | --- | ---- | --------- | ---------- | --- | --- | ---------- |
| h is determined |     | from | the relay | experiment | as  | T   | where T is |
|                 |     |      |           |            |     | 0   | 0          |
the oscillation period. The feedforward compensator has the simple
structure
|     |     |     | ∆u  | (t)= k (t)∆v(t) |     |     | (6.8) |
| --- | --- | --- | --- | --------------- | --- | --- | ----- |
|     |     |     | ff  | ff              |     |     |       |
where the feedforward gain k ff is calculated from the estimated pro-
cess parameters
bˆ(t)
|          |           |     | k   | (t)=−0.8 |       |     | (6.9) |
| -------- | --------- | --- | --- | -------- | ----- | --- | ----- |
|          |           |     | ff  |          | aˆ(t) |     |       |
| Operator | Interface |     |     |          |       |     |       |
Theinitialrelayamplitudeisgivenadefaultvaluesuitableforawide
range of process control applications. This parameter is not critical
sinceitwillbeadjustedafterthefirsthalfperiodtogiveanadmissible
amplitude of the limit cycle oscillation. The operation of the auto-
tuner is then very simple. To use the tuner, the process is simply
brought to an equilibrium by setting a constant control signal in
manual mode. The tuning is activated by pushing the tuning switch.
Thecontroller isautomatically switched toautomatic mode whenthe
| tuning | is complete. |     |     |     |     |     |     |
| ------ | ------------ | --- | --- | --- | --- | --- | --- |
The width of the hysteresis is set automatically, based on mea-
surement of the noise level in the process. The lower the noise level,
thelowertheamplituderequiredfromthemeasuredsignal.Therelay
amplitude is controlled so that the oscillation is kept at a minimum
| level | above the | noise | level. |     |     |     |     |
| ----- | --------- | ----- | ------ | --- | --- | --- | --- |
The following are some optional settings that may be set by the
operator:
| Control | Design[normal,PI,deadtime]. |     |     |     | Thedefaultdesign |     | method |
| ------- | --------------------------- | --- | --- | --- | ---------------- | --- | ------ |
[normal]
|     | can | result | in either | a PI or | a PID controller | depending | on  |
| --- | --- | ------ | --------- | ------- | ---------------- | --------- | --- |
whether the process is of first order or not. (See the discussion about

| 250 Chapter |     | 6 Automatic | Tuningand | Adaptation |     |     |
| ----------- | --- | ----------- | --------- | ---------- | --- | --- |
control design above.) The operator can force the controller to be PI
[PI].ThePIdesign
| byselecting |     |     | method | suited | forprocesses | withlong |
| ----------- | --- | --- | ------ | ------ | ------------ | -------- |
dead time is chosen by selecting the option [dead time]. The control
design can be changed either before or after a tuning, as well as
| during the | adaptation. |     |     |     |     |     |
| ---------- | ----------- | --- | --- | --- | --- | --- |
[Yes/No].
| Reset |     | A reset | of information |     | concerning | the auto-tuner, |
| ----- | --- | ------- | -------------- | --- | ---------- | --------------- |
the gain-scheduling, or the adaptive controller can be done. Some
information from a tuning is saved and used to improve the accuracy
of the subsequent tunings, including the noise level, the initial relay
amplitude, and the period of the oscillation. If a major change is
made in the control loop, for instance if the controller is moved to
anotherloop,theoperatorcanresetthetuninginformation.Resetting
the adaptive controller will reset the controller parameters to those
| obtained | by the | relay | auto-tuner. |     |     |     |
| -------- | ------ | ----- | ----------- | --- | --- | --- |
Initial relay amplitude. In some very sensitive loops, the initial
input step of the relay experiment may be too large. The initial step
| can then | be changed | by  | the operator. |     |     |     |
| -------- | ---------- | --- | ------------- | --- | --- | --- |
Gain scheduling reference. The switches between the different
| setsofPIDparametersinthegain-scheduling |     |     |     |     | tablecanbeperformed |     |
| --------------------------------------- | --- | --- | --- | --- | ------------------- | --- |
withdifferentchoices ofthescheduling reference.Thescheduling can
bebasedonthecontrolsignal,themeasurementsignal,oranexternal
signal. The gain scheduling is active only when a reference signal is
configured.
HoneywellUDC6000
The Honeywell UDC 6000 controller has an adaptive function called
Accutune.Accutuneusesbothmodel-basedproceduresandrule-based
procedures. It can only be used on stable processes. Consequently,
| integrating | processes |     | can not be treated. |     |     |     |
| ----------- | --------- | --- | ------------------- | --- | --- | --- |
Initial Tuning
The adaptive procedure is initialized by a step-response experiment.
The user brings the process variable to a point some distance away
from the desired setpoint in manual and waits for steady state.
Switching to automatic mode will initiate an open-loop step response
experiment,wherethesizeofthestepiscalculatedtobesolargethat
| it is supposed |     | to take | the process variable |     | to the | setpoint. |
| -------------- | --- | ------- | -------------------- | --- | ------ | --------- |
During the experiment, the process variable and its derivative
are continuously monitored. Dead time L is calculated as the time
intervalbetweenthestepchangeandthemomenttheprocessvariable
| crosses | a certain | small | limit. |     |     |     |
| ------- | --------- | ----- | ------ | --- | --- | --- |
If the derivative of the process variable continuously decreases
from the start, it is concluded that the process is of first order. Static

|        |                   |     |            | 6.6 CommercialProducts |     | 251 |
| ------ | ----------------- | --- | ---------- | ---------------------- | --- | --- |
| gain K | and time constant |     | T are then | calculated             | as  |     |
| p      |                   |     | 1          |                        |     |     |
+y˙
|     |     |     | = y 2 | 2 T 1 |     |     |
| --- | --- | --- | ----- | ----- | --- | --- |
K
|     |     |     | p   | ∆u  |     |     |
| --- | --- | --- | --- | --- | --- | --- |
(6.10)
−y
|     |     |     | = y 2 | 1   |     |     |
| --- | --- | --- | ----- | --- | --- | --- |
T
|     |     |     | 1 y˙ | −y˙ |     |     |
| --- | --- | --- | ---- | --- | --- | --- |
1 2
where y and y are two measurements of the process variable, y˙
| 1   | 2   |     |     |     |     | 1   |
| --- | --- | --- | --- | --- | --- | --- |
and y˙ 2 are estimates of the derivatives of the process variable at the
∆u
corresponding instants, and is the step size of the control signal.
| Thevalues | y arecalculatedasdistancesfromthevalueattheonsetof |     |     |     |     |     |
| --------- | -------------------------------------------------- | --- | --- | --- | --- | --- |
i
the step. These calculations can beperformed before the steady-state
is reached. It is claimed that the process is identified in a time less
than one third of the time constant. The controller is then switched
to automatic mode and controlled to the setpoint. When this is done,
a fine adjustment of the parameters is done by calculating the gain
| K p from | the steady-state | levels. |     |     |     |     |
| -------- | ---------------- | ------- | --- | --- | --- | --- |
If the derivative of the process variable increases to a maximum
andthendecreases,theprocessisidentifiedasasecond-orderprocess.
The step response of a second-order process with two time constants
is
|     |       | (cid:5) |      |                  | (cid:6) |        |
| --- | ----- | ------- | ---- | ---------------- | ------- | ------ |
|     |       |         | T e  | −t/T2 −T e −t/T1 |         |        |
|     | y(t)= |         | 1+ 2 | 1                |         | (6.11) |
K
|     |     | p   |     | T −T |     |     |
| --- | --- | --- | --- | ---- | --- | --- |
|     |     |     |     | 1 2  |     |     |
This equation is used to calculate static gain K and time constants
p
T and T . Process identification is performed in two steps. A first
| 1   | 2   |     |     |     |     |     |
| --- | --- | --- | --- | --- | --- | --- |
calculation isdoneshortly afterthetimeofmaximumslope. Thecon-
troller is then switched to automatic mode and controlled to the set-
point. When steady state is reached, the parameters arerecalculated
using theadditional information ofsteadystate levels. Theequations
| for calculating | the process | parameters |        | are   |      |     |
| --------------- | ----------- | ---------- | ------ | ----- | ---- | --- |
|                 |             | y(t        | )+y˙(t | )(T   | +T ) |     |
|                 |             | =          | max    | max 1 | 2    |     |
|                 |             | K p        |        | ∆u    |      |     |
1− N2
|     | T +T | =   | (cid:20) | (cid:21) t |     | (6.12) |
| --- | ---- | --- | -------- | ---------- | --- | ------ |
|     | 1    | 2   |          | max        |     |        |
|     |      | Nln | 1        |            |     |        |
N
T
= 1
N
T
2
where t is the time from the start of the rise to the point of
max
maximum slope. These three equations have four unknowns: K , T ,
p 1
T 2 and N. At the first time of identification, shortly after the time of
maximum slope, it is assumed that N = 6, and K , T , and T , are
|                                                          |     |     |     |     | p 1 | 2   |
| -------------------------------------------------------- | --- | --- | --- | --- | --- | --- |
| determinedfromtheequations.Whensteadystateisreached,gain |     |     |     |     |     | K   |
p
iscalculatedfromthesteady-statelevels.Thisprovidesthepossibility
tocalculatetheotherthreeunknownsfromthethreeequationsabove.

| 252 | Chapter | 6   | Automatic | Tuningand | Adaptation |     |     |     |
| --- | ------- | --- | --------- | --------- | ---------- | --- | --- | --- |
Adaptation
TheUDC6000controlleralsohascontinuousadaptation.Theadapta-
tion mechanism is activated when the process variable changes more
than 0.3% from the setpoint or if the setpoint changes more than a
|            |     |        | (More |         | below.)   |     |     |     |
| ---------- | --- | ------ | ----- | ------- | --------- | --- | --- | --- |
| prescribed |     | value. |       | details | are given |     |     |     |
The full details of the adaptive controller are not published, but
some of the rules in the heuristic rule base will be presented. The
controller monitors the behavior of the process variable and makes
| the following |     | adjustments: |     |     |     |     |     |     |
| ------------- | --- | ------------ | --- | --- | --- | --- | --- | --- |
1. The controller detects oscillations in the process variable. If the
| oscillation |     | frequency,ω,isless |     |     | than1/T,then |     | theintegral | time |
| ----------- | --- | ------------------ | --- | --- | ------------ | --- | ----------- | ---- |
|             |     |                    |     | 0   |              | i   |             |      |
=2/ω.
| is  | increased | to  | T   |     |     |     |     |     |
| --- | --------- | --- | --- | --- | --- | --- | --- | --- |
|     |           |     | i   | 0   |     |     |     |     |
2. If the oscillation frequency ω is greater than 1/T, then the
|     |     |     |     |     | 0   |     | i   |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
=1/ω.
| derivative |     | time | is chosen | as  | T   |     |     |     |
| ---------- | --- | ---- | --------- | --- | --- | --- | --- | --- |
|            |     |      |           |     | d 0 |     |     |     |
3. If the oscillation remains after adjustment 1 or 2, the controller
| will | cut | its gain | K in | half. |     |     |     |     |
| ---- | --- | -------- | ---- | ----- | --- | --- | --- | --- |
4. Ifaload disturbance orasetpoint changegives aresponse witha
=1/ω.
| dampedoscillation, |     |     | thederivative |     | timeischosen |     | tobe T d | 0   |
| ------------------ | --- | --- | ------------- | --- | ------------ | --- | -------- | --- |
5. If a load disturbance or a setpoint change gives a sluggish re-
|                                                |     |     |     |     |     |     | L+T | +T    |
| ---------------------------------------------- | --- | --- | --- | --- | --- | --- | --- | ----- |
| sponse,wherethetimetoreachsetpointislongerthan |     |     |     |     |     |     |     | 1 2 , |
both integral time T and derivative time T are divided by a fac-
|     |         |     |     | i   |     | d   |     |     |
| --- | ------- | --- | --- | --- | --- | --- | --- | --- |
| tor | of 1.3. |     |     |     |     |     |     |     |
6. If the static process gain K changes, the controller gain K is
p
| changed |     | so that | the | product | KK remains | constant. |     |     |
| ------- | --- | ------- | --- | ------- | ---------- | --------- | --- | --- |
p
| Control | Design |     |     |     |     |     |     |     |
| ------- | ------ | --- | --- | --- | --- | --- | --- | --- |
The UDC 6000 uses a controller on series form that has the transfer
function
|     |     |     |        | (1+sT)(1+sT  |     | )   |     |     |
| --- | --- | --- | ------ | ------------ | --- | --- | --- | --- |
|     |     |     | G (s)= | K            | i   | d   |     |     |
|     |     |     | c      | sT(1+0.125sT |     | )   |     |     |
|     |     |     |        |              | i   | d   |     |     |
The design goal is to cancel the process poles with the two zeros in
the controller. If there is no dead time in the process, the controller
| parameters |             | are chosen | in      | the following | way:         |      |         |     |
| ---------- | ----------- | ---------- | ------- | ------------- | ------------ | ---- | ------- | --- |
|            | First-order |            | process |               | Second-order |      | process |     |
|            |             | =24/K      |         |               |              | =6/K |         |     |
|            |             | K          |         | p             | K            |      | p       |     |
|            |             | =0.16T     |         |               |              | =    |         |     |
|            |             | T          |         |               | T            | T    |         |     |
|            |             | i          |         | 1             |              | i    | 1       |     |
|            |             | =0         |         |               |              | =    |         |     |
|            |             | T          |         |               | T            | T    |         |     |
|            |             | d          |         |               |              | d    | 2       |     |

6.6 Commercial Products 253
For processes with dead time, the controller parameters are deter-
mined as follows:
First-order process Second-order process
3 3
K = K =
K (1+3L/T) K (1+3L/T)
p i p i
T = T T = T +T
i 1 i 1 2
T T
T =0 T = 1 2
d d T +T
1 2
Operator Interface
The following are some optional parameters that may be set by the
operator:
• Select whether adaptation should be performed during setpoint
changes only, or during both setpoint changes and load distur-
bances.
• Set the minimum value of setpoint change that will activate the
adaptation. Range: ±5% to ±15%.
YokogawaSLPC-181,281
TheYokogawaSLPC-181and281bothuse aprocess model asafirst-
order system with dead time for calculating the PID parameters.
A nonlinear programming technique is used to obtain the model.
The PID parameters are calculated from equations developed from
extensive simulations. The exact equations are not published.
Two different controller structures are used.
(cid:5) (cid:1) (cid:6)
1 dy
1: u= K −y+ edt−T f
d
T dt
(cid:5) (cid:1)
i
(cid:6)
(6.13)
1 dy
2: u= K e+ edt−T f
d
T dt
i
where
dy N
f = (y−y ) (6.14)
f
dt T
d
The first structure is recommended if load disturbance rejection is
most important, and structure 2 if setpoint responses are most im-
portant. Thesetpoint canalsobepassed through twofiltersinseries:
1+αsT 1+α sT
Filter 1: i i Filter 2: d d (6.15)
1+sT 1+sT
i d

| 254 Chapter | 6 Automatic | Tuningand | Adaptation |     |
| ----------- | ----------- | --------- | ---------- | --- |
Table 6.2 Setpoint response specifications used in the Yokogawa
| SLPC-181and | 281. |               |              |     |
| ----------- | ---- | ------------- | ------------ | --- |
|             | Type | Features      | Criteria     |     |
|             | 1    | no overshoot  | no overshoot |     |
|             | 2    | 5% overshoot  | ITAE minimum |     |
|             | 3    | 10% overshoot | IAE minimum  |     |
|             | 4    | 15% overshoot | ISE minimum  |     |
where α and α are parameters set by the user, mainly to adjust
|     | i d |     |     |     |
| --- | --- | --- | --- | --- |
the overshoot of the setpoint response. The effects of these two filters
areessentially equivalent tosetpoint weighting. Itcanbeshown that
| α =b, where | bis the | setpoint weighting | factor. |     |
| ----------- | ------- | ------------------ | ------- | --- |
i
The user specifies the type of setpoint response performance ac-
cording to Table 6.2. A high overshoot will, of course, yield a faster
| response. | The controller | has four adaptive | modes: |     |
| --------- | -------------- | ----------------- | ------ | --- |
Auto mode. The adaptive control is on. PID parameters are auto-
| matically | updated. |     |     |     |
| --------- | -------- | --- | --- | --- |
Monitoring mode. In this mode, the computed model and the PID
parameters are only displayed. This mode is useful for validating the
adaptive function orchecking theprocessdynamics variations during
operation.
Auto startup mode. This is used to compute the initial PID pa-
rameters. An open loop step response is used to estimate the model.
| On-demand | mode. | This mode is | used to make a | setpoint change. |
| --------- | ----- | ------------ | -------------- | ---------------- |
When theon-demand tuning is requested, a step changeisapplied to
the process input in closed loop. The controller estimates the process
| model using   | the subsequent | closed-loop | response.      |             |
| ------------- | -------------- | ----------- | -------------- | ----------- |
| Thecontroller | constantly     | monitors    | theperformance | ofthesystem |
by computing the ratio of the variances of process output and model
output. This ratio is expected to be about 1. If it is greater than 2
or less than 0.5, a warning message for retuning of the controller
is given. Dead time and feedforward compensation are available for
the constant gain controller, but they are not recommended by the
| manufacturer                            | to be used | in conjunction | with adaptation. |           |
| --------------------------------------- | ---------- | -------------- | ---------------- | --------- |
| Fisher-RosemountIntelligentTunerandGain |            |                |                  | Scheduler |
The intelligent tuner is a software package that runs in the dis-
tributed control systems ProvoxTM and RS3TM. It is interesting to
note that the same software runs on two different systems. Tuning
is done on demand from the operator. There are good facilities for an

6.6 Commercial Products 255
y
1
0
u
−1
0 5 10 15 20
Figure6.9 Input(u)andoutput(y)signalsduringanexperiment
with relay feedback.
instrument engineer toinfluence boththetuningexperiment andthe
control design. Information about the process is obtained from an ex-
periment with relay feedback. Several different tuning methods can
be chosen.
It is easy for the operator to follow the experiment because the
control variable and the process variable are plotted on the console
duringtheexperiment. Atypical behavior ofthesignals isillustrated
in Figure 6.9. Tuning starts with the process in equilibrium. Then
there is an initialization phase in which a step change is made in
the control variable. The process output is monitored, and the step
isreversed when the process output has changed a specified amount.
Relayfeedbackisinitiatedwhentheoutputequalsthesetpointagain.
The step size is typically 3%, 5%, or 10% of the range of the control
variable.Thereisadefaultvaluebutaparticularvaluecanbechosen
from the console. The amplitude of the process variable is typically
between 1% and 3% of the signal span.
An hysteresis is normally used to overcome the problem of noisy
signals in a relay feedback experiment. This has the drawback of
giving too high a value of the ultimate period. A different method
that gives a more accurate value of the ultimate period can also be
used in the Fisher-Rosemount system. The initialization phase gives
information about the dead time of the process. After a switch the
relayisprohibited from switching during atime approximately equal
tothedeadtime.Therecommendationistousethisonlyinverynoisy
environments.
The tuning experiment gives process data in terms of the ap-
parent dead time L, the ultimate gain K , and the ultimate period
u
T . From these parameters, process static gain K , dominating time
u p
constant T, and apparent dead time L are calculated and displayed
on the screen. In a distributed system there may be communication
delays. Special care has been taken to make sure that the delay is
short and to account for it when calculating the ultimate gain and
the ultimate period.

256 Chapter 6 Automatic Tuningand Adaptation
Tuning is done from a display that can be brought up on the
console. The display shows curves; it also has menus and buttons
to execute the tuning. The program has the following methods for
computing the controller parameters.
PID Standard PID controller with a design that gives a mod-
erately fast response with small overshoot and a phase
○
margin of about 45 .
PID-60 PID controller with slow response and small overshoot.
P Proportional controller with Ziegler-Nichols design.
PI PI control based on Ziegler-Nichols design.
PID-ZN PID controller based on Ziegler-Nichols design, fast but
with considerable overshoot.
○
PID-45N PIDcontrol for anoisy control loop. Thecontroller has45
phasemarginandlessderivative actionthanthestandard
PID design.
PID-60N Similar to PID-45N but with less overshoot.
PI-DT PIdesignforprocesseswithdominatingdeadtime,smaller
gain and integral time than the PI design.
IMC Designbasedontheinternalmodelprinciple.(SeeSection
4.5.) The details are not available. This design does not
work for processes with integral action.
IMC-NSR Similar to IMC design for processes with integral action.
There are also recommendations for choosing different control de-
signs. PI control is the primary choice for flow-pressure and level
control, while PID is recommended for pH and temperature control.
Inaddition, theclosedloopcanbemodifiedbyselecting SLOW,NOR-
MAL, or FAST. With these choices the controller gain is multiplied
withthefactors0.50,1.00,and1.25.Itispossibletochangethedesign
without retuning the process.
After a tuning the new controller parameters are displayed to-
getherwiththeoldcontrollerparameters.Itisthenpossibletoaccept,
reject, redesign, or modify the controller parameters.
The intelligent gain scheduler is a complement to the tuner. The
scheduling variableistheprocessvariable,thecontrolvariable,oran
external signal. The range of the scheduling variable is divided into
three regions. The values of the controller parameters in each region
are stored in a table. Interpolation between the entries is done with
a fuzzy scheme. Values from the tuner are entered automatically in
the tables. They can also be entered manually.
TypicalapplicationsofgainschedulingarepHcontrol,split-range
control, level control in vessels with unusual geometries, and surge
tank control.

|     |     |     |     |     | 6.6 Commercial | Products | 257 |
| --- | --- | --- | --- | --- | -------------- | -------- | --- |
HoneywellLooptune
| Looptuneisatuning-program |           |     |           | packagefortheDCSsystemHoneywell |     |     |     |
| ------------------------- | --------- | --- | --------- | ------------------------------- | --- | --- | --- |
| TDC 3000.                 | It offers | the | following | features:                       |     |     |     |
• A search algorithm, which performs incremental improvements
| of the | controller | parameters |     | until | an optimum | is reached. |     |
| ------ | ---------- | ---------- | --- | ----- | ---------- | ----------- | --- |
•
| Arelayfeedbacktechnique |     |           |     | totunethecontroller |         | accordingtothe |     |
| ----------------------- | --- | --------- | --- | ------------------- | ------- | -------------- | --- |
| Ziegler-Nichols         |     | frequency |     | response            | method. |                |     |
• Gain scheduling, where the schedule contains three sets of con-
| troller       | parameters.   |          |       |        |                   |     |     |
| ------------- | ------------- | -------- | ----- | ------ | ----------------- | --- | --- |
| In this       | presentation, | we       | focus | on the | search algorithm. |     |     |
| The Objective |               | Function |       |        |                   |     |     |
The control performance is optimized by adjusting the controller pa-
(J)
rameters in such a way that an objective function is minimized.
| The objective | function |     | is  |     |     |     |     |
| ------------- | -------- | --- | --- | --- | --- | --- | --- |
=(1−w)σ2+wσ2
J
|       |        |          |     |             | e u   |        |           |
| ----- | ------ | -------- | --- | ----------- | ----- | ------ | --------- |
| σ2    |        |          |     |             |       | = −    | σ2        |
| where | is the | variance | of  | the control | error | e y sp | y; is the |
|       | e      |          |     |             |       |        | u         |
variance of the control signal; and wis a weighting factor with range
0 ≤ w ≤ 1, specified by the user. (This is the only parameter that
user.)
has to be specified by the If a small value of w is chosen, the
errorvariancetermdominatestheobjectivefunction.Thismeansthat
objective function J is minimized if the controller is tuned for tight
control. Ifwislarge,thecontrol signal varianceterm dominates, and
objective function J isminimized whenthecontroller istuned togive
| a smoother | control | with | smaller | control | actions. |     |     |
| ---------- | ------- | ---- | ------- | ------- | -------- | --- | --- |
Theobjective function iscalculated inthe following way.Setpoint
y sp , process output y, and control signal u are registered during an
(σ2)
| evaluation | period. | The | variance | of  | the control | error | and the |
| ---------- | ------- | --- | -------- | --- | ----------- | ----- | ------- |
e
varianceofthecontrolsignal(σ2)arethencalculatedinthefollowing
u
way:
(cid:12)n
1
|     |     | σ2  | =   | (y  | (i)−y(i))2 |     |     |
| --- | --- | --- | --- | --- | ---------- | --- | --- |
sp
e n
i=1
(cid:12)n
1
|     |     | σ2  | =   | (u(i)−u¯)2 |     |     |     |
| --- | --- | --- | --- | ---------- | --- | --- | --- |
u n
i=1
| where n | is the | number | of data | points | and |     |     |
| ------- | ------ | ------ | ------- | ------ | --- | --- | --- |
(cid:12)n
1
|     |     |     | u¯  | =   | u(i) |     |     |
| --- | --- | --- | --- | --- | ---- | --- | --- |
n
i=1
is the mean value of the control signal during the evaluation period.

| 258 Chapter   | 6 Automatic | Tuningand        | Adaptation |
| ------------- | ----------- | ---------------- | ---------- |
| The Search    | Procedure   |                  |            |
| The procedure | consists    | of the following | steps:     |
1. Collect nnew values of y , y, and u during an evaluation period.
sp
2. Compute the value of the objective function and compare it with
| the | previous value. |     |     |
| --- | --------------- | --- | --- |
3. Ifthevalue oftheobjective function hasdecreased, thecontroller
parameter is adjusted further in the same direction, otherwise
| the | direction is reversed. |     |     |
| --- | ---------------------- | --- | --- |
4. If the value of the objective function has reached its minimum,
| then | stop the adjustment. | If not, | go back to step 1 again. |
| ---- | -------------------- | ------- | ------------------------ |
Whenacontrollerparameterhasbeenadjustedaccordingtothese
rules, the Looptuner goes on to the next controller parameter and
starts to adjust it to an optimal value. It is claimed that normally
several passes through the tuning constants are needed in order to
| arrive at | the optimal | controller parameters. |     |
| --------- | ----------- | ---------------------- | --- |
The evaluation period is a crucial parameter in this tuning pro-
cedure. It is determined automatically and it should be as short as
possible in order to get a fast tuning procedure. On the other hand,
it is important that it is long enough, so that a representative num-
ber of disturbances occur within the period. At least eight significant
disturbances must occur within the evaluation period. The Looptune
alsohasarule-basethatcompensatestheobjective functionsforvari-
ations in the disturbance behavior between the different evaluation
periods.
ThesearchprocedureintheLooptunehastwomodesofoperation:
One-shot tuning. The tuning is deactivated when all controller
| parameters | have reached | their optimal | values. |
| ---------- | ------------ | ------------- | ------- |
Continuous adaptation. The adjustments goes on until it is inter-
| rupted by | the operator. |     |     |
| --------- | ------------- | --- | --- |
ABBDCSTuner
This DCS Tuner is a software package for on-line and off-line auto-
| matictuning | ofPIDcontrollers | intheABBMastersystem.Itrunson |     |
| ----------- | ---------------- | ----------------------------- | --- |
personal computers and is connected to the ABB Master by a serial
link interface. TheDCS Tuner hasfour mainfunctions: process iden-
tification, controller tuning, process analysis, and simulation. These
| four functions | are described  | below. |     |
| -------------- | -------------- | ------ | --- |
| Process        | Identification |        |     |
The process identification can be based on either historical data or
on-line data. Theon-line data acquisition canbeevent initiated. This

|     |     |     | 6.6 Commercial | Products | 259 |
| --- | --- | --- | -------------- | -------- | --- |
means that the data used for process identification can be controlled
based on a high- or low-level triggering. The triggering signal can
be the control error, the process variable, or any other signal logged
during the session. The major steps performed during the process
| model      | identification | are:           |         |     |     |
| ---------- | -------------- | -------------- | ------- | --- | --- |
| 1. Signal  | filering using | Butterworth    | filters |     |     |
| 2. Process | dead-time      | estimation     |         |     |     |
| 3. Process | model order    | identification |         |     |     |
4. Least-squares identification ofcontinuous-time anddiscrete-time
models
| 5. Process | model validation |     |     |     |     |
| ---------- | ---------------- | --- | --- | --- | --- |
These steps are normally performed automatically, but the operator
| may interfere | by changing | parameters. |     |     |     |
| ------------- | ----------- | ----------- | --- | --- | --- |
| Controller    | Tuning      |             |     |     |     |
The tuning procedure uses the discrete-time model to obtain the
controller parameters. The tuning method is based on a dominant
pole design procedure. The user may select among three different
| closed-loop | performances: | Fast, Normal, | or Damped. |     |     |
| ----------- | ------------- | ------------- | ---------- | --- | --- |
| Process     | Analysis      |               |            |     |     |
Three functions are available for process analysis. They are called
Statistics, FFT,and Correlation. The Statistics function provides sta-
tistical information about the different data series, such as mean,
standard deviation etc. Frequency spectra of the different signals
and frequency domain models of the process can be obtained using
the Fast Fourier Transform (FFT). Finally, the Correlation function
| gives results | of auto- | and cross-correlation | analysis. |     |     |
| ------------- | -------- | --------------------- | --------- | --- | --- |
Simulation
In the simulation mode, both open-loop and closed-loop simulation
are available. The user has access to both controller and process pa-
rameters. Thisprovides apossibility tocheckhow different controller
settings suit a certain process model, and also how changes in the
| process | model influence | the control | loop performance. |     |     |
| ------- | --------------- | ----------- | ----------------- | --- | --- |
TechmationProtuner
The Protuner is a process analyzer from Techmation Inc. It consists
of a software package for personal computers and an interface mod-
ule with cables to be connected to the process output and the control

| 260 Chapter | 6 Automatic | Tuningand |     | Adaptation |     |
| ----------- | ----------- | --------- | --- | ---------- | --- |
signal of the control loop to be analyzed. The Protuner monitors a
step-response experiment, calculates the frequency response of the
process based on the experimental data, and suggests controller pa-
| rameters | based on several | methods |     | for controller | tuning. |
| -------- | ---------------- | ------- | --- | -------------- | ------- |
Prior Information
Before theprocess analysis isperformed, the user must provide some
information about the process and the controller. This is done using
a couple of “Set-up menus.” The following process information must
be given:
•
| The ranges | of the | control | and the | measurement | signals. |
| ---------- | ------ | ------- | ------- | ----------- | -------- |
•
It must be determined if the process is stable or if it has integral
action.
To be able to set relevant controller parameters, the following data
| about the | controller must       | be  | provided: |     |     |
| --------- | --------------------- | --- | --------- | --- | --- |
| • P-type  | (gain or proportional |     | band)     |     |     |
• I-type (seconds, seconds/repeat, minutes, or minutes/repeat)
| • Controller | structure | (ideal, | series, | or parallel) |     |
| ------------ | --------- | ------- | ------- | ------------ | --- |
| • Sampling   | rate      |         |         |              |     |
• Filter time constant (if there is a low-pass filter connected to the
signal).
measurement
Before the tuning experiment can be performed, the user must also
specify a sample time. This is the time during which data will be
collected during the experiment. It isimportant to choose the sample
time long enough, so that the step response settles before the sample
time has ended. In case of an open-loop experiment of an integrating
process, the response must reach a constant rate of change when the
| experiment  | ends.       |     |       |     |     |
| ----------- | ----------- | --- | ----- | --- | --- |
| Determining | the Process |     | Model |     |     |
The tuning procedure is based on a step-response experiment. It can
beperformed either inopen or closed loop. Theopen-loop experiment
is recommended. When the user gives a start command, the process
| outputandthecontrolsignalaredisplayed |     |     |     | onthescreen,withatime |     |
| ------------------------------------- | --- | --- | --- | --------------------- | --- |
axis that is given by the sample time defined by the user. The user
then makes a step change in the control signal. If the experiment is
performed in closed loop a step is instead introduced in the setpoint.
There are several facilities for editing the data obtained from the
step-response experiment. Outliers can be removed and data can be
filtered. These features are very useful because they make it possi-
ble to overcome problems that are often encountered when making
| experiments | on industrial | processes. |     |     |     |
| ----------- | ------------- | ---------- | --- | --- | --- |

|     |     |     |     | 6.6 Commercial | Products | 261 |
| --- | --- | --- | --- | -------------- | -------- | --- |
When the data has been edited the Protuner calculates the fre-
quencyresponse oftheprocess. Theresult canbedisplayed inaBode
diagram, a Nyquist diagram, or a Nichols diagram. The static gain,
thedominant time constant and theapparent dead time arealso dis-
played, as well as the ultimate gain and the ultimate period.
Design Calculations
Thecontrollerparametersarecalculatedfromthefrequencyresponse.
A special technique is used. This is based on cancellation of process
poles by controller zeros. The integral time and the derivative time
are first determined to perform this cancellation. The gain is then
| determined | to meet predetermined |     |     | gain and phase | margins. |     |
| ---------- | --------------------- | --- | --- | -------------- | -------- | --- |
The Protuner provides several design options. Controller param-
| eters are | given for the        | following  | closed-loop | responses: |     |     |
| --------- | -------------------- | ---------- | ----------- | ---------- | --- | --- |
| Slow:     | Critically           | damped     | response.   |            |     |     |
| Medium:   | Slightly underdamped |            |             | response.  |     |     |
| Fast:     | Response             | with decay | ratio       | 0.38.      |     |     |
The different design options are obtained by specifying different val-
ues of the gain and the phase margins. The Protuner provides differ-
ent controller parameters depending on whether setpoint or load dis-
turbances are considered. Both P, PI, and PID controller parameters
areprovided. Thesetpoint weightings for proportional andderivative
action and the high frequency gain at the derivative part must be
| supplied | by the user. |     |     |     |     |     |
| -------- | ------------ | --- | --- | --- | --- | --- |
Evaluation
It is possible to evaluate the performance of the closed-loop system
inseveral ways. Thecombined frequency response, i.e.,thefrequency
| response | of the loop transfer |                 | function |            |     |     |
| -------- | -------------------- | --------------- | -------- | ---------- | --- | --- |
|          |                      | G(cid:10) (iω)= | G        | (iω)G (iω) |     |     |
p c
where G (iω) is the process transfer function and G (iω) is the con-
|     | p   |     |     |     | c   |     |
| --- | --- | --- | --- | --- | --- | --- |
troller transfer function, canbeplotted ina Bode diagram, aNyquist
diagram, or a Nichols diagram. Inthis way, thephase and amplitude
| margins | or the M value | can | be checked. |     |     |     |
| ------- | -------------- | --- | ----------- | --- | --- | --- |
s
The Protuner also has a simulation facility. It is possible to sim-
ulate the closed-loop response of the process and the suggested con-
troller.Todothis,itisnecessarytoprovidesomeadditionalcontroller
parameters, namely setpoint weightings band c, and derivative gain
limitation factor N. Using the simulation facility, it is also possible
toinvestigate the effects of noise and todesign filters toreduce these
effects.

| 262 Chapter    | 6 Automatic | Tuningand | Adaptation    |     |
| -------------- | ----------- | --------- | ------------- | --- |
| 6.7 Integrated |             | Tuning    | and Diagnosis |     |
It is well known that many control loops in the process industry do
not perform satisfactory. Poor controller tuning is one of the major
reasons for this, but there are other problems that are not solved by
adjusting the controller parameters. Examples are nonlinearities in
the valves (stiction, hysteresis, etc) and improperly sized valves and
transmitters. It is important to investigate the control loop carefully
andtodiscover theseproblemsbeforeinitiating thecontroller tuning.
| (Compare   |           |            | 6.2.)      |     |
| ---------- | --------- | ---------- | ---------- | --- |
| with       | the       | discussion | in Section |     |
| Frictionin | the Valve |            |            |     |
Acommon cause of problems ishigh friction in the valve. There is, of
(stiction)
course, always static friction in the valve, but if the valve
maintenance is insufficient, the friction may be so large that the
control performance degrades. The amount of friction can easily be
measuredbymakingsmallchangesinthecontrolsignalandchecking
howtheprocessoutputsreact.Toinvestigatethevalve,itispreferable
| tousetheposition | ofthevalvestemastheoutput.Theprocessoutput |     |     |     |
| ---------------- | ------------------------------------------ | --- | --- | --- |
can also be used, but then we are investigating the complete process.
The experiment will also take a longer time because of the dynamics
involved. The procedure is shown in Figure 6.10. In the figure, the
process output only responds to the control signal when the changes
in the control signal are large enough to overcome the static friction.
Friction inthevalve results instick-slip motion. This phenomena
is shown in Figure 6.11. Because of the static friction, the process
output will oscillate around the setpoint. The valve will only move
0.4
| 0.2 y |     |     |     |     |
| ----- | --- | --- | --- | --- |
0
| 0   |     | 50  | 100 | 150 |
| --- | --- | --- | --- | --- |
0.4
| 0.2 | u   |     |     |     |
| --- | --- | --- | --- | --- |
0
| 0      |                                                   | 50  | 100 | 150 |
| ------ | ------------------------------------------------- | --- | --- | --- |
| Figure | 6.10 Proceduretochecktheamountofvalvefriction.The |     |     |     |
upperdiagramshowsprocessoutputyandthelowerdiagramshows
| controlsignal | u.  |     |     |     |
| ------------- | --- | --- | --- | --- |

6.7 Integrated Tuningand Diagnosis 263
when the control signal has changed sufficiently since the previous
valve movement. When the valve moves, it moves too much. This
causes the stick-slip motion. The pattern in Figure 6.11, where the
measurement signal is close to a square wave and the control signal
is close to a triangular wave, is typical for stick-slip motion.
Many operators detune the controller when they see oscillations
like the one in Figure 6.11, since they believe that the oscillations
are caused by a bad controller tuning. Unfortunately, most adaptive
controllers do the same. What one should do, when a control loop
starts to oscillate, is to first determine the cause of the oscillation. A
good way to perform this determination is presented in Figure 6.12.
Thefirstproblemtodetermineiswhethertheoscillationsaregen-
erated outside the control loop or generated inside the loop. This can
bedonebydisconnectingthefeedback,e.g.,byswitchingthecontroller
to manual mode. If the oscillation is still present, the disturbances
must be generated outside the loop, otherwise they were generated
inside the loop.
If the disturbances are generated inside the loop, the cause can
be either friction in the valve or a badly tuned controller. Whether
friction ispresent or not canbedetermined bymaking smallchanges
in the control signal and checking if the measurement signal follows,
as shown in Figure 6.10. If friction is causing the oscillations, the
solution to the problem is valve maintenance.
If the disturbances are generated outside the control loop, one
should try,of course, tofindthesource of thedisturbances andtryto
eliminate it. This is not always possible, even if the source is found.
One can then try to feed the disturbances forward to the controller,
and in this way reduce their effect on the actual control loop.
y
0.7
0.5
0 10 20 30 40 50
0.7 u
0.5
0 10 20 30 40 50
Figure 6.11 Stick-slipmotioncausedbyfrictioninthevalve.The
upperdiagramshowsprocessoutputyandthelowerdiagramshows
controlsignal u.

| 264 | Chapter | 6 Automatic | Tuning | and Adaptation |     |
| --- | ------- | ----------- | ------ | -------------- | --- |
Put controller in
manual mode
|     |     | No  | Still | Yes |     |
| --- | --- | --- | ----- | --- | --- |
oscillating
?
|     |     | Check the valve |     | Search for the  |     |
| --- | --- | --------------- | --- | --------------- | --- |
source
|     | Yes | Friction |     | Possible | Yes |
| --- | --- | -------- | --- | -------- | --- |
to eliminate
?
?
|                  |     | No                |     | No              |              |
| ---------------- | --- | ----------------- | --- | --------------- | ------------ |
| Undertake valve  |     |                   |     |                 | Eliminate    |
| maintenance      |     |                   |     |                 | disturbances |
|                  |     | Check             |     | Possible        | Yes          |
|                  |     | controller tuning |     | to feed forward |              |
?
No
Use feedforward
Reduce disturbances
by controller tuning
Figure 6.12 Diagnosis procedure todiscover thecause ofoscilla-
| tions,       | and | recommendedactions | toeliminate | them. |     |
| ------------ | --- | ------------------ | ----------- | ----- | --- |
| Hysteresisin |     | theValve           |             |       |     |
Because of wear, there is often hysteresis (backlash) in the valve
or actuator. The amount of hysteresis can be measured as shown
in Figure 6.13. The experiment starts with two step changes in the
control signal in the same direction. The hysteresis gap will close if
the first step is sufficiently large. This means that the second step
is performed without hysteresis. The third step is then made in the
opposite direction. The control signal will then pass the whole gap
before the valve moves. If the last two steps are of the same size,

6.7 Integrated Tuningand Diagnosis 265
0.4
y
0.2
0
0 50 100 150
0.4
u
0.2
0
0 50 100 150
Figure 6.13 Procedure to check the amount of valve hysteresis.
The upper diagram shows processoutput yand the lower diagram
shows controlsignal u.
we can calculate the hysteresis as ∆y/K , where ∆yis the difference
p
between the process outputs after the first and the third step, see
Figure 6.13, and K is the static process gain (also easily obtained
p
from Figure 6.13). If the control signal is ramped (or moved in small
steps) upwards, and then downwards again, we obtain the result in
Figure 6.14. Here, the hysteresis can easily be determined as the
horizontal distance between the two lines.
Figure 6.15 shows closed-loop control of a process with large hys-
teresis in the valve. The control signal has to travel through the gap
in order to move the valve. Therefore, we get the typical linear drifts
in the control signal as shown in Figure 6.15.
y
0.8
0.6
0.4
0.2
u
0
0 0.2 0.4 0.6 0.8 1
Figure 6.14 Characteristic of a valve with hysteresis. The dia-
gram shows process output yasfunctionof controlsignal u.

| 266 Chapter | 6 Automatic | Tuningand | Adaptation |     |
| ----------- | ----------- | --------- | ---------- | --- |
y
0.5
0.4
| 0   | 50  |     | 100 | 150 |
| --- | --- | --- | --- | --- |
| 0.5 | u   |     |     |     |
0.4
| 0   | 50  |     | 100 | 150 |
| --- | --- | --- | --- | --- |
Figure 6.15 Closed-loop control with valve hysteresis. The up-
per diagram shows process output yand the lower diagram shows
| controlsignal | u.  |     |     |     |
| ------------- | --- | --- | --- | --- |
If a relay auto-tuner is applied to a process with hysteresis, the
estimatedprocessgainwillbesmaller thanthetruevalue. Thisgives
too large a controller gain. An auto-tuner based on a step-response
experiment will work properly if the gap is closed before the step-
response experiment is performed. (Compare with the second step in
6.13.)
Figure
OtherNonlinearities
Even valves with a small static friction and hysteresis often have a
nonlinear characteristic. The total characteristic of the process can
beobtained bychecking thestatic relation between thecontrol signal
0.8
| 0.4 |     | y   |     |     |
| --- | --- | --- | --- | --- |
0
| 0   | 50  |     | 100 | 150 |
| --- | --- | --- | --- | --- |
0.8
u
0.4
0
| 0   | 50  |     | 100 | 150 |
| --- | --- | --- | --- | --- |
Figure 6.16 A procedure to determine the static process charac-
teristic. The upper diagram shows process output yand the lower
| diagram | shows controlsignal | u.  |     |     |
| ------- | ------------------- | --- | --- | --- |

|     |     | 6.7 | IntegratedTuning | and Diagnosis | 267 |
| --- | --- | --- | ---------------- | ------------- | --- |
y
0.8
0.6
0.4
0.2
u
0
|     | 0 0.2 | 0.4 | 0.6 | 0.8 1 |     |
| --- | ----- | --- | --- | ----- | --- |
Figure 6.17 The static process characteristic, showing process
| output | yasfunctionof | controlsignal | u.  |     |     |
| ------ | ------------- | ------------- | --- | --- | --- |
andthemeasuredsignal.SeeFigure6.16.Thecharacteristicshownin
Figure6.16isobviously nonlinear. Ithasahigher gainatlargervalve
positions. If the stationary values of the measured signal are plotted
against the control signal, weobtain the static process characteristic.
See Figure 6.17. A plot like this reveals whether gain scheduling is
| suitable   | or not.  |         |            |                       |     |
| ---------- | -------- | ------- | ---------- | --------------------- | --- |
| Anonlinear | relation | between | thecontrol | signal andthemeasure- |     |
ment signal can be obtained for reasons other than nonlinearities in
thevalve. Forexample, theremightbenonlinearities inthesensor or
transmitter. As pointed out in Section 6.3, it is important to under-
stand the cause of the nonlinearity in order to determine a suitable
| gain-scheduling | reference. |     |     |     |     |
| --------------- | ---------- | --- | --- | --- | --- |
Noise
Another important issue to consider before tuning the controller is
the disturbances acting on the control loop. Wehave pointed out that
| itisimportanttoknowifthemajordisturbancesaresetpoint |     |     |     |     | changes |
| ---------------------------------------------------- | --- | --- | --- | --- | ------- |
(the servo problem) or load disturbances (the regulator problem).
It is also important to investigate the level of the measurement
|           |               |          | (Compare | 2.8.)        |        |
| --------- | ------------- | -------- | -------- | ------------ | ------ |
| noise and | its frequency | content. |          | with Section | If the |
noise level is high, it might be necessary to filter the measurement
signal before it enters the control algorithm. This is an easy way to
getrid of high-frequency noise. Ifthere aredisturbances with a large
frequency content near the ultimate frequency, it is not possible to
use low-pass filtering toremove them. Feedforward is one possibility,
ifthe disturbances canbemeasured attheir source. Notch filters can

268 Chapter 6 Automatic Tuningand Adaptation
be used if the noise is concentrated to a narrow frequency range. See
Section2.8wherenoisemodeling andmeasurements werediscussed.
SamplingRatesandPrefilters
Selectionofsamplingratesandtheassociatedprefilterareimportant
in all digital controllers. For single-loop controllers is is customary
to choose a constant sampling rate, often between 0.1 s and 1 s.
Faster rates are introduced when permitted by the processor speed.
Distributed control systems have somewhat greater flexibility.
The sampling rate should of course bechosen based on the band-
width of the control loop. In process control systems, sampling rates
have as a rule been chosen routinely without the proper considera-
tions of these issues. The reason for this is simply that there is not
muchonecandowhenthebandwidthofthecontrolloopisnotknown.
There are many new possibilities in this area when auto-tuning is
used.Afteratuning itispossible tochoosethesampling rateandthe
prefilter in a rational way. The control quality canoften beincreased
significantly by such a procedure. The prefilter should be matched to
thesamplingrate.Thiscaneasilybeachievedbyusingdualsampling
rates. The process variable is filtered and sampled with a fixed, fast
sampling rate.Digital filtering withavariable bandwidth isthen ap-
plied and the filtered signal is sampled at the rate appropriate for
the control loop.
On-LineDetection
We have shown some tests that can be performed manually by the
operator inorder toensure thatthecontrol loop isproperly designed.
The problems mentioned can also show up after a while, when the
control loop is in automatic mode. On-line detection procedures are,
therefore, of interest, and the research in this area has gained a lot
of interest in recent years. Most controllers have a primitive form of
diagnosis intheuseofalarmsonlimits onthemeasured signals. The
operator thus gets an alarm when signals exceed certain specified
alarm limits. More sophisticated detection procedures, where alarms
are given when problems like those mentioned above arise, will be
available in industrial products within the next few years.
A common approach to fault detection is shown in Figure 6.18. If
amodeloftheprocessisavailable, thecontrolsignalcanbefedtothe
inputoftheprocessmodel.Bycomparingtheoutputofthemodelwith
the true process output, one can detect when the process dynamics
change.Ifthemodel isgood, thedifference between themodeloutput
and the process output (e) is small. If the process dynamics change,

6.7 Integrated Tuningand Diagnosis 269
Model
−
e
Σ
+
y
sp
Controller Process
Figure 6.18 Model-based fault detection.
ewillnolonger besmall,sincethetworesponses tothecontrolsignal
aredifferent.Itisalsopossibletocompareothersignalsintheprocess
and the model rather than the output signals. These fault detection
methods are called observer-based methods.
Another fault detection approach is to use a recursive parameter
estimator in the same way as the model-based continuous adaptive
controller, and to base the detection on the changes in the parameter
estimates. These methods are called identification-based methods.
IntegratedTuningandDiagnosis
The diagnosis procedures are related to the adaptive techniques in
several ways. We have pointed out the importance of checking valves
before applying an automatic tuning procedure. If not, the automatic
tuning procedure will not provide the appropriate controller param-
eters. For this reason, it would be desirable to have these checks in-
corporated in the automatic tuning procedures. Such devices are not
yetavailable, andtheappropriatechecks,therefore, mustbemadeby
the operator.
Theon-linedetectionmethodsarerelatedtothecontinuousadap-
tive controller. The adaptive controller monitors the control loop per-
formance and changes the controller parameters, if the process dy-
namics change. The on-line fault detection procedures also monitor
the control-loop performance. They give an alarm instead of chang-
ing the controller parameters if the process dynamics change. As an
example, in Figure 6.12 we have seen that it is important to deter-
minewhytheperformancehaschangedbeforeactionsaretaken.Most
adaptive controllers applied to a process with stiction will detune the
controller, since they interpret the oscillations as caused by a badly
tuned controller. Consequently, it is desirable to supply the adaptive
controllers with on-line detection methods, so that reasons for bad
control-loop performance, other than poor controller tuning, are de-
tected. The lack of these kinds of detection procedures in adaptive

270 Chapter 6 Automatic Tuning and Adaptation
controllers are perhaps the major reason for the relatively few appli-
cations of continuous adaptive control available today.
6.8 Conclusions
The adaptive techniques are relatively new. Even though they have
been tried industrially for only a few years, there are currently sev-
eral thousand loops where adaptive techniques are used. This is not
a negligible number, but it is still a very small fraction of all con-
trol loops in operation. It is clear that auto-tuning is useful. It can
certainly help operators and instrument engineers keep the control
loopswelltuned. Thebenefitsareevenlargerformorecomplexloops.
For example, the derivative action is often switched off in manually
tuned systems because of tuning problems, in spite of the fact that it
improves performance.
Concerning the particular method to use, it is too early to draw
definiteconclusions. Therearemanydifferentwaystodetermine pro-
cess characteristics, many methods for design of PID controllers, and
manywaysofcombining suchtechniques tocreateauto-tuners. Judg-
ing from the systems that are now on the market, it appears that
many different ideas have been successfully implemented. However,
some patterns do emerge. It appears that more sophisticated meth-
ods require more prior information. This is probably what has led to
the introduction of the pre-tune mode, which often has been an af-
terthought. It would seem that a useful approach to this problem is
to combine several different approaches. It also seems very natural
to combine adaptive techniques with diagnosis and loop assessment.
6.9 References
Controllers with automatic tuning grew out of research on automatic
control. Overviews of adaptive techniques are found in (Dumont,
1986), (Åström, 1987a), and (Bristol, 1970). More detailed treat-
ments are found in the books (Harris and Billings, 1981), (Åström
and Wittenmark, 1989), and (Hang et al., 1993b). Overviews of dif-
ferent approaches and different products are found in (Isermann,
1982),(Gawthrop,1986),(KayaandTitus,1988),(Morris,1987),(Ya-
mamoto, 1991), and (Åström et al., 1993).
Manydifferent approaches areused intheautomatic tuners. The
systems described in (Nishikawa et al., 1984), (Kraus and Myron,
1984),and(Takatsuetal.,1991)arebasedontransientresponsetech-
niques.Thepaper(HangandSin,1991)isbasedoncrosscorrelation.

6.9 References 271
The use of orthonormal series representation of the step response of
thesystemisproposedin(Zervosetal.,1988).Thesystemin(Åström
and Hägglund, 1984) uses relay feedback. Other ways to use relay
feedback are discussed in (Schei, 1992) and (Leva, 1993). The paper
(Voda and Landau, 1995) describes a technique where the methods
BO and SO are combined with relay tuning. The hysteresis of the
relay is adjusted automatically so that the frequencyω , where the
135
processhasaphaselagat135 ○ ,isdetermined.Thepaper(Hangetal.,
1993a) discusses effects on load disturbances when relay feedback is
used.
Traditional adaptive techniques based on system identification
and control design have also been used. Identification is often based
on estimation of parameters in a transfer function model. Examples
of this approach are in (Hawk, 1983), (Hoopes et al., 1983), (Yarber,
1984a),(Yarber, 1984b),and (Cameron and Seborg, 1983).There are
alsosystemswherethecontrollerisupdateddirectlyasin(Radkeand
Isermann,1987),(MarsikandStrejc,1989),and(RadandGawthrop,
1991).
Gain scheduling is a very powerful technique that was developed
in parallel with adaptation. An example demonstrating the benefits
of gain scheduling is given in (Whatley and Pott, 1984). The paper
(Hägglund and Åström, 1991) describes commercial controllers that
combinegainschedulingwithautomatictuningandadaptation.Auto-
matic tuning can be particularly useful for start-up, this is discussed
in (Hess et al., 1987).
Several schemes are based on pattern recognition and attempts
to mimic an experienced operator. Rules in the form of logic or fuzzy
logic areoften used. Some examples are found in the papers (Bristol,
1967),(Porteretal.,1987),(Andersonetal.,1988),(Kleinetal.,1991),
(Pagano, 1991), and (Swiniarski, 1991).
The information about the commercial systems is very uneven.
Some systems are described in detail in journal publications. Other
systems are only described in manuals and other material from the
manufacturer of the devices. Several tuning aids are implemented
in hand-held computers or as software in PCs where the user is
enteringtheprocess information throughakeyboard.Someexamples
are (Blickley, 1988), (Tyreus, 1987), and (Yamamoto, 1991). A brief
presentation of the PIDWIZ system, which is based on a hand-held
calculator, is given in (Blickley, 1988).
There is much information about the Foxboro EXACT controller.
It is based on early work by Bristol on pattern recognition see, e.g.,
(Bristol, 1967), (Bristol, 1970), (Bristol et al., 1970), (Bristol, 1977),
(Bristol and Kraus, 1984), and (Bristol, 1986). The product is de-
scribed in (Kraus and Myron, 1984), and operational experience is
presented in (Higham, 1985) and (Callaghan et al., 1986).

| 272 Chapter |     | 6 Automatic | Tuningand |     | Adaptation |     |     |     |
| ----------- | --- | ----------- | --------- | --- | ---------- | --- | --- | --- |
The systems based on relay feedback are also well documented.
|                |     |               |     | (Åström |     |           | 1984). |      |
| -------------- | --- | ------------- | --- | ------- | --- | --------- | ------ | ---- |
| The principles |     | are presented |     | in      | and | Hägglund, |        | Many |
details about implementation and applications are given in (Åström
and Hägglund, 1988) and (Hägglund and Åström, 1991). The con-
trollers of this type now include automatic tuning, gain scheduling,
| and continuous |        | adaptation | of     | feedback  | and | feedforward | gains. |        |
| -------------- | ------ | ---------- | ------ | --------- | --- | ----------- | ------ | ------ |
|                |        | (McMillan  |        | 1993b)and |     | (McMillan   |        | 1993a) |
| The            | papers |            | etal., |           |     |             | etal., |        |
describetheFisher Rosemount products for tuning andgainschedul-
ing. The Yokogawa systems are discussed in (Takatsu et al., 1991)
| (Yamamoto, |     | 1991). |     |     |     |     |     |     |
| ---------- | --- | ------ | --- | --- | --- | --- | --- | --- |
and
We have not found any journal articles describing the Protuner
and Honeywell’s tuners. The interested reader is recommended to
| contact | the companies |     | directly. |     |     |     |     |     |
| ------- | ------------- | --- | --------- | --- | --- | --- | --- | --- |
There have been comparisons of different auto-tuners and adap-
tive controllers, but few results from those studies have reached the
public domain. Some papers that deal with the issue are (Nachtigal,
| 1986a), | (Nachtigal, | 1986b), | (Dumont,  |     | 1986),    | (Dumont |         | 1989).      |
| ------- | ----------- | ------- | --------- | --- | --------- | ------- | ------- | ----------- |
|         |             |         |           |     |           |         | et al., |             |
|         |             |         |           |     |           | (Frank, |         | 1990), (Is- |
| Fault   | detection   | and     | isolation | is  | discussed | in      |         |             |
ermann, 1984), (Isermann et al., 1990), and (Patton et al., 1989).
|           | (Hägglund, |     | 1993) |           |     |                 |     |           |
| --------- | ---------- | --- | ----- | --------- | --- | --------------- | --- | --------- |
| The paper |            |     |       | describes | a   | fault detection |     | technique |
that has been incorporated in a commercial controller. More elabo-
rate controllers that combine control and diagnosis are discussed in
| (Antsaklis |     | 1991) | (Åström, |     | 1992). |     |     |     |
| ---------- | --- | ----- | -------- | --- | ------ | --- | --- | --- |
|            | et  | al.,  | and      |     |        |     |     |     |

Control Paradigms
7.1 Introduction
Sofarwehaveonlydiscussedsimplecontrolproblemswithonecontrol
variable and one measured signal. Typical process control systems
can be much more complex with many control variables and many
measured signals. Thebottom-up approach is one way todesign such
systems. In this procedure the system is built up from simple com-
ponents. The systems can be implemented in many different ways.
Originally it was done by interconnection of separate boxes built of
pneumatic or electronic components. Today the systems are typically
implemented in distributed control systems consisting of several hi-
erarchically connected computers. The software for the distributed
control system is typically constructed so that programming can be
done by selecting and interconnecting the components. The key com-
ponent, the PID controller, has already been discussed in detail. In
Section 3.5 we showed that integrator windup could be avoided by
introducing nonlinearities in the PID controller. In Chapter 6 it was
demonstrated thatcontrollers couldbetuned automatically, alsothat
thechangesinsystembehaviorcouldbedealtwithbygainscheduling
and adaptation. In this chapter, we present some of the other compo-
nentsrequired tobuildcomplexautomation systems. Wealsopresent
some of the key paradigms that guide the construction of complex
systems.
A collection of paradigms for control are used to build complex
systems from simple components. The components are controllers of
the PID type, linear filters, and static nonlinearities. Typical nonlin-
earities are amplitude and rate limiters and signal selectors. Feed-
back is an important paradigm. Simple feedback loops are used to
keep process variables constant or to make them change in speci-
fied ways. (Feedback has been discussed extensively in the previous
chapters.) Thekey problem is todetermine the control variables that
should be chosen to control given process variables. Another problem
is that there may be interaction between different feedback loops. In
this chapter we discuss other paradigms for control. Cascade control
273

| 274 | Chapter | 7 Control | Paradigms |     |     |     |     |
| --- | ------- | --------- | --------- | --- | --- | --- | --- |
Process
y
|     |   sp |     |        |     | y      |     | y   |
| --- | ---- | --- | ------ | --- | ------ | --- | --- |
|     |      |     |        |  u  |    s   |     |     |
|     |      | C   |   C  s |     | P      | P   |     |
|     |      | p   |        |     |      1 | 2   |     |

Inner loop
Outer loop
|     | Figure | 7.1 Block | diagram | of  | asystem withcascade | control. |     |
| --- | ------ | --------- | ------- | --- | ------------------- | -------- | --- |
is one way to use several measured signals in a feedback loop. (See
7.2.)
Section Feedback is reactive in the sense that there must be an
error before control actions are taken. Feedforward is another con-
trolconcept that isproactive because control actions aretaken before
thedisturbance hasgenerated anyerrors.Feedforward control is dis-
cussed inSection 7.3.Model following isacontrol concept thatmakes
it possible for a system to respond in a specified way to command
signals. Section 7.4 presents this paradigm, which also can be com-
binedveryeffectivelywithfeedbackandfeedforward.Difficultiesmay
arisewhenseveralfeedbackloopsareused.InSection7.5wedescribe
somenonlinear elements andsome associated paradigms: surgetank
control, ratio control, split range control, and selector control. In Sec-
tions 7.6 and 7.7 we discuss neural and fuzzy control. These methods
can be viewed as special versions of nonlinear control. In Section 7.8
wediscusssomedifficultiesthatmayarizeininterconnectedsystems.
Section7.9usesanexampletoillustratehowthedifferentcomponents
andparadigmscanbeused.Someimportantobservationsmadeinthe
| chapter | are     | summarized | in Section |     | 7.10. |     |     |
| ------- | ------- | ---------- | ---------- | --- | ----- | --- | --- |
| 7.2     | Cascade |            | Control    |     |       |     |     |
Cascade control can be used when there are several measurement
signals and one control variable. It is particularly useful when there
aresignificantdynamics,e.g.,longdeadtimesorlongtimeconstants,
betweenthecontrolvariableandtheprocessvariable.Tightercontrol
can then be achieved by using an intermediate measured signal that
responds faster to the control signal. Cascade control is built up by
nestingthecontrolloops,asshownintheblockdiagraminFigure7.1.
The system in this figure has two loops. The inner loop is called the
secondary loop; the outer loop is called the primary loop. The reason

|     |     |     | 7.2 Cascade Control | 275 |
| --- | --- | --- | ------------------- | --- |
0.4
0
| 0   |     | 10  | 20  | 30  |
| --- | --- | --- | --- | --- |
0
−0.5
−1
| 0      |               | 10                    | 20           | 30   |
| ------ | ------------- | --------------------- | ------------ | ---- |
| Figure | 7.2 Responses | to a load disturbance | for a system | with |
(fullline)andwithout(dashedline)cascadecontrol.Theupperdi-
| agramshowsprocessoutput |     | yandthelowerdiagramshowscontrol |     |     |
| ----------------------- | --- | ------------------------------- | --- | --- |
| signal                  | u.  |                                 |     |     |
for this terminology is that the outer loop deals with the primary
measured signal. It is also possible to have a cascade control with
more nested loops. The performance of a system can be improved
with a number of measured signals, up to a certain limit. If all state
variables are measured, it is often not worthwhile to introduce other
measured variables. In such a case the cascade control is the same
asstatefeedback. Wewillillustrate thebenefits ofcascade control by
an example.
| EXAMPLE | 7.1 Improved | load disturbance | rejection |     |
| ------- | ------------ | ---------------- | --------- | --- |
Consider the system shown in Figure 7.1. Let the transfer functions
be
1
=
|     |     | G p1 s+1 |     |     |
| --- | --- | -------- | --- | --- |
and
|     |     | = 1 |     |     |
| --- | --- | --- | --- | --- |
G
p2 (s+1)3
Assume that a load disturbance enters at the input of the process.
There is significant dynamics from the control variable to the pri-
mary output. The secondary output does respond much faster than
the primary output. Thus, cascade control can be expected to give
improvements. With conventional feedback, it is reasonable to use
a PI controller with the parameters K = 0.37 and T = 2.2. These
i
parameters are obtained from the simple tuning rules presented in
Chapter 5. The response of the system to a step change in the load
| disturbance | is shown | in Figure 7.2. |     |     |
| ----------- | -------- | -------------- | --- | --- |

| 276   | Chapter 7 Control | Paradigms        |          |          |        |
| ----- | ----------------- | ---------------- | -------- | -------- | ------ |
| Since | the response      | of the secondary | measured | variable | to the |
control signal is quite fast, it is possible to use high loop gains in
the secondary loop. If the controller in the inner loop is proportional
with gain K s , the dynamics from the setpoint of C s to process output
becomes
K
|     |     | G(s)=  | s       |     |     |
| --- | --- | ------ | ------- | --- | --- |
|     |     | (s+1+K | )(s+1)3 |     |     |
s
This is faster than the open loop dynamics, and higher controller
| gainscanbeusedintheouterloop.With |     |     | K =5intheinnerloopand |     |     |
| --------------------------------- | --- | --- | --------------------- | --- | --- |
s
|               | =0.55andT | =1.9intheouterloop,theresponses |     |     |     |
| ------------- | --------- | ------------------------------- | --- | --- | --- |
| PIcontrolwith | K         |                                 |     |     |     |
i
shown in Figure 7.2 are obtained. The PI controller parameters are
obtained from the simple tuning rules presented in Chapter 5. The
figure shows that the disturbance response is improved substantially
byusingcascadecontrol.Noticeinparticularthatthecontrolvariable
dropsverymuchfasterwithcascadecontrol.Themainreasonforthis
is the fast inner feedback loop, which detects the disturbance much
| faster than | the outer | loop. |     |     |     |
| ----------- | --------- | ----- | --- | --- | --- |
The secondary controller is proportional and the loop gain is 5.
A large part of the disturbance is eliminated by the inner loop. The
remaining error is eliminated at a slower rate through the action
of the outer loop. In this case integral action in the inner loop will
| always | give an overshoot | in the disturbance | response. |     |     |
| ------ | ----------------- | ------------------ | --------- | --- | --- |
ChoiceofSecondaryMeasuredVariables
It is important to be able to judge whether cascade control can give
improvement and to have a methodology for choosing the secondary
measured variable. This is easy to do if we just remember that the
key idea of cascade control is toarrange atight feedback loop around
a disturbance. In the ideal case the secondary loop can be so tight
so that the secondary loop is a perfect servo wherein the secondary
measured variable responds very quickly to the control signal. The
| basic rules | for selecting | the secondary | variable | are: |     |
| ----------- | ------------- | ------------- | -------- | ---- | --- |
• There should be awell-defined relation between the primary and
| secondary | measured | variables. |     |     |     |
| --------- | -------- | ---------- | --- | --- | --- |
•
| Essential | disturbances | should | act in the inner | loop. |     |
| --------- | ------------ | ------ | ---------------- | ----- | --- |
•
The inner loop should be faster than the outer loop. The typical
rule of thumb is that the average residence times should have a
| ratio | of at least | 5.  |     |     |     |
| ----- | ----------- | --- | --- | --- | --- |
• It should be possible to have a high gain in the inner loop.
A common situation is that the inner loop is a feedback around an
actuator. The reference variable in the inner loop can then represent
a physical quantity, like flow, pressure, torque, velocity, etc., while

|     |     |     |     |     | 7.2 Cascade Control | 277 |
| --- | --- | --- | --- | --- | ------------------- | --- |
v
|     | A   |     | v   |     | D   |     |
| --- | --- | --- | --- | --- | --- | --- |
y
|     | u   |     | y   | y   |     |     |
| --- | --- | --- | --- | --- | --- | --- |
s
|     |     | T=1 |     | T=10 |     |     |
| --- | --- | --- | --- | ---- | --- | --- |
u
|     |     | v    |     |     |     | y   |
| --- | --- | ---- | --- | --- | --- | --- |
|     | B   |      |     |     |     | s   |
|     | u   |      | y   | y   |     |     |
|     |     | T=10 | s   | T=1 |     |     |
y
E
|     | C   |     |     | v   | u   |     |
| --- | --- | --- | --- | --- | --- | --- |
v
y
|     | u   |     | y   | y   |     | s   |
| --- | --- | --- | --- | --- | --- | --- |
s
|     | Figure | 7.3 | Examplesof | different | process and measurement | con- |
| --- | ------ | --- | ---------- | --------- | ----------------------- | ---- |
figurations.
the control variable of the inner loop could be valve pressure, control
current, etc. This is also a typical example where feedback is used to
make a system behave in a simple predictive way. It is also a very
| good | way | to linearize | nonlinear | characteristics. |     |     |
| ---- | --- | ------------ | --------- | ---------------- | --- | --- |
A number of different control systems with one control variable
and two measured signals are shown in Figure 7.3. In the figure the
control variable is represented by u, the primary measured variable
by y,thesecondary measuredvariableby y,andtheessential s distur-
banceisv.WiththerulesgivenaboveitisonlycaseAthatissuitable
| for | cascade | control. |     |     |     |     |
| --- | ------- | -------- | --- | --- | --- | --- |
ChoiceofControlModes
When the secondary measured signal is chosen it remains to choose
the appropriate control modes for the primary and secondary con-
trollers and to tune their parameters. The choice is based on the
dynamics oftheprocess andthenature ofthedisturbances. Itisvery
difficult to give general rules because the conditions can vary signif-
icantly. In critical cases it is necessary toanalyze and simulate. It is,
| however, |     | useful | to have | an intuitive | feel for the problems. |     |
| -------- | --- | ------ | ------- | ------------ | ---------------------- | --- |
Consider the system in Figure 7.1. To have a useful cascade con-
trol, it is necessary that the process P be slower than P and that
|     |     |     |     |     | 2   | 1   |
| --- | --- | --- | --- | --- | --- | --- |
theessential disturbancesacton P 1 .Weassumethattheseconditions
are satisfied. The secondary controller can often be chosen as a pure
proportional controller or a PD controller. In some cases integral ac-
tion canbeuseful toimprove rejection of low-frequency disturbances.
With controllers not having integral action, there may be a static er-

| 278 | Chapter 7 | Control | Paradigms |     |     |     |     |
| --- | --------- | ------- | --------- | --- | --- | --- | --- |
ror in the secondary loop. This may not be a serious drawback. The
secondary loop, asarule, isused toeliminate fastdisturbances. Slow
disturbances caneasilybeeliminated bytheprimaryloop, whichwill
typically have integral action. There are also drawbacks to using in-
tegral control in the secondary loop. With such a system there will
always be an overshoot in the response of the primary control loop.
Integral action isneeded if the process P contains essential time de-
2
lays and the process P is such that the loop gain in the secondary
1
| loop must  | be limited.        |     |     |     |                     |     |         |
| ---------- | ------------------ | --- | --- | --- | ------------------- | --- | ------- |
| Thespecial | casewhentheprocess |     |     |     | P isapureintegrator |     | isquite |
2
common.Inthiscaseintegral actionintheinnerloopisequivalent to
proportional control intheouter loop. Ifintegral action isusedinthe
inner loop, theproportional action intheouter loop mustbereduced.
This is a significant disadvantage for the performance of the system.
A good remedy is to remove the integrator in the inner loop and to
| increase | the gain | in the | outer | loop. |     |     |     |
| -------- | -------- | ------ | ----- | ----- | --- | --- | --- |
TuningandCommissioning
Cascade controllers must be tuned in a correct sequence. The outer
loop should first be put in manual when the inner loop is tuned. The
inner loop should then be put in automatic when tuning the outer
loop. Theinner loop isoften tuned for critical or overcritical damping
|     |     |     |     |     | (M ). |     |     |
| --- | --- | --- | --- | --- | ----- | --- | --- |
or equivalently for a small sensitivity If this is not done there
s
| is little     | margin for | using | feedback |       | in the outer | loop.         |            |
| ------------- | ---------- | ----- | -------- | ----- | ------------ | ------------- | ---------- |
| Commissioning |            | of    | cascade  | loops | also         | requires some | considera- |
tions. The following procedure can be used if we start from scratch
| with both | controllers | in  | manual | mode. |     |     |     |
| --------- | ----------- | --- | ------ | ----- | --- | --- | --- |
1. Adjust the setpoint of the secondary controller tothe value of the
| secondary | process |     | variable. |     |     |     |     |
| --------- | ------- | --- | --------- | --- | --- | --- | --- |
2. Set the secondary controller in automatic with internal setpoint
selected.
3. Adjust the primary controller so that its setpoint is equal to the
process variable and so that its control signal is equal to the
| setpoint  | of the        | secondary |            | controller. |              |           |     |
| --------- | ------------- | --------- | ---------- | ----------- | ------------ | --------- | --- |
| 4. Switch | the secondary |           | controller |             | to external  | setpoint. |     |
| 5. Switch | the primary   |           | controller |             | to automatic | mode.     |     |
Thesteps given above areautomated todifferent degrees in different
controllers. Iftheprocedure isnot done intheright waytherewill be
| switching | transients. |     |     |     |     |     |     |
| --------- | ----------- | --- | --- | --- | --- | --- | --- |

7.2 Cascade Control 279
IntegralWindup
If integral action is used in both the secondary and primary control
loops, it is necessary to have a scheme to avoid integral windup. The
inner loop can be handled in the ordinary way, but it is not a trivial
task to avoid windup in the outer loop. There are three situations
that must be covered:
1. The control signal in the inner loop can saturate.
2. The secondary control loop may be switched to internal setpoint.
3. The secondary controller is switched from automatic to manual
mode.
The feedback loop, as viewed from the primary controller, is broken
in all these cases, and it is necessary to make sure that its integral
modeisdealtwithproperly.Thisproblemissolved automatically ina
number of process controllers that have cascade control capabilities,
but if we build up the cascade control using two independent con-
trollers, we have to solve the problem ourselves. This requires being
able to inject a tracking signal into the primary controller.
If the output signal of the secondary controller is limited, the
process variable of the secondary controller should be chosen as the
tracking signal in the primary controller. This also needs a digital
transfer from the secondary to the primary controller telling it when
the tracking is to take place.
In the case where the secondary controller switches to working
according to its local setpoint instead of the external one from the
primary controller, the local setpoint should be sent back to the pri-
mary controller as a tracking signal. In this way one can avoid both
integrator windup and jumps in the transition to cascade control.
When the secondary controller switches over to manual control,
theprocessvariablefromthesecondarycontrollershouldbesentback
to the primary controller as a tracking signal.
SomeApplications
Cascade control is a convenient way to use extra measurements to
improve control performance. The following examples illustrate some
applications.
EXAMPLE 7.2 Valve positioners
Controlloopswithpneumatic valves isaverycommonapplication. In
this case the inner loop is a feedback around the valve itself where
thevalve position ismeasured. The inner loop reduces theinfluences
of pressure variations and various nonlinearities in the pneumatic
system.

| 280 | Chapter | 7 Control | Paradigms |     |     |     |
| --- | ------- | --------- | --------- | --- | --- | --- |
y
|   sp |     |     |     |            | I v   | y   |
| ---- | --- | --- | --- | ---------- | ----- | --- |
|      |     |     |     | Amplifier  |       | 1   |
|      | PC  | VC  | CC  |            | Motor | s   |
Figure 7.4 Block diagram of a system for position control. The
systemhasthreecascadedloopswithacurrentcontroller(CC)with
feedbackfromcurrent(I),avelocitycontroller(VC)withfeedback
fromvelocity(v),andapositioncontroller(PC)withfeedbackfrom
|         | position (y). |               |     |     |     |     |
| ------- | ------------- | ------------- | --- | --- | --- | --- |
| EXAMPLE | 7.3           | Motor control |     |     |     |     |
Figure 7.4 is a block diagram of a typical motor control system. This
system has three cascaded loops. The innermost loop is a current
loop where the current is measured. The next loop is the velocity
loop, which is based on measurement of the velocity. The outer loop
is a position loop. In this case integral action in the velocity loop is
equivalent to proportional action in the position loop. Furthermore,
it is clear that the derivative action in the position loop is equivalent
with proportional action in the velocity loop. From this it follows
directly that there is no reason to introduce integral action in the
velocity controller or derivative action in the position controller.
| EXAMPLE | 7.4 | Heat exchanger |     |     |     |     |
| ------- | --- | -------------- | --- | --- | --- | --- |
Aschematic diagram of a heat exchanger isshown in Figure 7.5.The
purpose of the control system is to control the outlet temperature
on the secondary side by changing the valve on the primary side.
The control system shown uses cascade control. The secondary loop
is a flow control system around the valve. The control variable of
the primary loop is the setpoint of the flow controller. The effect of
nonlinearities inthevalve,aswellasflowandpressuredisturbances,
| are | thus reduced | by the | secondary | controller. |     |     |
| --- | ------------ | ------ | --------- | ----------- | --- | --- |
Observers
Since cascade control can use many measured signals it is natural
to ask when it is no longer worthwhile to include an extra signal.
An answer to this question has been provided by control theory. The
explanation isbased on thenotion of state of a system. The state of a
system isthesmallest number of variables, thattogether withfuture
control signals, describes the future development of a system com-
pletely. The number of state variables is, thus, a natural measure of
thenumber ofmeasured signals thatareworthwhile toinclude. Ifall

|        |     |                   |      | 7.3 FeedforwardControl |     | 281     |
| ------ | --- | ----------------- | ---- | ---------------------- | --- | ------- |
|        |     | SP                |      |                        | SP  |         |
|        |     | MV                |      |                        | MV  |         |
|        |     |                   | F    |                        | T   |         |
| Figure | 7.5 | Schematic diagram | of a | heat exchangerwith     |     | cascade |
control.
state variables are measured, it is also sufficient to use proportional
feedback from these signals. This is called state feedback and can be
| viewed | as a natural | extension | of cascade | control. |     |     |
| ------ | ------------ | --------- | ---------- | -------- | --- | --- |
Use of observers is another helpful idea from control theory. An
observer is based on a mathematical model of a process. It is driven
by the control signals to the process and the measured variables. Its
outputisanestimateofthestateofthesystem.Anobserveroffersthe
possibility of combining mathematical models with measurements to
obtain signals that can not be measured directly. A combination of
anobserver with a state feedback from the estimated states is a very
| powerful | control     | strategy. |         |     |     |     |
| -------- | ----------- | --------- | ------- | --- | --- | --- |
| 7.3      | Feedforward |           | Control |     |     |     |
Disturbances can be eliminated by feedback. With a feedback system
it is, however, necessary that there be an error before the controller
can take actions to eliminate disturbances. In some situations it is
possible to measure disturbances before they have influenced the
processes. It is then natural to try to eliminate the effects of the
disturbances before they have created control errors. This control
paradigm is called feedforward. The principle is simply illustrated
in Figure 7.6. Feedforward can be used for both linear and nonlinear
| systems. | It requires | a mathematical | model | of  | the process. |     |
| -------- | ----------- | -------------- | ----- | --- | ------------ | --- |
As an illustration we will consider a linear system that has two
inputs, the control variable u and the disturbance v, and one output
y. The transfer function from disturbance to output is G v , and the
transfer function from the control variable to the output is G . The
u
| process | can be | described by | the following | equation: |     |       |
| ------- | ------ | ------------ | ------------- | --------- | --- | ----- |
|         |        | Y(s)=        | G (s)U(s)+G   | (s)V(s)   |     | (7.1) |
|         |        |              | u             | v         |     |       |

| 282 Chapter | 7   | Control Paradigms |     |     |     |
| ----------- | --- | ----------------- | --- | --- | --- |
Process
 v
Disturbance
G
v
|     |     |        |  u  | y     |     |
| --- | --- | ------ | --- | ----- | --- |
|     |     | G      |     | G Σ   |     |
|     |     |     ff |     |     u |     |
Feedforward
Control signal
Figure 7.6 Block diagram of a system with feedforward control
| froma | measurable | disturbance. |     |     |     |
| ----- | ---------- | ------------ | --- | --- | --- |
wheretheLaplacetransformedvariablesaredenotedbycapitals.The
| feedforward | control | law |     |     |     |
| ----------- | ------- | --- | --- | --- | --- |
G (s)
|     |     | U(s)=− |     | v V(s) | (7.2) |
| --- | --- | ------ | --- | ------ | ----- |
(s)
G
u
makestheoutputzeroforalldisturbancesv.Thefeedforwardtransfer
| function thus | should | be chosen | as: |     |     |
| ------------- | ------ | --------- | --- | --- | --- |
(s)
G v
|     |     | G   | (s)=− |       | (7.3) |
| --- | --- | --- | ----- | ----- | ----- |
|     |     |     | ff    | G (s) |       |
u
The feedforward compensator is, in general, a dynamic system.
The transfer function G must, of course, be stable, which means
ff
that G must also be stable. If the processes are modeled as static
v
systems, the feedforward compensator is also a static system. This is
| called static | feedforward. |     |     |     |     |
| ------------- | ------------ | --- | --- | --- | --- |
If the transfer functions characterizing the process are given by
|     |     | K    |     | K    |       |
| --- | --- | ---- | --- | ---- | ----- |
|     |     | =    | u   | = v  | (7.4) |
|     |     | G u  |     | G v  |       |
|     |     | 1+sT |     | 1+sT |       |
u v
(7.3)
it follows from Equation that the feedforward transfer function
is
1+sT
K
|     |     | G   | =− v | ⋅ u  | (7.5) |
| --- | --- | --- | ---- | ---- | ----- |
|     |     | ff  |      | 1+sT |       |
|     |     |     | K u  | v    |       |
In this case the feedforward compensator is a simple dynamic com-
| pensator of | a lead-lag | type. |     |     |     |
| ----------- | ---------- | ----- | --- | --- | --- |
Since the key idea is to cancel two signals, it is necessary that
the model is reasonably accurate. A modeling error of 20% implies
that only 80% of the disturbance is eliminated. Modeling errors are
directly reflected in control errors. Feedforward is typically much
| more sensitive | to modeling |     | errors than | feedback control. |     |
| -------------- | ----------- | --- | ----------- | ----------------- | --- |

|                        |     |     |                          | 7.3 FeedforwardControl |            | 283 |
| ---------------------- | --- | --- | ------------------------ | ---------------------- | ---------- | --- |
| Sinceitrequiresprocess |     |     | models, feedforwardisnot |                        | usedasmuch |     |
as feedback control. There are, however, many cases where a lead-
lag filter, as given in Equation (7.5), or even a constant feedforward
gives excellent results. The availability of adaptive techniques has
drasticallyincreasedtherangeofapplicabilityoffeedforward.Certain
standard controllers have a feedforward term. Feedforward is also
| easy     | to include | in distributed | control            | systems. |             |      |
| -------- | ---------- | -------------- | ------------------ | -------- | ----------- | ---- |
| Feedback | and        | feedforward    | have complementary |          | properties. | With |
feedback it is possible to reduce the effect of the disturbances with
frequencies lower than the system bandwidth. By using feedforward
we can also reduce the effects of faster disturbances. Feedback is
relatively insensitive to variations in the process model while feed-
forward, which is used directly in a process model, is more sensitive
to parameter variation. Feedback may cause instabilities while feed-
forwarddoes not give rise toany stability problems. To obtain a good
control system, it is desirable to combine feedback and feedforward.
Applications
In many process control applications there are several processes in
series. Insuchcases itisofteneasy tomeasure disturbances anduse
feedforward. Typical applications of feedforward control are: drum-
level control in steam boilers, control of distillation columns and
rolling mills. An application of combined feedback and feedforward
control follows.
|     | 7.5 | Drum level | control |     |     |     |
| --- | --- | ---------- | ------- | --- | --- | --- |
EXAMPLE
A simplified diagram of a steam boiler is shown in Figure 7.7. The
water in the raiser is heated by the burners. The steam generated
in the raiser, which is lighter than the water, rises toward the drum.
Steam valve
|     | Feed |     | F   | F   |     |     |
| --- | ---- | --- | --- | --- | --- | --- |
water
|     |     |     | L Drum |     |         |     |
| --- | --- | --- | ------ | --- | ------- | --- |
|     | Oil |     |        |     | Turbine |     |
Air
|        |     | Raiser                                         | Down comer |     |     |     |
| ------ | --- | ---------------------------------------------- | ---------- | --- | --- | --- |
| Figure | 7.7 | Schematicdiagramofadrumboilerwithlevelcontrol. |            |     |     |     |

| 284 | Chapter | 7   | Control | Paradigms |     |     |     |
| --- | ------- | --- | ------- | --------- | --- | --- | --- |
Thiscausesacirculationaroundtheloopconsistingoftheraisers,the
drum, and the down comers. The steam is separated from the water
| inthedrum.Thesteam |     |     |     | flowtotheturbine | iscontrolled |     | bythesteam |
| ------------------ | --- | --- | --- | ---------------- | ------------ | --- | ---------- |
valve.
It is important to keep the water level in the drum constant.
Too low a water level gives insufficient cooling of the raisers, and
there is a risk of burning. With too high a water level, water may
move into the turbines, which may cause damage. There is a control
system for keeping thelevel constant. Thecontrol problem isdifficult
because of the so-called shrink and swell effect. It can be explained
as follows: Assume that the system is in equilibrium with a constant
drum level. If the steam flow is increased by opening the turbine
valve, the pressure in the drum will drop. The decreased pressure
causes generation of extra bubbles in the drum and in the raisers.
Asaresult thedrum level will initially increase. Since moresteam is
taken out of the drum, the drum level will of course finally decrease.
This phenomena, which is called the shrink and swell effect, causes
severe difficulties in the control of the drum level. Mathematically it
also gives rise to right half plane zero in the transfer function.
The problem can be solved by introducing the control strategy
shown in Figure 7.7. It consists of a combination of feedback and
feedforward.Thereisafeedbackfromthedrumleveltothecontroller,
butthereisalsoafeedforwardfromthedifferencebetweensteamflow
and feed-water flow so that the feedwater flow is quickly matched to
| the | steam | flow. |           |     |     |     |     |
| --- | ----- | ----- | --------- | --- | --- | --- | --- |
| 7.4 | Model |       | Following |     |     |     |     |
When discussing PID-control in Chapter 4 the main emphasis was
on load disturbance response. The setpoint response was shaped by
setpointweighting.Insomecasesitisdesirabletohavemoreaccurate
control of the setpoint response. This can be achieved by using a
referencemodelthatgivesthedesiredresponsetosetpointchanges.A
| simpleapproachisthentousetheschemeshown |     |     |     |     |     | inFigure7.8where |     |
| --------------------------------------- | --- | --- | --- | --- | --- | ---------------- | --- |
the output of the reference model is fed into a simple feedback loop.
|     | y   |       | y     | e            | u   |         |  y  |
| --- | --- | ----- | ----- | ------------ | --- | ------- | --- |
|     | c   |       |    sp |              |     |         |     |
|     |     | Model |       | Σ Controller |     | Process |     |
-1
|     | Figure | 7.8 | Block | diagram of a systembased |     | on modelfollowing. |     |
| --- | ------ | --- | ----- | ------------------------ | --- | ------------------ | --- |

|     |     |     |     |     | 7.4 | Model | Following | 285 |
| --- | --- | --- | --- | --- | --- | ----- | --------- | --- |
Feedforward
  ff u
|   y  c |       | y   |     | e          |     |  u  |         |  y  |
| ------ | ----- | --- | --- | ---------- | --- | --- | ------- | --- |
|        |       | sp  | Σ   |            |     | Σ   |         |     |
|        | Model |     |     | Controller |     |     | Process |     |
−1
Figure 7.9 Block diagram of a system that combines model fol-
| lowing | and | feedforward | from | thecommand | signal. |     |     |     |
| ------ | --- | ----------- | ---- | ---------- | ------- | --- | --- | --- |
The reference model is typically chosen as a dynamic system of first
or second order. In this case we obtain model following by combining
a simple controller with a model. It is necessary that the feedback
loop be very fast relative to the response of the reference model.
The system can be improved considerably by introducing feedfor-
| wardasshowninFigure7.9.Inthissystem |     |     |                     |     | wehavealsofeedforward |                |     |     |
| ----------------------------------- | --- | --- | ------------------- | --- | --------------------- | -------------- | --- | --- |
| fromthecommandsignal.               |     |     | (ComparewithSection |     |                       | 7.3.)Thesignal |     | u   |
ff
is such that it will produce the desired output if the models are cor-
rect. The error ewill differ from zero when the output deviates from
its desired behavior. The feedback path will then generate the ap-
propriate actions. When implementing the system the boxes labeled
model and feedforward are often combined into one unit which has
| the command |     | signal y | as input | and | y and u | as  | outputs. |     |
| ----------- | --- | -------- | -------- | --- | ------- | --- | -------- | --- |
|             |     |          | c        |     | sp      | ff  |          |     |
The system is called a two-degree-of-freedom system because the
signalpathsfromsetpointtocontrolandprocessoutputtocontrolcan
|           |                |     |     |             |           |     | (see    | 3.4) |
| --------- | -------------- | --- | --- | ----------- | --------- | --- | ------- | ---- |
| be chosen | independently. |     | Use | of setpoint | weighting |     | Section |      |
is one way to obtain this to a small degree. The system in Figure 7.9
is the general version. For such systems it is common to design the
feedback so that the system is insensitive to load disturbances and
process uncertainties. The model and the feedforward elements are
then designed to obtain the desired setpoint response. The feedback
controller isoften chosen asa PID controller. Model following is used
when precise setpoint following is desired, for example, when several
| control | loops | have to | be coordinated. |     |     |     |     |     |
| ------- | ----- | ------- | --------------- | --- | --- | --- | --- | --- |
A GeneralControllerStructure
ThesysteminFigure7.9usesfeedforwardtoimprovecommandsignal
following. It is possible to combine this with feedforward from mea-
sured disturbances as discussed in Section 7.3. We will then obtain
the general controller structure shown in Figure 7.10. In this case
feedforward is used both to improve setpoint response and to reduce

286 Chapter 7 Control Paradigms
Feedforward
v
G Σ G
ff1 ff2
Process
y c G
m
y sp Σ e G
fb
Σ u G
p2
Σ G
p1
y
−1
Figure 7.10 Block diagram of a system that combines feedback
and feedforward.
the effects of a measurable disturbance.
Thepropertiesofthesystemareanalyzedhere.Ifthesubsystems
are linear and time invariant, we find that the Laplace transform of
the control error is given by
G (1+G G ) G −G G
E(s)=− p1 p2 ff2 V(s)+ m p ff1 Y (s) (7.6)
1+G G 1+G G c
p fb p fb
where G and G are transfer functions for feedforwards from the
ff1 ff2
commandsignalandfromthedisturbance.G isthetransferfunction
fb
for the feedback. The process has the transfer function
G = G G (7.7)
p p1 p2
It follows from Equation (7.6) that the transfer function from com-
mand signal to error is given by
G −G G
G(s)= m p ff1 (7.8)
1+G G
p fb
This transfer function is small if the loop transfer function G(cid:10) =
G G is large even without feedforward. The loop transfer function
p fb
is typically large for frequencies smaller than the servo bandwidth.
Therefore, the transfer function G is small for low frequencies even
without feedforward. By choosing the feedforward so that
G G = G (7.9)
p ff1 m
we find that the transfer function becomes zero for all frequencies,
irrespective of the feedback used. Since we are combining feedback
and feedforward, we can let the feedback handle the low frequencies
andusefeedforwardcompensationonlytodealwiththehighfrequen-
cies. Thismeans that Equation (7.9)need only besatisfied for higher

|     |     |     | 7.5 Nonlinear | Elements | 287 |
| --- | --- | --- | ------------- | -------- | --- |
frequencies. This makes the feedforward compensator simpler. Sim-
(7.6)
ilarly it follows from Equation that the transfer function from
| the disturbance | to the control | error  | is given by |     |     |
| --------------- | -------------- | ------ | ----------- | --- | --- |
|                 |                | G (1+G | G )         |     |     |
|                 |                | =− p1  | p2 ff2      |     |     |
G
|     |     | v 1+G | G   |     |     |
| --- | --- | ----- | --- | --- | --- |
p fb
Inananalogy withtheprevious discussion, wefindthatthis transfer
| function | will be zero if |     |     |     |     |
| -------- | --------------- | --- | --- | --- | --- |
G G =−1
p2 ff2
holds. The transfer function will also be small if the loop transfer
| function | G(cid:10) is large. |     |     |     |     |
| -------- | ------------------- | --- | --- | --- | --- |
These simple calculations illustrate the differences between feed-
back and feedforward. In particular they show that feedforward re-
duces disturbances by canceling two terms, while feedback reduces
the disturbances by dividing them by a large number. This clearly
demonstrates why feedforward is more sensitive than feedback.
TuningFeedforwardControllers
Feedforward controllers must be well tuned. Unfortunately, it is dif-
ficult to tune such controllers. The main difficulty is that it is often
not possible to change the disturbances in order to investigate the
disturbance response. Therefore, it is necessary to wait for a nat-
ural disturbance before the performance of the feedforward can be
| observed. | This makes tuning  | very | time consuming. |     |     |
| --------- | ------------------ | ---- | --------------- | --- | --- |
| 7.5       | Nonlinear Elements |      |                 |     |     |
Nonlinearelementshavebeendiscussedbefore.InSection3.5weused
alimitertoavoidintegralwindup, inSection3.4wediscussed thead-
dition of nonlinearities to obtain “error squared on proportional” and
similarcontrolfunctions.InChapter6itwasshownthatperformance
could be improved by gain scheduling. In this section we describe
more nonlinear elements and also present some control paradigms
| that guide | the use of these | elements. |     |     |     |
| ---------- | ---------------- | --------- | --- | --- | --- |
Limiters
Since all physical values are limited, it is useful to have limiting
devices in control systems too. A simple amplitude limiter is shown
in Figure 7.11. The limiter can mathematically be described as the

288 Chapter 7 Control Paradigms
u
u h y
u
l
Figure 7.11 Block diagram of asimple amplitude limiter.
static nonlinearity 
u(cid:10) if u≤u(cid:10)
y=

u if u(cid:10) <u<u
h
u if u≥u
h h
It is also useful to limit the rate of change of signals. A system for
doing this is shown in Figure 7.12.This circuit is called arate limiter
or a ramp unit. The output will attempt to follow the input signals.
Sincethereisintegralactioninthesystem,theinputsandtheoutputs
will be identical in steady state. Since the output is generated by an
integrator with limited input signal, the rate of change of the output
will be limited to the bounds given by the limiter. Rate limiters are
used, for example, in model-following control of the type shown in
Section 7.4. A more sophisticated limiter is shown in Figure 7.13.
This limiter is called a jump and rate limiter. The output will follow
the input for small changes in the input signal. At large changes
the output will follow the input with a limited rate. The system in
Figure 7.13 can be described by the following equations
dx
=sat(u−x)
dt
y= x+sat(u−x)
where the saturation function is defined as

−a x ≤−a
sat(x)= x (cid:2)x(cid:2)< a

a x ≥ a
If(cid:2)u−x(cid:2) ≤ait follows from the equations describing the system that
y = u, and if u ≥ x+a it follows that dx/dt = a. Thus, the output
u Σ e 1 y
s
−1
Figure 7.12 Block diagram ofa rate limiter or arampunit.

|     |     |     |     | 7.5 | Nonlinear | Elements | 289 |
| --- | --- | --- | --- | --- | --------- | -------- | --- |
|     | u   |     |     |     |           |          | y   |
|     |     | Σ   |     |     |           | Σ        |     |
x
1
s
−1
|             |          | Figure | 7.13      | Jumpand       | rate limiter. |     |     |
| ----------- | -------- | ------ | --------- | ------------- | ------------- | --- | --- |
| signal will | approach |        | the input | signal at the | rate          | a.  |     |
Limiters are used in many different ways. They can be used to
limit the command signals so that we are not generating setpoints
that are demanding faster changes than a system can cope with. In
Section3.5itwasshownhowamplitudelimitersmaybeusedtoavoid
| integral | windup | in PID | controllers. |     |     |     |     |
| -------- | ------ | ------ | ------------ | --- | --- | --- | --- |
SurgeTankControl
The control problems that were discussed in Chapter 4 were all reg-
ulation problems where the task was to keep a process variable as
close to a given setpoint as possible. There are many other control
problems that also areimportant. Surgetank control is one example.
The purpose of a surge tank is to act as a buffer between different
production processes. Flow from one process is fed to another via the
surge tank. Variations in production rate can be accommodated by
letting the level in the surge tank vary. Conventional level control,
which attempts to keep the level constant, is clearly not appropriate
in this case. To act as a buffer the level should indeed change. It is,
however,importantthatthetankneitherbecomesemptynoroverflow.
| There | are | many | approaches | to surge | tank | control. | A common, |
| ----- | --- | ---- | ---------- | -------- | ---- | -------- | --------- |
simple solution is to use a proportional controller with a low gain.
Controllers withdeadzones ornonlinear PIcontrollers arealsoused.
Gainschedulingisabettermethod.Theschedulingvariableischosen
asthetanklevel.Acontrollerwithlowgainischosenwhenthelevelis
| between10%and90%,andacontroller |     |     |     | withhighgainisusedoutside |     |     |     |
| ------------------------------- | --- | --- | --- | ------------------------- | --- | --- | --- |
the limits. There are also special schemes for surge tank control.
In many cases there are long sequences of surge tanks and pro-
duction units, as illustrated in Figure 7.14. Two different control
structures, control in the direction of the flow or opposite to the flow,
are shown in the figure. Control in the direction opposite to the flow

| 290 Chapter | 7 Control | Paradigms |     |     |
| ----------- | --------- | --------- | --- | --- |
A
B
Figure 7.14 Different structures for surge tank control The ma-
terial flow is from the left to the right. The scheme in A is called
controlinthedirectionoftheflow.TheschemeinBiscalledcontrol
| in the | directionopposite | tothe | flow. |     |
| ------ | ----------------- | ----- | ----- | --- |
is superior, because then all control loops are characterized by first-
order dynamics. With control in the direction of the flow, it is easy to
get oscillations or instabilities because of the feedback from the end
| of the chain | to the beginning. |     |     |     |
| ------------ | ----------------- | --- | --- | --- |
RatioControl
When mixing different substances it is desirable to control the pro-
portions of thedifferent media. Incombustion control, for example, it
is desirable to have a specified ratio of fuel to air. Similar situations
occur in many other process control problems. Two possible ways to
solve these problems are shown in Figure 7.15. One of the flows, y ,
k
is controlled in the normal way, and the other flow yis controlled as
in Figure 7.15A, where the setpoint is desired ratio a and the mea-
sured value is the ratio y/y . This arrangement makes the control
k
loop nonlinear, since the gain of the second controller depends on the
signal y . A better solution is the one shown in Figure 7.15B, where
k
thesignalobtained bymultiplying y k by aandaddingabiasbisused
| as the setpoint | to a PI | controller. | The error signal | is  |
| --------------- | ------- | ----------- | ---------------- | --- |
|                 |         | e=a(y       | +b)−y            |     |
k
where a is the desired ratio. If the error is zero it follows that
|     |     | y=  | ay +b |     |
| --- | --- | --- | ----- | --- |
k
Ratio controllers can easily be implemented by combining ordinary
PI and PID controllers with devices for adding and multiplying. The
control paradigm is so common that they are often combined in one
unit called a ratio controller, e.g., a Ratio PI controller (RPI). There
| are also PID  | controllers | that can | operate in ratio | mode. |
| ------------- | ----------- | -------- | ---------------- | ----- |
| We illustrate | ratio       | control  | with an example. |       |

|     |     |     | 7.5 Nonlinear | Elements | 291 |
| --- | --- | --- | ------------- | -------- | --- |
| A   |     | B   |               |          |     |
| y   |     |     | b             | a        |     |
a
|     |     | y   |     | a(y +b) |     |
| --- | --- | --- | --- | ------- | --- |
|     |     | k   | Σ Π | k       |     |
|     | SP  | u   |     |         |     |
PI
|     |      |     |     | SP  | u   |
| --- | ---- | --- | --- | --- | --- |
| Div | y PV |     |     |     | PI  |
|     |      | y   |     | PV  |     |
y
k
y
k
|         | Figure 7.15  | Block diagram | of two ratio | controllers. |     |
| ------- | ------------ | ------------- | ------------ | ------------ | --- |
| EXAMPLE | 7.6 Air-fuel | control       |              |              |     |
Operation of a burner requires that the ratio between fuel flow and
air flow is kept constant. One control system that achieves this can
be constructed from an ordinary PI controller and an RPI controller
as is shown in Figure 7.16. The fuel and the air circuits are provided
with ordinary flow control. Fuel is controlled by a PI controller, the
air flow is controlled with a ratio PI controller where the ratio signal
is the fuel flow. The bias term b is used to make sure that there is
an air flow even if there is no fuel flow. The system in Figure 7.16 is
not symmetric. A consequence of this is that there will be air excess
when the setpoint is decreased suddenly, but air deficiency when the
| setpoint | is suddenly | increased. |     |     |     |
| -------- | ----------- | ---------- | --- | --- | --- |
SplitRangeControl
Oil
MV
PI
SP
SP
RPI
MV
Air
|     | Figure 7.16 | Block diagram | of anair-fuel | controller. |     |
| --- | ----------- | ------------- | ------------- | ----------- | --- |

292 Chapter 7 Control Paradigms
Heating valve
Open
Cooling valve
Closed
0 0.5 1.0
Figure 7.17 Illustration of theconcept of split range control.
Cascadecontrolisusedwhenthereisonecontrolvariableandseveral
measured signals. The dual situation is used when there is one mea-
sured variable andseveral control variables. Systems of this type are
common, e.g., in connection with heating and cooling. One physical
device is used for heating and another for cooling. The heating and
cooling systems often have different static and dynamic characteris-
tics. The principle of split range control is illustrated in Figure 7.17,
which shows the static relation between the measured variables and
the control variables. When the temperature is too low, it is neces-
sary to supply heat. The heater, therefore, has its maximum value
when the measured variable is zero. It then decreases linearly until
mid-range,wherenoheatingissupplied. Similarly,thereisnocooling
when the measured variable is below mid-range. Cooling, however, is
applied when the process variable is above mid-range, and it then
increases.
There isacritical region when switching fromheating tocooling.
To avoid both heating and cooling at the same time, there is often
a small dead zone where neither heating nor cooling is supplied.
Switching between the different control modes may cause difficulties
and oscillations.
Split range control is commonly used in systems for heating and
ventilation. It is also useful applications when the control variable
ranges over a very large range. The flow is then separated into par-
allel paths each controlled with a valve.
SelectorControl
Selector control can be viewed as the inverse of split range control.
In split range there is one measured signal and several actuators.
In selector control there are many measured signals and only one
actuator. A selector is a static device with many inputs and one
output. There are two types of selectors: maximum and minimum.
Foramaximumselector theoutputisthelargestoftheinputsignals.

|     |     |     |     | 7.5 | Nonlinear | Elements | 293 |
| --- | --- | --- | --- | --- | --------- | -------- | --- |
There are situations where there are several controlled process
variables that must be taken into account. One variable is the pri-
mary controlled variable, but it is also required that other process
variables remain within given ranges. Selector control can be used
to achieve this. The idea is to use several controllers and to have a
selector that chooses the controller that is most appropriate. One ex-
ampleof use is where the primary controlled variable istemperature
| andwemustensurethatpressuredoesnotexceed |     |     |     |     |     | acertainrangefor |     |
| ---------------------------------------- | --- | --- | --- | --- | --- | ---------------- | --- |
safety reasons.
The principle of selector control is illustrated in Figure 7.18. The
primary controlled variable is the process output y. There is an aux-
iliary measured variable zthat should be kept within the limits z
min
and z . The primary controller C has process variable y, setpoint
max
y , and output u . There are also secondary controllers with mea-
| sp  |     | n   |     |     |     |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- |
sured process variables that are the auxiliary variable z and with
setpoints that arebounds of the variable z. The outputs of these con-
trollers are u and u . The controller C is an ordinary PI or PID
|     | h   | l   |     |     |     |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- |
controller that gives good control under normal circumstances. The
output of the minimum selector is the smallest of the input signals;
the output of the maximum selector is the largest of the inputs.
| Undernormalcircumstances |     |             | theauxiliary |      | variableislargerthan |       |     |
| ------------------------ | --- | ----------- | ------------ | ---- | -------------------- | ----- | --- |
| the minimum              |     | value z and | smaller      | than | the maximum          | value | z . |
|                          |     | min         |              |      |                      |       | max |
This means that the output u is large and the output u is small.
|     |     |     | h   |     |     | l   |     |
| --- | --- | --- | --- | --- | --- | --- | --- |
The maximum selector, therefore, selects u and the minimum selec-
n
| toralsoselects |     | u .Thesystem | actsasifthemaximum |     |     | andminimum |     |
| -------------- | --- | ------------ | ------------------ | --- | --- | ---------- | --- |
n
controller were not present. If the variable zreaches its upper limit,
the variable u becomes small and is selected by the minimum selec-
h
tor. This means that the control system now attempts to control the
u
|     | PV C | h   |     |     |     |     |     |
| --- | ---- | --- | --- | --- | --- | --- | --- |
z
| max |     | max |     |     |     |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- |
SP
| y   |     |     | M   |     |     |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- |
sp
|     |     | u   | I   | u   |     | z   | y   |
| --- | --- | --- | --- | --- | --- | --- | --- |
|     | C   | n   |     |     | G   | G   |     |
|     |     | M   | N   |     |     |     |     |
|     |     |     |     |     | 1   | 2   |     |
A
X
| z   |     |     |     |     |     | Process |     |
| --- | --- | --- | --- | --- | --- | ------- | --- |
| min |     | u   |     |     |     |         |     |
SP C l
min
PV
|     |     | Figure | 7.18 Selectorcontrol. |     |     |     |     |
| --- | --- | ------ | --------------------- | --- | --- | --- | --- |

| 294 | Chapter | 7 Control | Paradigms |     |     |
| --- | ------- | --------- | --------- | --- | --- |
variable zand drive it towards its limit. A similar situation occurs if
| the variable |     | zbecomes | smaller | than z . |     |
| ------------ | --- | -------- | ------- | -------- | --- |
min
In a system with selectors, only one control loop at a time is in
operation.Thecontrollerscanbetunedinthesamewayassingle-loop
controllers. There may be some difficulties with conditions when the
controller switches. With controllers having integral action, it is also
necessary totracktheintegral states ofthosecontrollers thatarenot
in operation. Selector control is very common in order to guarantee
thatvariables remain within constraints. Thetechnique iscommonly
used in the power industry for control in boilers, power systems,
and nuclear reactors. The advantage is that it is built up of simple
nonlinear components and PI and PID controllers. An alternative to
selector control is to make a combination of ordinary controllers and
logic. The following example illustrates the use of selector control.
| EXAMPLE | 7.7 | Air-fuel | control |     |     |
| ------- | --- | -------- | ------- | --- | --- |
InExample7.6wediscussedair-fuelcontrol.Ratiocontrolhastwodis-
advantages. When the power demand is increased, there may be lack
of air because the setpoint of the air controller increases first when
| thedualcontroller |     | hasincreasedtheoilflow.Thesystemcannotcom- |     |     |     |
| ----------------- | --- | ------------------------------------------ | --- | --- | --- |
pensateforperturbationsintheairchannel.Amuchimprovedsystem
uses selectors, such as is shown in Figure 7.19. The system uses one
minimum and one maximum selector. There is one PI controller for
fuel flow and one PI controller for the air flow. The setpoint for the
air controller is the larger of the command signal and the fuel flow.
Oil
MV
|     |     |     | M   |     | PI  |
| --- | --- | --- | --- | --- | --- |
|     |     |     | I   | SP  |     |
N
Power
demand
M
|     |     |     | A   | SP  |     |
| --- | --- | --- | --- | --- | --- |
PI
X
MV
Air
| Figure | 7.19             | Air-fuelcontroller |              | basedonselectors.Comparewith |       |
| ------ | ---------------- | ------------------ | ------------ | ---------------------------- | ----- |
| the    | ratio controller |                    | for the same | systemin Figure              | 7.16. |

|     |     |     |     | 7.6 | Neural Network Control | 295 |
| --- | --- | --- | --- | --- | ---------------------- | --- |
This means that the air flow will increase as soon as more energy is
demanded. Similarly, the setpoint to the fuel flow is the smaller of
the demand signal and the air flow. This means that when demand
isdecreased, thesetpoint tothedualflowcontroller willimmediately
be decreased, but the setpoint to the air controller will remain high
until the oil flow has actually decreased. The system thus ensures
that there will always be anexcess of air. It is important tomaintain
good air quality. It is particularly important in ship boilers because
| captainsmaypayheavypenalties |             |          |     | iftherearesmokepuffscomingout |     |     |
| ---------------------------- | ----------- | -------- | --- | ----------------------------- | --- | --- |
| of the                       | stacks when | in port. |     |                               |     |     |
MedianSelectors
A median selector is a device with many inputs and many outputs.
Its output selects the input that represents the current median of
the input signals. A special case is the two-out-of-three selector, com-
monly used for highly sensitive systems. To achieve high reliability
it is possible to use redundant sensors and controllers. By inserting
median selectors it is possible to have a system that will continue to
| function | even   | if several | components | fail.   |     |     |
| -------- | ------ | ---------- | ---------- | ------- | --- | --- |
| 7.6      | Neural | Network    |            | Control |     |     |
In the previous section, we have seen that simple nonlinearities can
be used very effectively in control systems. In this and the following
sections, we will discuss some techniques based on nonlinearities,
where the key idea is to use functions of several variables. It is
not easy to characterize such functions in a simple way. The ideas
described have been introduced under the names of neural and fuzzy
control. Atfirstsight thesemethods mayseem quite complicated, but
once we strip off the colorful language used, we will find that they
| are nothing | but | nonlinear | functions. |     |     |     |
| ----------- | --- | --------- | ---------- | --- | --- | --- |
u w
     1      1
w
u     2
|     |     |      2 |     |     | y   |     |
| --- | --- | ------ | --- | --- | --- | --- |
u w
n    n
|     | Figure | 7.20 | Schematicdiagram |     | ofa simple neuron. |     |
| --- | ------ | ---- | ---------------- | --- | ------------------ | --- |

| 296 | Chapter | 7   | Control Paradigms |     |     |     |     |
| --- | ------- | --- | ----------------- | --- | --- | --- | --- |
NeuralNetworks
Neural networks originated in attempts to make simple models for
neural activity in the brain and attempts to make devices that could
recognize patterns and carry out simple learning tasks. A brief de-
| scription  | that | captures | the essential |        | idea follows.   |     |          |
| ---------- | ---- | -------- | ------------- | ------ | --------------- | --- | -------- |
| A Simple   |      | Neuron   |               |        |                 |     |          |
| Aschematic |      | diagram  | ofasimple     | neuron | isshowninFigure |     | 7.20.The |
system has many inputs and one output. If the output is y and the
inputs are u , u , ... , u the input-output relation is described by
|     |     | 1 2 | n   |     |     |                   |     |
| --- | --- | --- | --- | --- | --- | ----------------- | --- |
|     |     |     |     |     |     | (cid:23) (cid:24) |     |
(cid:12)n
|     | y=  | f(w | +w +...+w |     | )=    |          | (7.10) |
| --- | --- | --- | --------- | --- | ----- | -------- | ------ |
|     |     | 1 u | 1 2 u 2   |     | n u n | f wu i i |        |
k=1
wherethenumbersw i arecalledweights.Thefunction f isaso-called
sigmoid function, illustrated in Figure 7.21. Such a function can be
| represented |     | as  |     |     |     |     |     |
| ----------- | --- | --- | --- | --- | --- | --- | --- |
αx−e −αx
e
|     |     |     | f(x) | =   |     |     | (7.11) |
| --- | --- | --- | ---- | --- | --- | --- | ------ |
eαx+e−αx
whereαisaparameter.
|     |     |     | This | model | ofaneuron | isthus | simply anon- |
| --- | --- | --- | ---- | ----- | --------- | ------ | ------------ |
linearfunction.Somespecialclassesoffunctionscanbeapproximated
(7.10).
by Equation
Neural Networks
More complicated models can be obtained by connecting neurons to-
getherasshowninFigure7.22.Thissystemiscalledaneuralnetwork
or a neural net. The adjective feedforward is often added to indicate
that the neurons are connected in a feedforward manner. There are
also other types of neural networks. In the feedforward network, the
input neurons are connected to a layer of neurons, the outputs of the
neurons in the first layer are connected to the neurons in the second
1
0
−1
|     |     | −4  | −2          |                   | 0   | 2   | 4   |
| --- | --- | --- | ----------- | ----------------- | --- | --- | --- |
|     |     |     | Figure 7.21 | Sigmoidfunctions. |     |     |     |

7.6 Neural Network Control 297
u
1
u
2
y
1
u
3
u
4
y
2
u
5
Figure 7.22 A feedforward neural network.
layer, etc., until we have the outputs. The intermediate layers in the
net are called hidden layers.
EachneuronisdescribedbyEquation(7.10).Theinput-output re-
lation of a neural net is thus a nonlinear static function. Conversely
wecanconsideraneuralnetasonewaytoconstructanonlinearfunc-
tion of several variables. The neural network representation implies
thatanonlinear function of several variables isconstructed from two
components: a single nonlinear function, the sigmoid function (7.11),
which is a scalar function of one variable; and linear operations. It is
thusasimplewaytoconstruct anonlinearity fromsimpleoperations.
Onereasonwhyneuralnetworksareinteresting isthatpracticallyall
continuous functions can be approximated by neural networks hav-
ing one hidden layer. It has been found practical to use more hidden
layers because then fewer weights can be used.
Learning
Noticethattherearemanyparameters(weights)inaneuralnetwork.
Assuming that there are n neurons in a layer, if all neurons are con-
nected, n2 parameters are then required to describe the connections
between twolayers. Another interesting property ofaneural network
is that there are so-called learning procedures. This is an algorithm
that makes it possible to find parameters (weights) so that the func-
tionmatchesgiven input-output values. Theparameters aretypically
obtained recursively by giving an input value to the function and the
desired output value. The weights are then adjusted so that the data
is matched. A new input-output pair is then given and the param-
eters are adjusted again. The procedure is repeated until a good fit
has been obtained for a reasonable data set. This procedure is called
training a network. Apopular method for training a feedforward net-

| 298 Chapter | 7 Control | Paradigms |     |     |
| ----------- | --------- | --------- | --- | --- |
work is called back propagation. For this reason the feedforward net
| is sometimes | called a back-propagation |     | network. |     |
| ------------ | ------------------------- | --- | -------- | --- |
| Control      | Applications              |     |          |     |
A feedforward neural network is nothing but a nonlinear function of
several variables with a training procedure. The function has many
parameters (weights) that can be adjusted by the training procedure
sothatthefunctionwillmatchgivendata.Evenifthisisanextremely
simplistic model of a real neuron, it is a very useful system compo-
nent. In process control we can often make good use of nonlinear
functions. Sensor calibration is one case. There are many situations
whereaninstrumenthasmanydifferentsensors,theoutputsofwhich
must be combined nonlinearly to obtain the desired measured value.
Nonlinear functions can also be used for pattern recognition.
| 7.7 Fuzzy | Control |     |     |     |
| --------- | ------- | --- | --- | --- |
Fuzzy control is an old control paradigm that has received a lot of
attention recently. In this section we will give a brief description of
the key ideas. We will start with fuzzy logic, which has inspired the
development.
FuzzyLogic
Ordinary Boolean logic deals with quantities that are either true or
false.Fuzzylogicisanattempttodevelopamethodforlogicreasoning
thatislesssharp. Thisisachieved byintroducing linguistic variables
and associating them with membership functions, which take values
between 0 and 1. In fuzzy control the logical operations and, or, and
not are operations on linguistic variables. These operations can be
expressed in terms of operations on the membership functions of
the linguistic variables. Consider two linguistic variables with the
membership functions f (x) and f (x). The logical operations are
A B
defined by the following operations on the membership functions.
|     | f     | =min(f    | (x), f (x)) |     |
| --- | ----- | --------- | ----------- | --- |
|     | A and | B A       | B           |     |
|     | f     | =max(f    | (x), f (x)) |     |
|     | A or  | B A       | B           |     |
|     | f     | =1− f (x) |             |     |
not A A
A linguistic variable, where the membership function is zero every-
where except for one particular value, is called a crisp variable.
| Assume | for example that | we want | to reason about | temperature. |
| ------ | ---------------- | ------- | --------------- | ------------ |
Forthis purpose weintroduce the linguistic variables cold, moderate,

|     |      |     |     |          |     | 7.7 Fuzzy | Control | 299 |
| --- | ---- | --- | --- | -------- | --- | --------- | ------- | --- |
| 1   | cold |     |     | moderate |     |           | hot     |     |
0.5
0
| −10 |     | 0   |     | 10  | 20  |     | 30  | 40  |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
1
| 0.5 |     | coldand | moderate |     |     |     |     |     |
| --- | --- | ------- | -------- | --- | --- | --- | --- | --- |
0
| −10 |     | 0      |          | 10  | 20  |     | 30  | 40  |
| --- | --- | ------ | -------- | --- | --- | --- | --- | --- |
| 1   |     | coldor | moderate |     |     |     |     |     |
0.5
0
| −10    |     | 0                                                  |     | 10  | 20  |     | 30  | 40  |
| ------ | --- | -------------------------------------------------- | --- | --- | --- | --- | --- | --- |
| Figure |     | 7.23 Illustrationoffuzzylogic.Theupperdiagramshows |     |     |     |     |     |     |
the membership functions of cold, moderate, and hot. The middle
| diagram |       | shows   | the membership |                | functions | for cold  | and moderate |     |
| ------- | ----- | ------- | -------------- | -------------- | --------- | --------- | ------------ | --- |
| the     | lower | diagram | shows          | the membership |           | functions | for cold     | or  |
moderate.
andhot,andweassociatethemwiththemembershipfunctionsshown
in Figure 7.23. The membership function for the linguistic variables
coldandmoderateandcoldormoderatearealsoshowninthefigure.
A FuzzyController
A block diagram of a fuzzy PD controller is shown in Figure 7.24.
The control error, which is a continuous signal, is fed to a linear
system that generates the derivative of the error. The error and its
derivativeareconvertedtoso-called“linguistic variables”inaprocess
called“fuzzification.” Thisprocedureconverts continuous variablesto
a collection of linguistic variables. The number of linguistic variables
is typically quite small, for example: negative large (NL), negative
|        | (NM), |          |     | (NS), |      | (Z),     |       | (PS), |
| ------ | ----- | -------- | --- | ----- | ---- | -------- | ----- | ----- |
| medium |       | negative |     | small | zero | positive | small |       |
positive medium (PM), and positive large (PL). The control strategy
is expressed in terms of a function that maps linguistic variables to
linguistic variables. This function is defined in terms of aset of rules
expressed in fuzzy logic. As an illustration wegive the rules for a PD
controller where the error and its derivative are each characterized
by three linguistic variables (N, Z, P) and the control variable is

| 300 Chapter | 7 Control | Paradigms |     |     |
| ----------- | --------- | --------- | --- | --- |
Linguistic
variables
de
 d t
e u
| Linear |     |     | Fuzzy  |     |
| ------ | --- | --- | ------ | --- |
e Fuzzyfier
| Filter  |     |     |     | Defuzzifier |
| ------- | --- | --- | --- | ----------- |
Logic
|     | Figure | 7.24 AfuzzyPD | controller. |     |
| --- | ------ | ------------- | ----------- | --- |
(NL, PL).
| characterized | by five linguistic | variables |           | NM, Z, PM, and |
| ------------- | ------------------ | --------- | --------- | -------------- |
| Rule 1:       | If e is N and      | de/dt     | is P then | u is Z         |
| Rule 2:       | If e is N and      | de/dt     | is Z then | u is NM        |
| Rule 3:       | If e is N and      | de/dt     | is N then | u is NL        |
| Rule 4:       | If e is Z and      | de/dt     | is P then | u is PM        |
| Rule 5:       | If e is Z and      | de/dt     | is Z then | u is Z         |
| Rule 6:       | If e is Z and      | de/dt     | is N then | u is NM        |
| Rule 7:       | If e is P and      | de/dt     | is P then | u is PL        |
| Rule 8:       | If e is P and      | de/dt     | is Z then | u is PM        |
| Rule 9:       | If e is P and      | de/dt     | is N then | u is Z         |
These rules can also be expressed in table form, see Table 7.1.
The membership functions representing the linguistic variables
normally overlap (see Figure 7.23). Due to this, several rules con-
tribute to the control signal. The linguistic variable representing the
control signal is calculated as a weighted sum of the linguistic vari-
ables of the control signal. The linguistic variable representing the
control signal is then mapped into a real number by an operation
called “defuzzification.” More details are given in the following.
Fuzzy Inference
Manydifferent shapes ofmembership functions canbeused. Infuzzy
controlitiscommonpracticetouseoverlappingtriangularshapeslike
the ones shown in Figure 7.23 for both inputs and control variables.
| Typicallyonlyafewmembership |     | functions | areusedforthemeasured |     |
| --------------------------- | --- | --------- | --------------------- | --- |
variables.
Fuzzy logic is only used to a moderate extent in fuzzy control. A
keyissue istointerprete logic expressions ofthetypethatappearsin
thedescription ofthefuzzycontroller. Somespecialmethodsareused
infuzzycontrol. Todescribe these weassume that f , f ,and f are
A B C
the membership functions associated with the linguistic variables A,
B, andC . Furthermore let x and y represent measurements. If the
values x and y are measured, they are considered as crisp values.
| 0   | 0   |     |     |     |
| --- | --- | --- | --- | --- |

|       |                    |     |        |         | 7.7        | Fuzzy Control 301 |
| ----- | ------------------ | --- | ------ | ------- | ---------- | ----------------- |
| Table | 7.1 Representation |     | of the | fuzzyPD | controller | asatable.         |
de
dt
|                     |           |        | P              | Z   | N     |     |
| ------------------- | --------- | ------ | -------------- | --- | ----- | --- |
|                     |           | N      | Z              | NM  | NL    |     |
|                     |           | e Z    | PM             | Z   | NM    |     |
|                     |           | P      | PL             | PM  | Z     |     |
| The fuzzy           | statement |        |                |     |       |     |
|                     |           | If x   | is A and       | y   | is B  |     |
| is then interpreted |           | as the | crisp variable |     |       |     |
|                     |           | z0 =   | min(f (x0),    |     | (y )) |     |
|                     |           |        | A              | f B | 0     |     |
whereandisequivalenttominimizationofthemembershipfunctions.
| The linguistic | variable | u defined | by      |        |     |      |
| -------------- | -------- | --------- | ------- | ------ | --- | ---- |
|                | If       | x is A    | or y is | B then | u   | is C |
is interpreted as a linguistic variable with the membership function
|     |     |     | f (x)= z0f | (x) |     |     |
| --- | --- | --- | ---------- | --- | --- | --- |
|     |     |     | u          | C   |     |     |
If there are several rules, as in the description of the PD controller,
eachruleisevaluated individually. Theresults obtained foreachrule
are combined using the or operator. This corresponds to taking the
maximum of the membership functions obtained for each individual
rule.
Figure 7.25 is a graphical illustration for the case of the first two
rulesofthePDcontroller.Thefigureshowshowthelinguisticvariable
corresponding to each rule is constructed and how the control signal
is obtained by taking the maximum of the membership functions
| obtained from | all | rules. |     |     |     |     |
| ------------- | --- | ------ | --- | --- | --- | --- |
The inference procedure described is called “product-max.” This
refers to the operations on the membership functions. Other infer-
ence procedures are also used in fuzzy control. The and operation
is sometimes represented by taking the product of two membership
functions and the or operator by taking a saturated sum. Combina-
tions of the schemes arealso used. Inthis wayit ispossible toobtain
| “product-max” | and | “min-sum” | inference. |     |     |     |
| ------------- | --- | --------- | ---------- | --- | --- | --- |
Defuzzification
Fuzzy inference results in a control variable expressed as a linguis-
tic variable and defined by its membership function. To apply a

| 302 Chapter | 7 Control Paradigms |     |     |     |
| ----------- | ------------------- | --- | --- | --- |
Rule 1:   If  e  is  N and  de/dt  is  P then  u  is  Z
| N   |     |     | P   | Z   |
| --- | --- | --- | --- | --- |
Rule 2:   If  e  is  N and  de/dt  is  Z  then  u  is  NM
| N   |     | Z   |     | NM  |
| --- | --- | --- | --- | --- |
e
de
dt
Figure 7.25 Illustration of fuzzy inference with two rules using
the min-maxrule.
control signal wemust have areal variable. Thus, thelinguistic vari-
able defining the control signal must be converted to a real number
throughtheoperation of“defuzzification.” Thiscanbedoneinseveral
different ways. Consider a linguistic variable Awiththemembership
(x).
| function f A | Defuzzification | by mean | values gives | the value |
| ------------ | --------------- | ------- | ------------ | --------- |
(cid:4)
xf (x)dx
= (cid:4) A
x 0
f (x)dx
A
Defuzzification by the centroid gives a real variable x that satisfies
0
|     | (cid:1) | (cid:1) |       |     |
| --- | ------- | ------- | ----- | --- |
|     | x0      |         | ∞     |     |
|     |         | (x)dx = | (x)dx |     |
|     | f       |         | f     |     |
|     | A       |         | A     |     |
|     | −∞      | x0      |       |     |
NonlinearControl
| Havinggonethroughthedetails, |     | wereturntothefuzzyPDcontroller |     |     |
| ---------------------------- | --- | ------------------------------ | --- | --- |
in Figure 7.24. We first notice that the operations fuzzification, fuzzy
logic,anddefuzzificationcanbedescribedinaverysimpleway.Strip-
pingawaythevocabularyandconsideringthefinalresult,afuzzycon-
trollerisnothingbutanonlinearcontroller.ThesysteminFigure7.24

|     |     |     | 7.7 Fuzzy | Control 303 |
| --- | --- | --- | --------- | ----------- |
1
0.5
u 0
−0.5
−1
1
|     | 0.5 |     |     | 1   |
| --- | --- | --- | --- | --- |
|     |     | 0   | 0.5 |     |
0
|     | de/dt | −0.5 |     |     |
| --- | ----- | ---- | --- | --- |
−0.5 e
−1 −1
Figure 7.26 Graphic illustration of the nonlinearity of the fuzzy
controller showing control signal u as function of control error e
and itsderivative.
| can in | fact be expressed | as      |         |     |
| ------ | ----------------- | ------- | ------- | --- |
|        |                   | (cid:5) | (cid:6) |     |
de
u=
|     |     | F e, |     |     |
| --- | --- | ---- | --- | --- |
dt
where F is a nonlinear function of two variables. Thus, the fuzzy
PDcontroller isacontroller where the output is anonlinear function
de/dt!
| of the | error e and its | derivative | In Figure 7.26 | we give a |
| ------ | --------------- | ---------- | -------------- | --------- |
graphic illustration of the nonlinearity defined by given rules for the
PD controller with standard triangular membership functions and
product fuzzification. The figure shows that the function is close to
linear.Inthisparticularcasethefuzzycontrollerwillbehavesimilarly
| to an ordinary | linear | PD controller. |     |     |
| -------------- | ------ | -------------- | --- | --- |
Fuzzycontrolmaybeconsideredasawaytorepresentanonlinear
function. Notice that it is still necessary to deal with generation of
derivatives or integrals, integral windup, and all the other matters
| inthesame                                      | wayasforordinary | PIDcontrollers. | Wemayalso    | inquire |
| ---------------------------------------------- | ---------------- | --------------- | ------------ | ------- |
| astowhenitisusefultointroducethenonlinearities |                  |                 | andwhatshape |         |
| they should                                    | have.            |                 |              |         |
Representation ofanonlinearity byfuzzification, fuzzylogic, and
defuzzificationisnotverydifferentfromrepresentationofanonlinear
function as a table with an interpolation procedure. Roughly speak-
ing,thefunctionvaluescorrespondtotherules;themembershipfunc-
tions and the fuzzification and defuzzification procedures correspond
totheinterpolation mechanism. Toillustrate thisweconsider afunc-
tion of two variables. Such a function can be visualized as a surface
in two dimensions. A linear function is simply a tilted plane. This

304 Chapter 7 Control Paradigms
function can be described completely by three points on a plane, i.e.,
threerules.Morecomplexsurfacesorfunctions areobtained byusing
more function values. The smoothness of the surface is expressed by
the interpolation procedures.
Fromthepoint ofview ofcontrol, thekeyquestion isunderstand-
ing when nonlinearities areuseful and whatshape they should have.
These are matters where much research remains to be done. There
are cases where the nonlinearities can be very beneficial but also
cases where the nonlinearities cause problems. It is also a nontrivial
task to explore what happens. A few simulations of the behavior is
not enough because the response of a nonlinear system is strongly
amplitude dependent.
Let us also point out that the properties of the controller in
Figure 7.24 are strongly influenced by the linear filter used. It is
thus necessary to limit the high-frequency gain of the approximation
of the derivative. It is also useful to take derivatives of the process
output instead of the error, as was discussed in Section 3.4. Other
filters can also be used; by adding an integrator to the output of the
system in Figure 7.24, we obtain a fuzzy PI controller.
Applications
The representation of the control law as a collection of rules for lin-
guistic variables has a strong intuitive appeal. It is easy to explain
heuristically how the control system works. This is useful in commu-
nicating control strategies to persons with little formal training. It is
one reason why fuzzy control is a good tool for automation of tasks
thatarenormallydonebyhumans.Inthisapproachitisattemptedto
model the behavior of an operator in terms of linguistic rules. Fuzzy
control has been used in a number of simple control tasks for ap-
pliances. It has also been used in controllers for processes that are
complicated and poorly known. Control of a cement kiln is one exam-
ple of this type of application. Fuzzy control has also been used for
controller tuning.
7.8 Interacting Loops
An advantage to building a complex system from simple components
by using a few control principles is that complexity is reduced by de-
composition. In normal cases it is also comparatively easy to extrap-
olate the experience of commissioning and tuning single-loop control.
It is also appealing to build up a complex system by gradual refine-
ment. There are, however, also some drawbacks with the approach:

|     |     |     |     | 7.8 | Interacting | Loops | 305 |
| --- | --- | --- | --- | --- | ----------- | ----- | --- |
• Since we have not determined the fundamental limitations, it
is difficult to decide when further refinements do not give any
| significant | benefits. |     |     |     |     |     |     |
| ----------- | --------- | --- | --- | --- | --- | --- | --- |
• It is easy to get systems that are unnecessarily complicated. We
may get systems where several control loops are fighting each
other.
• There are cases where it is difficult to arrive at a good overall
| system | by a | loop-by-loop | approach. |     |     |     |     |
| ------ | ---- | ------------ | --------- | --- | --- | --- | --- |
If there are difficulties, it is necessary to use a systematic approach
based on mathematical modeling analysis and simulation. This is,
however,moredemandingthantheempiricalapproach.Inthissection
| we illustrate | some | of  | the difficulties | that | may arise. |     |     |
| ------------- | ---- | --- | ---------------- | ---- | ---------- | --- | --- |
ParallelSystems
Systems that are connected in parallel are quite common. Typical
examples are motors that are driving the same load, power systems
and networks for steam distribution. Control of such systems require
special consideration. To illustrate the difficulties that may arise we
will consider the situation with two motors driving the same load. A
| schematic | diagram | of  | the system | is shown | in Figure | 7.27. |     |
| --------- | ------- | --- | ---------- | -------- | --------- | ----- | --- |
Let ωbe the angular velocity of the shaft, J the total moment
of inertia, and D the damping coefficient. The system can then be
| described | by the | equation |     |     |     |     |     |
| --------- | ------ | -------- | --- | --- | --- | --- | --- |
dω
|         |       | J                             | + Dω= | M +M | −M  |             | (7.12) |
| ------- | ----- | ----------------------------- | ----- | ---- | --- | ----------- | ------ |
|         |       |                               | dt    | 1    | 2 L |             |        |
| where M | and M | arethetorquesfromthemotorsand |       |      |     | M istheload |        |
| 1       |       | 2                             |       |      |     | L           |        |
torque.
Gearbox
A
|     |     |    C   1 |       |     |     |     |     |
| --- | --- | -------- | ----- | --- | --- | --- | --- |
1
ω
w
   sp
|     |     | C   |    A   2 |     |     |     |     |
| --- | --- | --- | -------- | --- | --- | --- | --- |
     2
| Figure7.27 |     | Schematicdiagramoftwomotorsthatdrivethesame |     |     |     |     |     |
| ---------- | --- | ------------------------------------------- | --- | --- | --- | --- | --- |
load.

306 Chapter 7 Control Paradigms
Proportional Control
Assume each motor is provided with a proportional controller. The
control strategies are then
M = M + K (ω −ω)
1 10 1 sp (7.13)
M = M + K (ω −ω)
2 20 2 sp
Inthese equations theparameters M and M give the torques pro-
10 20
vided by each motor whenω=ω and K and K are the controller
sp 1 2
gains. It follows from Equations (7.12) and (7.13) that
dω
J +(D+ K + K )ω= M +M −M +(K + K )ω
1 2 10 20 L 1 2 sp
dt
The closed-loop system is, thus, a dynamical system of first order.
Afterperturbations theangular velocity reachesitssteady statewith
a time constant
J
T =
D+K + K
1 2
The response speed is thus given by the sum of the damping and the
controller gains. The stationary value of the angular velocity is given
by
K + K M +M −M
ω=ω = 1 2 ω + 10 20 L
0 D+K + K sp D+ K + K
1 2 1 2
Thisimpliesthattherenormallywillbeasteadystateerror.Similarly
we find from Equation (7.13) that
M −M K
1 10 = 1
M −M K
2 20 2
The ratio of the controller gains will indicate how the load is shared
between the motors.
Proportional and Integral Control
The standard way to eliminate a steady state error is to introduce
integral action. In Figure 7.28 we show a simulation of the system
in which the motors have identical PI controllers. The setpoint is
changed at time 0. A load disturbance in the form of a step in the
load torque is introduced at time 10 and a pulse-like measurement
disturbance in the second motor controller is introduced at time 20.
When the measurement error occurs the balance of the torques is
changed so that the first motor takes up much more of the load after
the disturbance. In this particular case the second motor is actually
breaking. This is highly undesirable, of course.
To understand the phenomena we show the block diagram of the
system in Figure 7.29. The figure shows that there are two parallel

7.8 Interacting Loops 307
ω
sp
1
0.5 ω
0
0 10 20 30
M
1
0.4
M
2
0
0 10 20 30
n
0
M
L
−1
0 10 20 30
Figure 7.28 Simulation of a system with two motors with PI
controllersthatdrivethesameload.Thefigureshowssetpointω ,
sp
processoutputω,controlsignals M and M ,loaddisturbance M ,
1 2 L
and measurement disturbance n.
paths in the system that contain integration. This is a standard case
where observability and controllability is lost. Expressed differently,
it is not possible to change the signals M and M individually from
1 2
the error. Since the uncontrollable state is an integrator, it does not
gotozeroafter disturbance. Thismeansthatthe torquescantakeon
arbitrary values after disturbance. For example, it may happen that
oneofthemotorstakespracticallyalltheload,clearlyanundesirable
situation.
M
1
PI Motor 1
ω
sp Σ M s 1 ω
s
PI Motor 2
M
2
Figure 7.29 Block diagram for the systemin Figure 7.28.

308 Chapter 7 Control Paradigms
M
10
α Σ
Motor 1
ω
sp ω
Σ 1
PI s
1 −α Motor 2 Σ
M
20
Figure 7.30 Block diagram of animproved controlsystem.
How to Avoid the Difficulties
Having understood the reason for the difficulty, it is easy to modify
thecontroller asshowninFigure7.30.Inthiscaseonlyonecontroller
with integral action is used. The output of this drives proportional
controllers for each motor. A simulation of such a system is shown in
Figure 7.31. The difficulties are clearly eliminated.
The difficulties shown in the examples with two motors driving
the same load are even more accentuated if there are more motors.
ω
sp
1
0.5 ω
0
0 10 20 30
M
1
0.4 M
2
0
0 10 20 30
n
0
M
L
−1
0 10 20 30
Figure 7.31 Simulation of the system with the modified con-
troller. The figure shows setpoint ω , process output ω, control
sp
signals M and M ,loaddisturbance M ,andmeasurementdistur-
1 2 L
bance n.

7.8 Interacting Loops 309
Good control in this case can be obtained by using one PI controller
and distributing the outputs of this PI controller to the different mo-
tors, each of which has a proportional controller. An alternative is to
provide one motor with a PI controller and let the other have propor-
tional control. To summarize, we have found that there may be diffi-
culties with parallel systems having integral action. The difficulties
are caused by the parallel connection of integrators that produce un-
stable subsystems that are neither controllable nor observable. With
disturbances these modes can change in an arbitrary manner. The
remedy is to change the control strategies so there is only one inte-
grator.
InteractionofSimpleLoops
Thereareprocesses thathave manycontrol variables andmanymea-
sured variables. Such systems are called multi-input multi-output
(MIMO) systems. Because of the interaction between the signals, it
may be very difficult to control such systems by a combination of
simple controllers. A reasonably complete treatment of this problem
is far outside the scope of this book. Let it suffice to illustrate some
difficulties that may arise by considering processes with two inputs
and two outputs. A block diagram of such a system is shown in Fig-
ure 7.32. A simple approach to control such a system is to use two
single-loop controllers, one for each loop. To do this we must first de-
cide how the controllers should be connected, i.e., if y in the figure
1
should be controlled by u or u . This is called the pairing problem.
1 2
This problem is straightforward if there is little interaction among
the loops, which can be determined from the responses of all outputs
toallinputs(seee.g.Figure7.33).Thesingle-loop approachwillwork
well if there is small coupling between the loops. The loops can then
be tuned separately. There may be difficulties, however, when there
is coupling between the loops (as shown in the following example).
u
y sp1 C 1 1 y 1
Process
y u
sp2 C
2
2 y
2
Figure 7.32 Block diagram of a system with two inputs and two
outputs.

310 Chapter 7 Control Paradigms
EXAMPLE 7.8 Rosenbrock’s system
Consider a system with two inputs and two outputs. Sych a system
can be characterized by giving the transfer functions that relate all
inputs and outputs. These transfer functions can be organized as the
matrix    
G(s)=
 (cid:3)
11
(s) (cid:3)
12
(s)= s+ 1
1 s+
2
3

(cid:3) (s) (cid:3) (s) 1 1
21 22 s+1 s+1
The first index refers to the outputs and the second to the inputs.
In the matrix above, the transfer function (cid:3) denotes the transfer
12
function from the second input to the first output.
The behavior of the system can be illustrated by plotting the
step responses from all inputs, as shown in Figure 7.33. From this
figure we can see that there are significant interactions between
the signals. The dynamics of all responses do, however, appear quite
benign.Inthiscaseitisnotobvioushowthesignalsshouldbepaired.
Arbitrarily, we use the pattern 1-1, 2-2. It is very easy to design
a controller for the individual loops if there is no interaction. The
transfer function of the process is
1
G(s)=
s+1
in both cases. With PI control it is possible to obtain arbitrarily high
gains, if there are no constraints on measurement noise or process
uncertainty. A reasonable choice is to have K = 19, b = 0, and
T = 0.19. This gives a system with relative damping ζ = 0.7 and
i
an undamped natural frequency of 10 rad/s. The responses obtained
with this controller in one loop and the other loop open are shown in
0.5 0.5
y
1
y
1
0 0
0 2 4 6 8 0 2 4 6 8
0.5 0.5 y
y 2
2
0 0
0 2 4 6 8 0 2 4 6 8
Figure 7.33 Open-loop step responses of the system. The left
diagrams show responses to a step change in control signal u ,
1
andtherightdiagramsshowresponsestoastepchangeincontrol
signal u .
2

|     |     |     |     | 7.8 Interacting | Loops | 311 |
| --- | --- | --- | --- | --------------- | ----- | --- |
| 1   |     |     |     | 1               |       |     |
| 0.5 |     |     |     | 0.5 y           |       |     |
| y   | 1   |     |     | 1               |       |     |
| 0   |     |     |     | 0               |       |     |
| 0   | 1   | 2   | 3   | 0 1             | 2     | 3   |
| 1   |     |     |     | 1               |       |     |
| 0.5 |     |     |     | 0.5             |       |     |
| y   | 2   |     |     | y 2             |       |     |
| 0   |     |     |     | 0               |       |     |
| 0   | 1   | 2   | 3   | 0 1             | 2     | 3   |
Figure 7.34 Step responses with one loop closed and the other
open. The left diagrams show responses to steps in u when con-
1
troller C is disconnected, and the right diagrams show responses
2
| to stepsin | u   | when controller | C   | isdisconnected. |     |     |
| ---------- | --- | --------------- | --- | --------------- | --- | --- |
|            |     | 2               | 1   |                 |     |     |
Figure 7.34. Notice that the desired responses are as expected, but
thattherealsoarestrongresponses intheother signals. Ifbothloops
are closed with the controllers obtained, the system will be unstable.
In order to have reasonable responses with both loops closed,
it is necessary to detune the loops significantly. In Figure 7.35 we
show responses obtained when the controller in the first loop has
|            |     | =     | =         |                      |     | =   |
| ---------- | --- | ----- | --------- | -------------------- | --- | --- |
| parameters | K   | 2 and | T 0.5 and | the other controller | has | K   |
i
0.8 and T = 0.7. The gains are more than an order of magnitude
i
smaller than the ones obtained with one loop open. A comparison
with Figure 7.34 shows that the responses are significantly slower.
Theexampleclearly demonstrates the deficiencies inloop-by loop
| 1     |     |     |     | 1     |        |     |
| ----- | --- | --- | --- | ----- | ------ | --- |
| 0.5 y |     |     |     | 0.5 y |        |     |
|       | 1   |     |     | 2     |        |     |
| 0     |     |     |     | 0     |        |     |
| 0 2   | 4   | 6 8 | 10  | 0 2 4 | 6 8 10 |     |
0.2
1
u
2
u
1
0
0
| 0 2 | 4   | 6 8 | 10  | 0 2 4 | 6 8 10 |     |
| --- | --- | --- | --- | ----- | ------ | --- |
Figure 7.35 Stepresponses when both loops are closed. The fig-
ureshowsresponsestosimultaneoussetpointchangesinbothloops.

| 312 Chapter | 7 Control | Paradigms |     |
| ----------- | --------- | --------- | --- |
tuning. The example chosen is admittedly somewhat extreme but it
clearlyindicatesthatitisnecessarytohaveothertechniquesfortruly
multivariable systems. The reason for the difficulty is that the seem-
inglyinnocentsystemisactuallyanon-minimumphasemultivariable
| system with | a zero at s=−1. |     |     |
| ----------- | --------------- | --- | --- |
InteractionMeasures
The example given clearly indicates the need to have some way to
find out if interactions may cause difficulties. There are no simple
universal methods. Anindication canbeobtained bytherelative gain
(RGA).
array This can be computed from the static gains in all loops
in a multivariable system. For the a 2 (cid:14) 2 system like the one in
| Example 7.8 | the RGA is |     |     |
| ----------- | ---------- | --- | --- |
|             |            |   |     |
λ 1−λ

R=
1−λ λ
where
(cid:3) (0)(cid:3) (0)
|     | λ=      | 11 22                                 |     |
| --- | ------- | ------------------------------------- | --- |
|     | (cid:3) | (0)(cid:3) (0)−(cid:3) (0)(cid:3) (0) |     |
|     |         | 11 22 12 21                           |     |
Thenumberλhasphysicalinterpretationastheratioofthegainfrom
u to y with the second loop open and with the second loop under
1 1
|            | (y =0).There |                   | λ=1. Ifλ=0 |
| ---------- | ------------ | ----------------- | ---------- |
| very tight | feedback     | is no interaction | if         |
2
thereisalsonointeraction, buttheloopsshouldbeinterchanged.The
λ<
loops should be interchanged when 0.5. The interaction is most
λ=0.5.
severe if
For a multivariable system the relative gain is a matrix R in
| which component | r ij is given | by  |     |
| --------------- | ------------- | --- | --- |
r =(cid:3) h
ij ij ji
where (cid:3) is ij-th element of the static gain matrix G of the process
ij
| and h is | the ij-th element | of the the matrix |     |
| -------- | ----------------- | ----------------- | --- |
ij
H = G −1
Notice that (cid:3) is the static gain from input j to output i.
ij
Bristol’s recommendation for controller pairing is that the mea-
suredvalues andcontrol variables should bepairedsothatthecorre-
sponding relative gains are positive, and as close to one as possible.
If the gains are outside the interval 0.67 < λ< 1.5, decoupling can
improve the control significantly. Since the relative gain is based on
the static properties of the system, it does not capture all aspects of
the interaction.

7.9 SystemStructuring 313
7.9 System Structuring
Inthissection weillustrate how complexcontrol systems canbebuilt
from simple components by using the paradigms we have discussed.
The problem is quite complex. It involves selection of measured vari-
ables and control variables, and it requires significant physical un-
derstanding of the process.
TheProcess
The process to consider is a chemical reactor. A schematic diagram
is shown in Figure 7.36. Two substances A and B are mixed in the
reactor. They react to form a product. The reaction is exothermic,
whichmeansthatitwillgenerateheat.Theheatisdissipatedthrough
water that is circulating in cooling pipes in the reactor. The reaction
isvery fast;equilibrium isachieved after atime thatismuch shorter
than the residence time of the reactor. The flow q of substance A is
A
considerably larger than q . Efficiency of the reaction and the heat
B
generation is essentially proportional to the flow q .
B
Astaticprocessmodelisusefulinordertounderstandthecontrol
problem.Figure7.37showstheefficiencyandtheheatgenerationasa
function of temperature. In the figure we have drawn a straight line
that corresponds to the cooling power. There are equilibria where
the power generated by the reaction is equal to the cooling power
represented atpoints P and Q inthefigure. Thepoint P corresponds
Cool
water
V L
1
T
r
T
v
V
2 Cooling
Steam pipes
V V
3 5
q
A
V
q 4
B
Figure 7.36 Schematicdiagram of achemicalreactor.

314 Chapter 7 Control Paradigms
Power
Q
P
T Temperature
c
Figure 7.37 Staticprocess model for the exothermicreactor.
to an unstable equilibrium. It follows from Figure 7.37 that if the
temperatureisincreasedabovePthepowergeneratedbythereaction
islarger thanthe cooling power. Temperature will thus increase. The
catalyst in the reactor may be damaged if the temperature becomes
too high. Similarly if the temperature decreases below point P it will
continuetodecreaseandthereactionstops.Thisphenomena iscalled
“freezing.” Freezing starts at the surface of the cooling tube and will
spread rapidly through the reactor. If this happens the reactor must
be switched off and restarted again.
DesignRequirements
There are considerable risks in running an exothermic reactor. The
reactor canexplode if the temperature is too high. To reduce the risk
of explosion, the reactors are placed in special buildings far away
from the operator. Because of the risk of explosion, it is not feasible
to experiment with controller tuning. Consequently, it is necessary
to compute controller setting beforehand and verify that the settings
are correct before starting the reactor. Safety is the overriding re-
quirement of the control system. It is important to guarantee that
the reaction temperature will not be too high. It is also important
to make sure that process upsets do not lead to loss of coolant flow,
and that stirring does not lead to an explosion. It is also desirable
to operate the reactor efficiently. This means that freezing must be
avoided. Besides it is desirable to keep the efficiency as high as pos-
sible. Because of the risks, it is also necessary to automate start and
stopaswellasnormaloperation. Itisdesirabletoavoidhavingtorun
thereactorundermanualcontrol.Inthisparticularcasetheoperator
can set two variables, the reactor temperature and the ratio between
the flows q and q . The reaction efficiency and the product quality
A B
can be influenced by these two variables.

7.9 SystemStructuring 315
ControllerStructure
The reactor has five valves. Two of them, V and V , influence the
1 2
coolant temperature. The flow of the reactor is controlled by V and
3
V ,andtheproductflowiscontrolled bythevalve V .Inthisparticu-
4 5
larapplicationthevalveV iscontrolledbyprocessstepsdownstream.
5
(Compare this with the discussion of surge tanks in Section 7.5.)
There are five measured signals: the reactor temperature T , the
r
level inthe reactortank L, thecooling temperature T ,and theflows
v
q and q . The physical properties of the process gives a natural
A B
structuring of the control system. A mass balance for the material
in the reactor tank shows that the level is essentially influenced by
the flow q and the demanded production. It follows from the sto-
A
chiometry ofthereaction thattheratio of theflows q and q should
A B
be kept constant for an efficient reaction. The reactor temperature
is strongly influenced by the water temperature, by the temperature
of the coolant flow and the flows q and q . Coolant temperature is
A B
influenced by the valve V that controls the amount of flow and by
1
the steam valve V .
2
This simple physical discussion leads to the diagram shown in
Figure7.38,whichshowsthecausalityofthevariablesintheprocess.
The valve V can be regarded as a disturbance because it is set by
5
downstream process units. Figure 7.38 suggests that there are three
natural control loops:
V
5
L
V
3
V
1
T v T r
V
2
q
B
V
4 q
A
Figure 7.38 Causality diagram for the process variable.

| 316 Chapter | 7 Control Paradigms |     |     |     |
| ----------- | ------------------- | --- | --- | --- |
T
v
M
I
T
|   r |     |     | N   |     |
| --- | --- | --- | --- | --- |
L
  sp
V
|     | P   |     |     |      3 |
| --- | --- | --- | --- | ------ |
L
M
|     | L   | A   |     |     |
| --- | --- | --- | --- | --- |
X
Π
T
  v
| Figure | 7.39 Blockdiagramforthelevelcontrolthroughvalve |     |     | V . |
| ------ | ----------------------------------------------- | --- | --- | --- |
3
| 1. Level | control: Controlling | the tank level | with valve | V . |
| -------- | -------------------- | -------------- | ---------- | --- |
3
2. Temperature control: Control of the reactor temperature with
| valves | V 1 and V 2 . |     |     |     |
| ------ | ------------- | --- | --- | --- |
/q
3. Flow ratio control: Control of ratio q B A with valve V 4 .
| These control | loops are discussed | in detail. |     |     |
| ------------- | ------------------- | ---------- | --- | --- |
LevelControl
The block diagram for the level control is shown in Figure 7.39. The
primaryfunction isaproportional feedback fromthelevel totheflow
q , which is controlled by the valve V . The reactor is also used as
| A   |     | 3   |     |     |
| --- | --- | --- | --- | --- |
a surge tank to smooth out the difference between actual production
and commanded production. The level in the tank will vary during
normal operations. Reasonable limits arethat the level should be be-
tween 50% and 100%. If the proportional band of the controller is
| chosenas50%,thecontrolvariablewillbefullyclosed |     |     |     | whenthetank |
| ----------------------------------------------- | --- | --- | --- | ----------- |
is full and half-open when the tank is half-full. It is important that
the reactor temperature remains within given bounds. The flow q A
is constrained, therefore, by two selectors based on measurements of
the temperature in the reactor tank (T ) and the coolant tempera-
r
(T ).
ture When starting the reactor the level is kept at the lower
v
limit until the coolant temperature becomes sufficiently high. This

|     |     |     |     | 7.9 | SystemStructuring | 317 |
| --- | --- | --- | --- | --- | ----------------- | --- |
is achieved by combination of limiters, multipliers, and selectors, as
| shown in Figure | 7.39. |     |     |     |     |     |
| --------------- | ----- | --- | --- | --- | --- | --- |
TemperatureControl
Figure7.40gives ablockdiagramforcontrolling thereactortempera-
ture.Sincethechemicalreactionisfastcomparedtotemperatureand
flow dynamics, the reactor can be viewed as a heat exchanger from
the control point of view. During normal conditions the temperature
is controlled by adjusting the coolant flow through the valve V . The
1
primarycontrolfunctionisafeedbackfromtemperaturetothevalves
V and V . The setpoint in this control loop can be adjusted manu-
| 1 2 |     |     |     |     |     |     |
| --- | --- | --- | --- | --- | --- | --- |
ally.Theparametersofthiscontrolloopcanbedetermined asfollows.
The transfer function from coolant flow to the reactor temperature is
| approximately | given | by  |     |     |     |     |
| ------------- | ----- | --- | --- | --- | --- | --- |
K
|     |     | G(s)= |       | p      |     | (7.14) |
| --- | --- | ----- | ----- | ------ | --- | ------ |
|     |     |       | (1+sT | )(1+sT | )   |        |
|     |     |       |       | 1      | 2   |        |
where the time constant typically has values T = 300 s and T =
|     |     |     |     |     | 1   | 2   |
| --- | --- | --- | --- | --- | --- | --- |
50 s. The following rough calculation gives approximate values of the
controller parameter. Aproportional controller with gain K gives the
| loop transfer | function |     |     |     |     |     |
| ------------- | -------- | --- | --- | --- | --- | --- |
KK
|     |     | (s)= |     | p   |     | (7.15) |
| --- | --- | ---- | --- | --- | --- | ------ |
G 0
|                    |          |         | (1+sT   | )(1+sT      | )       |     |
| ------------------ | -------- | ------- | ------- | ----------- | ------- | --- |
|                    |          |         |         | 1           | 2       |     |
| The characteristic | equation |         | of the  | closed loop | becomes |     |
|                    |          | (cid:5) | (cid:6) |             |         |     |
|                    |          | 1       | 1       | 1+          | KK      |     |
|                    | s2+s     |         | +       | +           | p =0    |     |
|                    |          | T       | T       | T           | T       |     |
|                    |          |         | 1 2     | 1           | 2       |     |
q
|   A |     | FF  |     |     |     |     |
| --- | --- | --- | --- | --- | --- | --- |
3-9
V
    1
T
  sp
Σ
| T   | PID |     |     |     |     |     |
| --- | --- | --- | --- | --- | --- | --- |
r
M
|     |     |     |     | A   | V   |     |
| --- | --- | --- | --- | --- | --- | --- |
  2
|     |     |     |     | X   | 9-15 |     |
| --- | --- | --- | --- | --- | ---- | --- |
T
  v
| Figure 7.40  | Blockdiagramshowingtemperaturecontrolthrough |     |     |     |     |     |
| ------------ | -------------------------------------------- | --- | --- | --- | --- | --- |
| valves V and | V                                            | .   |     |     |     |     |
1 2

| 318 | Chapter | 7 Control | Paradigms |     |     |     |     |     |
| --- | ------- | --------- | --------- | --- | --- | --- | --- | --- |
The closed system is thus of second order. The relative damping ζ
ωare
| and the | the undamped |     | natural | frequency |         | given | by  |        |
| ------- | ------------ | --- | ------- | --------- | ------- | ----- | --- | ------ |
|         |              |     |         | 1         | 1       | 1     |     |        |
|         |              |     | 2ζω=    | +         | (cid:9) |       |     | (7.16) |
|         |              |     |         | T         | T       | T     |     |        |
|         |              |     |         | 1         | 2       | 2     |     |        |
and
1+
KK
|     |     |     | 2ζω2 | =   |         | p   |     | (7.17) |
| --- | --- | --- | ---- | --- | ------- | --- | --- | ------ |
|     |     |     |      |     | T 1 T 2 |     |     |        |
≫
The approximation in the first expression is motivated by T 1 T 2 .
|        |          |         |     | ζ = |              | (7.16) |      |       |
| ------ | -------- | ------- | --- | --- | ------------ | ------ | ---- | ----- |
| With a | relative | damping |     | 0.5 | the Equation |        | then | gives |
ω(cid:9)1/T . Furthermore it follows from Equation (7.17) that
2
T 300
|     |     |     | 1+ KK | = 1 | =   | =6  |     |     |
| --- | --- | --- | ----- | --- | --- | --- | --- | --- |
p
|     |     |     |     | T 2 | 50  |     |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
The loop gain is thus essentially determined by the ratio of the time
| constants. | The | controller | gain | becomes |     |     |     |     |
| ---------- | --- | ---------- | ---- | ------- | --- | --- | --- | --- |
5
|     |     |     |     | K = |     |     |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
K p
and the closed-loop system has the undamped natural frequency.
|     |     |     | ω=1/T | =0.02 | rad/s |     |     |     |
| --- | --- | --- | ----- | ----- | ----- | --- | --- | --- |
2
If PI control is chosen instead, it is reasonable to choose a value of
| the integration |     | time. |     |     |     |     |     |     |
| --------------- | --- | ----- | --- | --- | --- | --- | --- | --- |
(cid:9)5T
|     |     |     |     | T 1 | 2   |     |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
Control can be improved by using derivative action. The achievable
improvementdependsonthetimeconstantofthetemperaturesensor.
In typical cases this time constant is between 10 s and 40 s. If it is
as low as 10 s it is indeed possible to obtain improved control by
introducing a derivative action in the controller. The derivative time
can be chosen to eliminate the time constant T . We then obtain a
2
system with the time constants 300 s and 10 s. The gain can then be
| increased | so  | that |     |     |     |     |     |     |
| --------- | --- | ---- | --- | --- | --- | --- | --- | --- |
300
|     |     |     | 1+  | =   | =30 |     |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
KK p
10
and the undamped natural frequency of the system then becomes
ω (cid:9) 0.1 rad/s. If the time constant of the temperature sensor is
around 40s,the derivative action gives only marginalimprovements.
The heat generated by the chemical reaction is proportional to
the flow q . To make sure that variations in q are compensated
|     | A   |     |     |     |     | A   |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
rapidly wehave also introduced a feedforward from the flow q A . This
feedforward will only operate when the tank level is larger than 50%
| in order | to avoid | freezing     | when | the         | reactor | is started. |     |          |
| -------- | -------- | ------------ | ---- | ----------- | ------- | ----------- | --- | -------- |
| To       | start    | the reaction |      | the reactor | must    | be heated   | so  | that the |
temperature in the reaction vessel is larger than T (compare with
c

|     |     |     |     | 7.9 | SystemStructuring | 319 |
| --- | --- | --- | --- | --- | ----------------- | --- |
Figure 7.37). This is done by using the steam valve V . Split range
2
|                                  |           |               |       |                          | (compare | 7.5).   |
| -------------------------------- | --------- | ------------- | ----- | ------------------------ | -------- | ------- |
| control                          | is used   | for the steam | and   | water valves             |          | Section |
| Thewatervalveisopenforlowsignals |           |               |       | (3–9PSI)andthesteamvalve |          |         |
| is open                          | for large | pressures     | (9–15 | PSI).                    |          |         |
To avoid having the reactor freez, it is necessary to make sure
that the reaction temperature is always larger than T . This is the
c
reason for the extra feedback from water temperature to T v through
a maximum selector. This feedback makes sure that the steam valve
opensifthetemperatureinthecoolantflowbecomestoolow.Cascade
| control | would | be an alternative |     | to this arrangement. |     |     |
| ------- | ----- | ----------------- | --- | -------------------- | --- | --- |
FlowRatioControl
The ratio of the flows q and q must be kept constant. Figure 7.41
|     |     |     | A   | B   |     |     |
| --- | --- | --- | --- | --- | --- | --- |
shows how the efficiency of the reaction depends on q when q is
B A
| keptconstant.Theflowq |     |     | iscontrolledwitharatiocontrolsystem(as |     |     |     |
| --------------------- | --- | --- | -------------------------------------- | --- | --- | --- |
B
7.42),which
| shown | in Figure |     | is  | the primary | control | function. The re- |
| ----- | --------- | --- | --- | ----------- | ------- | ----------------- |
action ratedepends strongly on q .Todiminish therisk of explosion,
B
there is a nonlinearity in the feedback that increases the gain when
/q
q is large. The flow loop has several selectors. At startup it is
B A
desirable that substance B is not added until the water temperature
has reached the critical value T c and the reactor tank is half-full.
To achieve this the feedback from the water temperature and tank
level have been introduced through limiters and a minimum selector.
There are also limiters and a selector that closes valve V rapidly if
4
flow q is lost. There is also a direct feedback from q through lim-
| A   |     |     |     |     |     | A   |
| --- | --- | --- | --- | --- | --- | --- |
iters and selectors and a feedback from the reactor temperature that
closes valve V , if the reactor temperature becomes too high.
4
Yield
q
B
| Figure | 7.41 | Reaction | yieldas | afunctionof | q at | constant q . |
| ------ | ---- | -------- | ------- | ----------- | ---- | ------------ |
|        |      |          |         |             | B    | A            |

| 320 Chapter | 7 Control | Paradigms |     |     |     |
| ----------- | --------- | --------- | --- | --- | --- |
T
v
L
| q   |                |     |     | M   |     |
| --- | -------------- | --- | --- | --- | --- |
| B   |                |     | SP  |     |     |
|     | R a t i o      |     |     | I   | V   |
| q   |                |     | PI  |     | 4   |
| A   | co n t r oller |     | M V | N   |     |
q
A
T
r
/q
| Figure | 7.42 Blockdiagramforcontrollingthemixingratioq |     |     |     |     |
| ------ | ---------------------------------------------- | --- | --- | --- | --- |
B A
| throughvalve | V . |     |     |     |     |
| ------------ | --- | --- | --- | --- | --- |
4
| OverrideControlof | theOutletValve |     |     |     |     |
| ----------------- | -------------- | --- | --- | --- | --- |
The flow out of the reactor is determined by valve V . This valve is
5
normally controlled by process steps downstream. The control of the
reactor can be improved by introducing an override, which depends
onthestateofthereactor.Whenstartingthereactor,itisdesirableto
have the outlet valve closed until the reactor tank is half-full and the
reaction has started. This is achieved by introducing the tank level
and the tank temperature to the setpoint of the valve controller via
| limitersandminimum | selectors | asisshowninFigure7.43.Thevalve |     |     |     |
| ------------------ | --------- | ------------------------------ | --- | --- | --- |
V 5 is normally controlled by q sp .The minimum selector overrides the
| command | q when the level | L or the | temperature | T are | too low. |
| ------- | ---------------- | -------- | ----------- | ----- | -------- |
|         | sp               |          |             | r     |          |
L
M
|     | q   |     |     | V   |     |
| --- | --- | --- | --- | --- | --- |
|     | sp  |     | I   | 5   |     |
N
T
r
Figure 7.43 Block diagram for controlling the outflow of the re-
| actorthroughvalve | V 5 . |     |     |     |     |
| ----------------- | ----- | --- | --- | --- | --- |

7.10 Conclusions 321
7.10 Conclusions
In this chapter we have illustrated how complex control systems can
be built from simple components such as PID controllers, linear fil-
ters, gain schedules, and simple nonlinear functions. A number of
control paradigms have been introduced to guide system design.
The primary linear control paradigms are feedback by PID con-
trol, and feedforward. Cascade control can be used to enhance con-
trol performance through the use of extra measurements. Observers
can be used in a related way when measurements are not available.
Control by observers and state feedback may be viewed as a natural
extension of cascade control.
Smith predictors (discussed in Section 3.9) can be used to im-
prove control of systems with long dead time, and notch filters and
otherfilterswithcomplexpolesandzerosareusefulwhencontrolling
systems with poorly damped oscillatory modes.
Wealsodiscussedseveralnonlinearcomponentsandrelatedpara-
digms. The nonlinearities used are nonlinear functions, gain sched-
ules, limiters, and selectors. In Section 3.4, how simple PID con-
trollers could be enhanced by simple nonlinear functions was dis-
cussed. This was used to avoid windup and to provide special control
functions like “error squared on integral,” etc. Ratio control is a non-
linear strategy that admits control of two process variables so that
theirratioisconstant.InSection6.3wediscussedhowgainschedules
couldbeusedtocopewithcontrolofprocesses withnonlinear charac-
teristics. Gain schedules and nonlinear functions are also useful for
control paradigms such as surge tank control, where the goal is not
to keep process variables constant but to allow them to vary in pre-
scribed ranges. Selector control is another very important paradigm
that is used for constraint control where certain process variables
have to be kept within given constraints. We also showed that con-
trollers basedon neural and fuzzytechniques could beinterpreted as
nonlinear controllers.
Parameter estimation, discussed inSection2.7,canbeusedtoes-
timateprocessparameters.Adaptationandtuningareotherparadigms
that were discussed in Chapter 6.
There are many ways to use the different control paradigms. We
have also indicated that there may be difficulties due to interaction
of several loops.
7.11 References
Many aspects on the material of this chapter are found in the classi-
cal textbooks on process control such as (Buckley, 1964), (Shinskey,

| 322 | Chapter | 7 Control | Paradigms |     |     |     |     |     |     |
| --- | ------- | --------- | --------- | --- | --- | --- | --- | --- | --- |
1988), and (Seborg et al., 1989). A more specialized presentation is
|            | (Hägglund, |              | 1991).        |        | (Shinskey,            | 1981) |     | (Klefenz, |     |
| ---------- | ---------- | ------------ | ------------- | ------ | --------------------- | ----- | --- | --------- | --- |
| given      | in         |              | The           | books  |                       |       | and |           |     |
| 1986)      | focus on   | applications | to            | energy | systems.              |       |     |           |     |
| Themethods |            | discussed    | inthischapter |        | canallbecharacterized |       |     |           | as  |
bottom-up procedures in the sense that a complex system is built up
by combining simple components. An interesting view of this is pre-
|        | (Bristol, | 1980). |            |     |          |     |         |              |     |
| ------ | --------- | ------ | ---------- | --- | -------- | --- | ------- | ------------ | --- |
| sented | in        |        | A top-down |     | approach | is  | another | possibility. |     |
A discussion of this, which is outside the scope of this book, is found
| in (Seborg | et  | al., 1986). |     |     |     |     |     |     |     |
| ---------- | --- | ----------- | --- | --- | --- | --- | --- | --- | --- |
Cascadeandfeedforwardcontrolaretreatedinthestandardtexts
on control. A presentation with many practical aspects is found in
| (Tucker |     | 1960). |          |         |     |           |      |              |     |
| ------- | --- | ------ | -------- | ------- | --- | --------- | ---- | ------------ | --- |
|         | and | Wills, | Selector | control |     | is widely | used | in practice. |     |
Ageneralpresentationisgivenin(Åström,1987b).Manyapplications
aregiven inthebooks(Shinskey, 1978)and(Klefenz, 1986).Analysis
|      |               |     |          | (Foss, | 1981). |       |           |            |     |
| ---- | ------------- | --- | -------- | ------ | ------ | ----- | --------- | ---------- | --- |
| of a | simple scheme | is  | given in |        |        | It is | difficult | to analyse |     |
nonlinear systems. A stability analysis of a system with selectors is
|     | (Foss, | 1981). |     |     |     |     |     |     |     |
| --- | ------ | ------ | --- | --- | --- | --- | --- | --- | --- |
given in
(Mamdani,
| Fuzzy | control | has | been around |     | for a long | time, | see |     |     |
| ----- | ------- | --- | ----------- | --- | ---------- | ----- | --- | --- | --- |
1974), (Mamdani and Assilian, 1974), (King and Mamdani, 1977),
|     | (Tong, 1977). |     |              |          |     |          |           |          |     |
| --- | ------------- | --- | ------------ | -------- | --- | -------- | --------- | -------- | --- |
| and |               | It  | has recently | received |     | a lot of | attention | particu- |     |
larlyinJapan:see(Zadeh, 1988),(Tong,1984),(Sugeno, 1985),(Dri-
|       |         | 1993), | (Wang, | 1994). |     |           |     |      |      |
| ----- | ------- | ------ | ------ | ------ | --- | --------- | --- | ---- | ---- |
| ankov | et al., | and    |        |        | The | technique | has | been | used |
for automation of complicated processes that have previously been
controlled manually. Control ofcement kilns isatypical example, see
| (Holmblad |     |            | 1981). |       |     |      |           |     |        |
| --------- | --- | ---------- | ------ | ----- | --- | ---- | --------- | --- | ------ |
|           | and | stergaard, |        | There | has | been | a similar |     | devel- |
opment in neural networks, see, for example, (Hecht-Nielsen, 1990),
(Pao,1990),and(ÅströmandMcAvoy,1992).Therewasalotofactiv-
ityin neural networks during thelate1960s, whichvanished rapidly.
There was a rapid resurgence of interest in the 1980s. There are a
lot of exaggerations both in fuzzy and neural techniques, and no bal-
anced view of the relevance of the fields for control has yet emerged.
The paper (Willis et al., 1991) gives an overview of possible uses of
(Pottman
| neural | networks | for | process control, | and | the | paper |     | and | Se- |
| ------ | -------- | --- | ---------------- | --- | --- | ----- | --- | --- | --- |
borg,1993)describesanapplicationtocontrolofpH.Thepapers(Lee,
1990),(Huang,1991),and(Swiniarski,1991)describeapplications
to
PID controllers and their tuning. There have also been attempts to
merge fuzzy and neural control, see (Passino and Antsaklis, 1992)
|     | (Brown |             | 1994). |     |     |     |     |     |     |
| --- | ------ | ----------- | ------ | --- | --- | --- | --- | --- | --- |
| and |        | and Harris, |        |     |     |     |     |     |     |
Some fundamental issues related to interaction in systems are
treatedin(Rijnsdorp,1965a),(Rijnsdorp,1965b),and(McAvoy,1983).
|     |          |            |               |     | (Bristol, |     | 1966). |         |     |
| --- | -------- | ---------- | ------------- | --- | --------- | --- | ------ | ------- | --- |
| The | relative | gain array | was described |     | in        |     |        | Control | of  |
systems with strong interaction between many loops require tech-
niques that are very different from those discussed in this chapter,
see, for example, (Cutler and Ramaker, 1980) and (Seborg et al.,
| 1986). |         |        |          | (Buckley, | 1970). |     |     |     |     |
| ------ | ------- | ------ | -------- | --------- | ------ | --- | --- | --- | --- |
|        | Section | 7.9 is | based on |           |        |     |     |     |     |

Bibliography
(1988):
| Anderson, | K. L.,G.L. | Blankenship, |     | and | L.G. Lebow |     | “A rule- |
| --------- | ---------- | ------------ | --- | --- | ---------- | --- | -------- |
based PID controller.” In Proc. IEEE Conference on Decision and
| Control, | Austin, | Texas. |     |     |     |     |     |
| -------- | ------- | ------ | --- | --- | --- | --- | --- |
Anderssen, A. S. and E. T. White (1970): “Parameter estimation by
thetransferfunctionmethod.”ChemicalEngineeringScience,25,
pp. 1015–1021.
Anderssen, A. S. and E. T. White (1971): “Parameter estimation by
| the | weighted       | moments | method.” | Chemical |     | Engineering | Science, |
| --- | -------------- | ------- | -------- | -------- | --- | ----------- | -------- |
| 26, | pp. 1203–1221. |         |          |          |     |             |          |
Antsaklis, P. J., K. M. Passino, and S. J. Wang (1991): “An intro-
| duction   | to  | autonomous | control | systems.” | IEEE | Control | Systems |
| --------- | --- | ---------- | ------- | --------- | ---- | ------- | ------- |
| Magazine, |     | 11:4, pp.  | 5–13.   |           |      |         |         |
(1987a):
| Åström,   | K. J. |              | “Adaptive | feedback | control.” | Proc. | IEEE, 75, |
| --------- | ----- | ------------ | --------- | -------- | --------- | ----- | --------- |
| February, |       | pp. 185–217. | Invited   | paper.   |           |       |           |
Åström, K. J. (1987b): “Advanced control methods—Survey and as-
sessment of possibilities.” In Morris and Williams, Eds., Ad-
vanced Control in Computer Integrated Manufacturing, Proceed-
| ings  | 13th | Annual Advanced |          | Control | Conference. | Purdue | Univer- |
| ----- | ---- | --------------- | -------- | ------- | ----------- | ------ | ------- |
| sity, | West | Lafayette,      | Indiana. |         |             |        |         |
Åström,K.J.(1991):“Assessmentofachievableperformanceofsimple
feedback loops.” International Journal of Adaptive Control and
| Signal | Processing, |     | 5, pp. 3–19. |     |     |     |     |
| ------ | ----------- | --- | ------------ | --- | --- | --- | --- |
Åström, K. J. (1992): “Autonomous control.” In Bensoussan and Ver-
jus, Eds., Future Tendencies in Computer Science, Control and
| Applied  | Mathematics, |          | volume           | 653 | of Lecture | Notes | in Computer |
| -------- | ------------ | -------- | ---------------- | --- | ---------- | ----- | ----------- |
| Science, | pp.          | 267–278. | Springer-Verlag. |     |            |       |             |
(1984):
| Åström, | K. J. | and T. Hägglund |     |     | “Automatic | tuning | of simple |
| ------- | ----- | --------------- | --- | --- | ---------- | ------ | --------- |
regulators with specifications on phase and amplitude margins.”
| Automatica, |     | 20, pp. | 645–651. |     |     |     |     |
| ----------- | --- | ------- | -------- | --- | --- | --- | --- |
Åström, K. J. and T. Hägglund (1988): Automatic Tuning of PID
Controllers. Instrument Society of America, Research Triangle
| Park, | North | Carolina. |     |     |     |     |     |
| ----- | ----- | --------- | --- | --- | --- | --- | --- |
323

324 Bibliography
Åström, K. J., T. Hägglund, C. C. Hang, and W. K. Ho (1993): “Au-
tomatic tuning and adaptation for PID controllers—A survey.”
Control Engineering Practice, 1:4, pp. 699–714.
Åström,K.J.,C.C.Hang,P.Persson, andW.K.Ho(1992):“Towards
intelligent PID control.” Automatica, 28:1, pp. 1–9.
Åström, K. J. and T. J. McAvoy (1992): “Intelligent control.” Journal
of Process Control, 2:2, pp. 1–13.
Åström, K. J. and L. Rundqwist (1989): “Integrator windup and how
to avoid it.” In Proceedings of the American Control Conference
(ACC ’89), pp. 1693–1698, Pittsburgh, Pennsylvania.
Åström,K.J.andH.Steingrímsson(1991):“Implementation ofaPID
controlleronaDSP.”InAhmed,Ed.,DigitalControlApplications
with the TMS 320 Family, Selected Application Notes, pp. 205–
238. Texas Instruments.
Åström, K. J. and B. Wittenmark (1984): Computer Controlled
Systems—Theory and Design. Prentice-Hall, Englewood Cliffs,
New Jersey.
Åström, K. J. and B. Wittenmark (1989): Adaptive Control. Addison-
Wesley, Reading, Massachusetts.
Åström, K. J. and B. Wittenmark (1990): Computer Controlled Sys-
tems—Theory and Design. Prentice-Hall, Englewood Cliffs, New
Jersey, second edition.
Atherton, D. P. (1975): Nonlinear Control Engineering—Describing
Function Analysis and Design. Van Nostrand Reinhold Co., Lon-
don, UK.
Bialkowski, W. L. (1993): “Dreams versus reality: A view from both
sides of the gap.” Pulp and Paper Canada, 94:11.
Blickley, G. (1990): “Modern control started with ziegler-nichols tun-
ing.” Control Engineering, October, pp. 11–17.
Blickley, G. J. (1988): “PID tuning made easy with hand-held com-
puter.” Control Engineering, November, p. 99.
Boyd,S.P.andC.H.Barratt(1991):LinearControllerDesign–Limits
ofPerformance.PrenticeHallInc.,Englewood Cliffs,NewJersey.
Bristol,E.(1966):“Onanewmeasureofinteraction formultivariable
process control.” IEEE Transactions on Automatic Control, 11,
p. 133.
Bristol,E.H.(1967):“Asimpleadaptivesystemforindustrialcontrol.”
Instrumentation Technology, June.
Bristol,E.H.(1970):“Adaptive controlodyssey.”InISASilverJubilee
Conference, Paper 561–570, Philadelphia.
Bristol, E. H. (1977): “Pattern recognition: An alternative to param-

Bibliography 325
eter identification in adaptive control.” Automatica, 13, pp. 197–
202.
Bristol, E. H. (1980): “After DDC: Idiomatic (structured) control.”
In Proceedings American Institute of Chemical Engineering
(AIChE), Philadelphia.
Bristol, E. H. (1986): “The EXACT pattern recognition adaptive con-
troller, a user-oriented commercial success.” In Narendra, Ed.,
Adaptive and Learning Systems,pp. 149–163, New York.Plenum
Press.
Bristol, E. H., G. R. Inaloglu, and J. F. Steadman (1970): “Adaptive
processcontrolbypatternrecognition.”Instrum.ControlSystems,
pp. 101–105.
Bristol, E.H.andT.W.Kraus(1984):“Lifewithpattern adaptation.”
In Proc. 1984 American Control Conference, San Diego, Califor-
nia.
Brown, M. and C. Harris(1994): Neurofuzzy Adaptive Modelling and
Control. Prentice Hall.
Buckley, P. S. (1964): Techniques of Process Control. John Wiley &
Sons, Inc.
Buckley, P. S. (1970): “Protective controls for a chemical reactor.”
Chemical Engineering, April, pp. 145–150.
Callaghan, P. J., P. L. Lee, and R. B. Newell (1986): “Evaluation of
foxborocontroller.” ProcessControl Engineering, May, pp.38–40.
Callender, A., D. R. Hartree, and A. Porter (1936): “Time lag in a
control system.” Philos. Trans. A., 235, pp. 415–444.
Cameron, F. and D. E. Seborg (1983): “A self-tuning controller with
a PID structure.” Int. J. Control, 38:2, pp. 401–417.
Chen, B.-S. and S.-S. Wang (1988): “The stability of feedback con-
trolwith nonlinear saturating actuator: Time domain approach.”
IEEE Transactions on Automatic Control, 33, pp. 483–487.
Chen, C.-L. (1989): “A simple method for on-line identification and
controller tuning.” AIChE Journal, 35:12, pp. 2037–2039.
Chien, I. L. (1988): “IMC-PID controller design—an extension.”
In IFAC Symposium, Adaptive Control of Chemical Processes,
pp. 155–160, Copenhagen, Denmark.
Chien, I.-L. and P. S. Fruehauf (1990): “Consider IMC tuning to
improvecontrollerperformance.”ChemicalEngineeringProgress,
October, pp. 33–41.
Chien, K. L., J. A. Hrones, and J. B. Reswick (1952): “On the auto-
matic control of generalized passive systems.” Trans. ASME, 74,
pp. 175–185.

326 Bibliography
Clarke, D.W.(1984):“PID algorithms andtheir computer implemen-
tation.” Trans. Inst. M. C., 6:6, pp. 305–316.
Close, C. M. and D. K. Frederick (1993): Modeling and Analysis of
Dynamic Systems. Houghton Mifflin.
Cohen, G. H. and G. A. Coon (1953): “Theoretical consideration of
retarded control.” Trans. ASME, 75, pp. 827–834.
Coon, G. A. (1956a): “How to find controller settings from process
characteristics.” Control Engineering, 3, pp. 66–76.
Coon, G. A. (1956b): “How to set three-term controller.” Control En-
gineering, 3, pp. 71–76.
Corripio, A. B. (1990): Tuning of Industrial Control Systems. Instru-
ment Society of America.
Cutler, C. R. and B. C. Ramaker (1980): “Dynamic matrix control—
A computer control algorithm.” In Proceedings Joint Automatic
Control Conference, Paper WP5-B, San Francisco, California.
Dahlin, E. B. (1968): “Designing and tuning digital controllers.” In-
struments and Control Systems, 42, June, pp. 77–83.
Deshpande,P.B.andR.H.Ash(1981):ElementsofComputerProcess
Control with Advanced Control Applications. Instrument Society
of America, Research Triangle Park, North Carolina.
Dreinhofer, L. H. (1988): “Controller tuning for a slow nonlinear pro-
cess.” IEEE Control Systems Magazine, 8:2, pp. 56–60.
Driankov,D.,H.Hellendoorn, andM.Reinfrank (1993):AnIntroduc-
tion to Fuzzy Control. Springer-Verlag.
Dumont, G. A. (1986): “On the use of adaptive control in the pro-
cess industries.” In Morari and McAvoy, Eds., Proceedings Third
International Conference on Chemical Process Control–CPCIII,
Amsterdam. Elsevier.
Dumont, G.A.,J.M.Martin-S nchez,andC.C.Zervos (1989):“Com-
parison of an auto-tuned PID regulator and an adaptive predic-
tive control system on an industrial bleach plant.” Automatica,
25, pp. 33–40.
Elgerd,O.I.andW.C.Stephens(1959):“Effectofclosed-loop transfer
function pole and zero locations on the transient response of
linear control systems.” Applications and Industry, 42, pp. 121–
127.
Ender,D.B.(1993):“Processcontrolperformance: Notasgoodasyou
think.” Control Engineering, 40:10, pp. 180–190.
Fertik, H. A. (1975): “Tuning controllers for noisy processes.” ISA
Transactions, 14, pp. 292–304.
Fertik,H.A.andC.W.Ross(1967):“Directdigitalcontrolalgorithms

|      |             |           |     |     |         |          | Bibliography | 327 |
| ---- | ----------- | --------- | --- | --- | ------- | -------- | ------------ | --- |
| with | anti-windup | feature.” |     | ISA | Trans., | 6:4, pp. | 317–328.     |     |
(1981):
Foss, A. M. “Criterion to assess stability of a ‘lowest wins’
| control | strategy.” | IEEE | Proc. | Pt. | D, 128:1, | pp. | 1–8. |     |
| ------- | ---------- | ---- | ----- | --- | --------- | --- | ---- | --- |
(1979):
| Foxboro, | Inc. | Controller |     | Tuning | Guide, | PUB | 342A. |     |
| -------- | ---- | ---------- | --- | ------ | ------ | --- | ----- | --- |
(1990):
| Frank, P. | M.        | “Fault          | diagnosis |              | in dynamic   |     | systems | using an- |
| --------- | --------- | --------------- | --------- | ------------ | ------------ | --- | ------- | --------- |
| alytical  | and       | knowledge-based |           | redundancy—A |              |     | survey  | and some  |
| new       | results.” | Automatica,     |           | 26:3,        | pp. 459–474. |     |         |           |
(1967):
| Fröhr, F. |     | “Optimierung |               | von | Regelkreisen |     | nach dem   | Betrag- |
| --------- | --- | ------------ | ------------- | --- | ------------ | --- | ---------- | ------- |
| soptimum  | und | dem          | symmetrischen |     | Optimum.”    |     | Automatik, | 12,     |
| January,  | pp. | 9–14.        |               |     |              |     |            |         |
Fröhr, F. and F. Orttenburger (1982): Introduction to Electronic Con-
| trolEngineering.SiemensAktiengesellschaft, |     |     |     |     |     |     | Heyden&SonLtd, |     |
| ------------------------------------------ | --- | --- | --- | --- | --- | --- | -------------- | --- |
London.
Gallun, S. E., C. W. Matthews, C. P. Senyard, and B. Slater (1985):
“Windup protection and initialization for advanced digital con-
| trol.” | Hydrocarbon |     | Processing, | June, | pp. | 63–68. |     |     |
| ------ | ----------- | --- | ----------- | ----- | --- | ------ | --- | --- |
Gawthrop, P. J. (1986): “Self-tuning PID controllers: Algorithms and
| implementation.” |     | IEEE | Transactions |     | on  | Automatic | Control, | 31, |
| ---------------- | --- | ---- | ------------ | --- | --- | --------- | -------- | --- |
pp. 201–209.
(1968):
| Gelb, A. and | W.            | E. V. Velde |        |         | Multiple-Input |     | Describing | Func- |
| ------------ | ------------- | ----------- | ------ | ------- | -------------- | --- | ---------- | ----- |
| tions        | and Nonlinear |             | System | Design. | McGraw-Hill,   |     | New        | York. |
Gerry,J.P.(1987):“AcomparisonofPIDcontroller algorithms.” Con-
| trol Engineering, |     | March, |     | pp. 102–105. |     |     |     |     |
| ----------------- | --- | ------ | --- | ------------ | --- | --- | --- | --- |
(1959):
| Gille, J.C.,M. | J.Pelegrin,  |     | and | P.Decaulne |     |     | Feedback | Control |
| -------------- | ------------ | --- | --- | ---------- | --- | --- | -------- | ------- |
| Systems.       | McGraw-Hill, |     | New | York.      |     |     |          |         |
A.H.,L.Guzzella,andW.Schaufelberger(1988):“Bump-
Glattfelder,
lesstransfer,anti-reset-windup, saturatingandoverridecontrols:
A status report on self-tuning regulators.” In Proceedings of
| IMACS-88, |     | Part 2, | pp. 66–72, | Paris, | France. |     |     |     |
| --------- | --- | ------- | ---------- | ------ | ------- | --- | --- | --- |
Glattfelder, A. H. and Schaufelberger (1983): “Stability analysis of
single loop systems with saturation and antireset-windup cir-
cuits.” IEEE Transactions on Automatic Control, 28, pp. 1074–
1081.
Glattfelder, A. H. and W. Schaufelberger (1986): “Start-up per-
formance of different proportional-integral-anti-wind-up regula-
| tors.” | International |     | Journal | of Control, |     | 44, pp. | 493–505. |     |
| ------ | ------------- | --- | ------- | ----------- | --- | ------- | -------- | --- |
Goff,K.W.(1966a):“DynamicsindirectdigitalcontrolI—Estimating
characteristics and effects of noisy signals.” ISA Journal, 13,
| November, | pp. | 45–49. |     |     |     |     |     |     |
| --------- | --- | ------ | --- | --- | --- | --- | --- | --- |
(1966b):
| Goff, K. | W.       | “Dynamics |        | in       | direct | digital  | control II—A  | sys- |
| -------- | -------- | --------- | ------ | -------- | ------ | -------- | ------------- | ---- |
| tematic  | approach |           | to DDC | design.” | ISA    | Journal, | 13, December, |      |

328 Bibliography
pp. 44–54.
(1953):
| Graham, | D. and | R. C. | Lathrop |     | “The | synthesis | of  | ‘optimum’ |
| ------- | ------ | ----- | ------- | --- | ---- | --------- | --- | --------- |
transient response: Criteria and standard forms.” Transactions
| of the | AIEE, | 72, November, |     | pp. | 273–288. |     |     |     |
| ------ | ----- | ------------- | --- | --- | -------- | --- | --- | --- |
Grebe, J. J., R. H. Boundy, and R. W. Cermak (1933): “The control
of chemical processes.” Trans. of American Institute of Chemical
| Engineers, |     | 29, pp. | 211–255. |     |     |     |     |     |
| ---------- | --- | ------- | -------- | --- | --- | --- | --- | --- |
Haalman, A. (1965): “Adjusting controllers for a deadtime process.”
| Control | Engineering, |     | July-65, |     | pp. 71–73. |     |     |     |
| ------- | ------------ | --- | -------- | --- | ---------- | --- | --- | --- |
Habel, F. (1980): “Ein Verfahren zur Bestimmung der Parametern
von PI-, PD- und PID-Reglern.” Regelungstechnik, 28:6, pp. 199–
205.
Hägglund,T.(1991):ProcessControlinPractice.Chartwell-BrattLtd,
| Bromley, |     | UK. |     |     |     |     |     |     |
| -------- | --- | --- | --- | --- | --- | --- | --- | --- |
(1992):
| Hägglund, | T.  |     | “A predictive |     | PI controller | for | processes | with |
| --------- | --- | --- | ------------- | --- | ------------- | --- | --------- | ---- |
long dead times.” IEEE Control Systems Magazine, 12:1, pp. 57–
60.
Hägglund, T. (1993): “Disturbance supervision in feedback loops.” In
Preprints Tooldiag’93, International Conference onFaultDiagno-
| sis, | Toulouse, | France. |     |     |     |     |     |     |
| ---- | --------- | ------- | --- | --- | --- | --- | --- | --- |
Hägglund, T. and K. J. Åström (1991): “Industrial adaptive con-
trollersbasedonfrequencyresponsetechniques.”Automatica,27,
pp. 599–609.
(1991):
| Hang, C. | C., | K. J. Åström, | and | W.  | K. Ho | “Refinements |     | of the |
| -------- | --- | ------------- | --- | --- | ----- | ------------ | --- | ------ |
Ziegler-Nichols tuning formula.” IEE Proceedings, Part D, 138:2,
pp. 111–118.
(1993a):
| Hang, C. | C., K. | J. Åström, | and | W. K. | Ho  | “Relay | auto-tuning |     |
| -------- | ------ | ---------- | --- | ----- | --- | ------ | ----------- | --- |
in the presence of static load disturbance.” Automatica, 29:2,
pp. 563–564.
Hang, C. C., T. H. Lee, and W. K. Ho (1993b): Adaptive Control.
| Instrument |     | Society | of America, |     | Research | Triangle | Park, | North |
| ---------- | --- | ------- | ----------- | --- | -------- | -------- | ----- | ----- |
Carolina.
Hang, C. C. and K. K. Sin (1991): “An on-line auto-tuning method
| based        | on  | cross-correlation.” |              | IEEE | Transactions |     | on  | Industrial |
| ------------ | --- | ------------------- | ------------ | ---- | ------------ | --- | --- | ---------- |
| Electronics, |     | 38:6,               | pp. 428–437. |      |              |     |     |            |
Hanus, R. (1988): “Antiwindup and bumpless transfer: a survey.” In
| Proceedings |     | of IMACS-88, |     | Part | 2, pp. 59–65, | Paris, | France. |     |
| ----------- | --- | ------------ | --- | ---- | ------------- | ------ | ------- | --- |
Hanus, R., M. Kinnaert, and J.-L. Henrotte (1987): “Conditioning
technique,ageneralanti-windupandbumplesstransfermethod.”
| Automatica, |            | 23:729–739. |     |          |              |     |           |     |
| ----------- | ---------- | ----------- | --- | -------- | ------------ | --- | --------- | --- |
| Harriott,   | P. (1964): | Process     |     | Control. | McGraw-Hill, |     | New York. |     |

Bibliography 329
Harris,C.J.andS.A.Billings, Eds.(1981):Self-tuningandAdaptive
Control: Theory and Applications. Peter Peregrinus, London.
Hartree, D. R., A. Porter, A. Callender, and A. B. Stevenson (1937):
“Time-lag in control systems—II.” Proceedings of the Royal Soci-
ety of London, 161, pp. 460–476.
Hawk,Jr.,W.M.(1983):“Aself-tuning,self-containedPIDcontroller.”
In Proc. 1983 American Control Conference, pp. 838–842, San
Francisco, California.
Hazebroek, P. and B. L. van der Waerden (1950): “Theoretical con-
siderations on the optimum adjustment of regulators.” Trans.
ASME, 72, pp. 309–322.
Hazen,H.L.(1934):“Theoryofservomechanisms.” JFI,218,pp.283–
331.
Hecht-Nielsen, R. (1990): Neurocomputing. Addison-Wesley.
Hess, P.,F.Radke, and R.Schumann (1987): “Industrial applications
of a PID self-tuner used for system start-up.” In Preprints 10th
IFAC World Congress, volume 3, pp. 21–26, Munich, Germany.
Higham, E. H. (1985): “A self-tuning controller based on expert sys-
tems and artificial intelligence.” In Proceedings of Control 85,
pp. 110–115, England.
Higham, J.D.(1968):“‘Single-term’ control offirst- andsecond-order
processes with dead time.” Control, February, pp. 2–6.
Holmblad, L. P. and J. stergaard (1981): “Control of a cement kiln
by fuzzy logic.” F.L. Smidth Review, 67, pp. 3–11. Copenhagen,
Denmark.
Hoopes,H.S.,W.M.Hawk,Jr.,andR.C.Lewis(1983):“Aself-tuning
controller.” ISA Transactions, 22:3, pp. 49–58.
Horowitz, I. M. (1963): Synthesis of Feedback Systems. Academic
Press, New York.
Howes, G. (1986): “Control of overshoot in plastics-extruder barrel
zones.” In EI Technology, No. 3, pp. 16–17. Eurotherm Interna-
tional, Brighton, UK.
Huang, Z. (1991): “Auto-tuning of PID controllers using neural net-
works.” In Preprints IFAC International Symposium on Intelli-
gent Tuning and Adaptive Control (ITAC 91), Singapore.
Hwang, S.-H. and H.-C. Chang (1987): “A theoretical examination
of closed-loop properties and tuning methods of single-loop PI
controllers.” Chemical Engineering Science, 42, pp. 2395–2415.
Isermann, R.(1980): “Practical aspects of process identification.” Au-
tomatica, 16, pp. 575–587.
Isermann, R. (1982): “Parameter adaptive control algorithms—A tu-

330 Bibliography
torial.” Automatica, 18, pp. 513–528.
Isermann, R. (1984): “Process fault detection based on modeling and
estimation methods—A survey.” Automatica, 20, pp. 387–404.
Isermann, R., W. Appel, B. Freyermuth, A. Fuchs, W. Janik, D. Neu-
mann, T. Reiss, and P. Wanke (1990): “Model based fault diag-
nosis and supervision of machines and drives.” In Preprints 11th
IFAC World Congress, Tallinn, Estonia.
Ivanoff, A. (1934): “Theoretical foundations of the automatic regula-
tion of temperature.” J. Institute of Fuel, 7, pp. 117–138.
Johansson, R. (1993): System Modeling and Identification. Prentice
Hall, Englewood Cliffs, New Jersey.
Kapasouris, P. and M. Athans (1985): “Multivariable control sys-
tems with saturating actuators antireset windup strategies.” In
Proc.Automatic ControlConference,pp.1579–1584,Boston,Mas-
sachusetts.
Kaya, A. and S. Titus (1988): “A critical performance evaluation of
four single loop self tuning control products.” In Proceedings of
the 1988 American Control Conference, Atlanta, Georgia.
Kessler, C. (1958a): “Das symmetrische Optimum, Teil I.” Regelung-
stechnik, 6:11, pp. 395–400.
Kessler, C. (1958b): “Dassymmetrische Optimum, Teil II.”Regelung-
stechnik, 6:12, pp. 432–436.
King, P. J. and E. H. Mamdani (1977): “The application of fuzzy
controlsystemstoindustrialprocesses.”Automatica,13,pp.235–
242.
Klefenz, G. (1986): Automatic Control of Steam Power Plants. Bibli-
ographisches Institut, third edition.
Klein, M., T. Marczinkowsky, and M. Pandit (1991): “An elemen-
tary pattern recognition self-tuning PI-controller.” In Preprints
IFAC International Symposium on Intelligent Tuning and Adap-
tive Control (ITAC 91), volume 1, Singapore.
Kramer, L. C. and K. W. Jenkins (1971): “A new technique for pre-
venting direct digital control windup.” In Proc. Joint Automatic
Control Conference, pp. 571–577, St Louis, Missouri.
Kraus, T. W. and T. J. Myron (1984): “Self-tuning PID controller
uses pattern recognition approach.” Control Engineering, June,
pp. 106–111.
Krikelis,N.J.(1984):“Designoftrackingsystemssubjecttoactuators
and saturation and integrator windup.” International Journal of
Control, 39:4, pp. 667–682.
Küpfmüller, K. (1928): “Über die Dynamik der selbststätigen Ver-

|                   |     |     |         |              |     | Bibliography |     | 331 |
| ----------------- | --- | --- | ------- | ------------ | --- | ------------ | --- | --- |
| stärkungsregler.” |     |     | ENT, 5, | pp. 459–467. |     |              |     |     |
Lee, C. C. (1990): “A self-learning rule-based controller with approx-
imate reasoning and neural nets.” In Preprints 11th IFAC World
| Congress, | Tallinn, |     | Estonia. |     |     |     |     |     |
| --------- | -------- | --- | -------- | --- | --- | --- | --- | --- |
Leva,A.(1993):“PIDautotuning algorithm basedonrelayfeedback.”
| IEE | Proceedings |     | D, 140:5, | pp. 328–338. |     |     |     |     |
| --- | ----------- | --- | --------- | ------------ | --- | --- | --- | --- |
Ljung,L.(1987):SystemIdentification—Theory
fortheUser.Prentice
| Hall, | Englewood |     | Cliffs, New | Jersey. |     |     |     |     |
| ----- | --------- | --- | ----------- | ------- | --- | --- | --- | --- |
(1983):
| Ljung, L.andT.Söderström |     |     |        |            | Theory         | andPractice |     | of Recursive |
| ------------------------ | --- | --- | ------ | ---------- | -------------- | ----------- | --- | ------------ |
| Identification.          |     | MIT | Press, | Cambridge, | Massachusetts. |             |     |              |
Lloyd, S. G. and G. D. Anderson (1971): Industrial Process Control.
| Fisher | Controls | Co., | Marshalltown, |     | Iowa. |     |     |     |
| ------ | -------- | ---- | ------------- | --- | ----- | --- | --- | --- |
(1968):
| L&N    | Leeds |     | & Northrup | Technical |     | Journal. | Spring | Issue, |
| ------ | ----- | --- | ---------- | --------- | --- | -------- | ------ | ------ |
| Number | 3.    |     |            |           |     |          |        |        |
Lopez, A. M., J. A. Miller, C. L. Smith, and P. W. Murrill (1967):
“Tuningcontrollerswitherror-integralcriteria.”Instrumentation
| Technology, |     | November, | pp. | 57–62. |     |     |     |     |
| ----------- | --- | --------- | --- | ------ | --- | --- | --- | --- |
(1969):
| Lopez, | A. M., P. | W. Murrill, | and | C.  | L. Smith |     | “Tuning | PI and |
| ------ | --------- | ----------- | --- | --- | -------- | --- | ------- | ------ |
PID digital controllers.” Instruments and Control Systems, 42,
| February, |     | pp. 89–95. |     |     |     |     |     |     |
| --------- | --- | ---------- | --- | --- | --- | --- | --- | --- |
Lukas,M.P.(1986):DistributedProcessControlSystems—TheirEval-
| uation | and | Design. | Van Nostrand |     | Reinhold, | New | York. |     |
| ------ | --- | ------- | ------------ | --- | --------- | --- | ----- | --- |
(1990):
| Luyben,  | W. L.      |     | Process      | Modeling, | Simulation |          | and | Control for |
| -------- | ---------- | --- | ------------ | --------- | ---------- | -------- | --- | ----------- |
| Chemical | Engineers. |     | McGraw-Hill, |           | second     | edition. |     |             |
Maciejowski, J. M. (1989): Multivariable Feedback Design. Addison-
| Wesley, | Reading, |     | Massachusetts. |     |     |     |     |     |
| ------- | -------- | --- | -------------- | --- | --- | --- | --- | --- |
(1974):
Mamdani, E. H. “Application of fuzzy algorithm for control of
| simple | dynamic | plant.” | Proc. | IEE, | 121, | pp. 1585–1588. |     |     |
| ------ | ------- | ------- | ----- | ---- | ---- | -------------- | --- | --- |
Mamdani, E. H. and S. Assilian (1974): “A case study on the appli-
cation of fuzzy set theory to automatic control.” In Proceedings
| IFAC | Stochastic | Control |     | Symposium, | Budapest, |     | Hungary. |     |
| ---- | ---------- | ------- | --- | ---------- | --------- | --- | -------- | --- |
(1989):
| Mantz, | R. J. and | E.  | J. Tacconi |     | “Complementary |     |     | rules to |
| ------ | --------- | --- | ---------- | --- | -------------- | --- | --- | -------- |
Ziegler and Nichols’ rules for a regulating and tracking con-
troller.” International Journal of Control, 49, pp. 1465–1471.
(1989):
| Marsik, | J. and | V. Strejc |     | “Application |     | of  | identification-free |     |
| ------- | ------ | --------- | --- | ------------ | --- | --- | ------------------- | --- |
algorithms for adaptive control.” Automatica, 25, pp. 273–277.
Marsili-Libelli, S. (1981): “Optimal design of PID regulators.” Inter-
| national | Journal |     | of Control, | 33:4, | pp. 601–616. |     |     |     |
| -------- | ------- | --- | ----------- | ----- | ------------ | --- | --- | --- |
Maxwell,J.C.(1868):“Ongovernors.”ProceedingsoftheRoyalSociety
| of  | London, | 16, pp. | 270–283. | Also | published |     | in “Mathematical |     |
| --- | ------- | ------- | -------- | ---- | --------- | --- | ---------------- | --- |
Trends in Control Theory” edited by R. Bellman and R. Kalaba,

332 Bibliography
| Dover | Publications, |     | New | York 1964, | pp. | 3–17. |     |     |     |
| ----- | ------------- | --- | --- | ---------- | --- | ----- | --- | --- | --- |
(1983):
| McAvoy, | T. J. |     | Interaction | Analysis: |     | Principles | and | Applica- |     |
| ------- | ----- | --- | ----------- | --------- | --- | ---------- | --- | -------- | --- |
tions. Instrument Society of America, Research Triangle Park,
| North | Carolina. |     |     |     |     |     |     |     |     |
| ----- | --------- | --- | --- | --- | --- | --- | --- | --- | --- |
McMillan, G. K. (1983): Tuning and Control Loop Performance. In-
strumentSocietyofAmerica,ResearchTrianglePark,NorthCar-
| olina, | second | edition. |     |     |     |     |     |     |     |
| ------ | ------ | -------- | --- | --- | --- | --- | --- | --- | --- |
McMillan,G.K.(1986):“Advancedcontrolalgorithms:Bewareoffalse
| prophecies.” |     | InTech, | January, | pp. | 55–57. |     |     |     |     |
| ------------ | --- | ------- | -------- | --- | ------ | --- | --- | --- | --- |
McMillan, G. K., W. K. Wojsznis, and G. T. Borders, Jr (1993a):
“Flexible gain scheduler.” In Advances in Instrumentation and
| Control, |     | volume | 48 of ISA | Conference, |     | pp. 811–818. |     |     |     |
| -------- | --- | ------ | --------- | ----------- | --- | ------------ | --- | --- | --- |
McMillan, G. K., W. K. Wojsznis, and K. Meyer (1993b): “Easy tuner
forDCS.”InAdvancesinInstrumentationandControl,volume48
| of  | ISA Conference, |     | pp. 703–710. |     |     |     |     |     |     |
| --- | --------------- | --- | ------------ | --- | --- | --- | --- | --- | --- |
Meyer, C., D. E. Seborg, and R. K. Wood (1976): “A comparison of
theSmithpredictorandconventionalfeedbackcontrol.”Chemical
| Engineering |     | Science, | 31, | pp. 775–778. |     |     |     |     |     |
| ----------- | --- | -------- | --- | ------------ | --- | --- | --- | --- | --- |
(1967):
Miller, J. A., A. M. Lopez, C. L. Smith, and P. W. Murrill “A
comparisonofcontrollertuningtechniques.”ControlEngineering,
| December, |     | pp. 72–75. |     |     |     |     |     |     |     |
| --------- | --- | ---------- | --- | --- | --- | --- | --- | --- | --- |
(1922):
| Minorsky, | N.  |     | “Directional | stability |     | of automatically |     | steered |     |
| --------- | --- | --- | ------------ | --------- | --- | ---------------- | --- | ------- | --- |
bodies.” J. Amer. Soc. of Naval Engineers, 34:2, pp. 280–309.
(1970):
| Moore, | C. F., | C. L. Smith, | and | P. W. | Murrill |     | “Improved |     | algo- |
| ------ | ------ | ------------ | --- | ----- | ------- | --- | --------- | --- | ----- |
rithm for direct digital control.” Instruments & Control Systems,
| 43, | January, | pp. | 70–74. |     |     |     |     |     |     |
| --- | -------- | --- | ------ | --- | --- | --- | --- | --- | --- |
(1991):
| Morari, | M. andJ.H. |         | Lee     | “Model      | predictive |         | control: | The    | good, |
| ------- | ---------- | ------- | ------- | ----------- | ---------- | ------- | -------- | ------ | ----- |
| the     | bad,       | and the | ugly.”  | In Chemical |            | Process | Control, | CPCIV, |       |
| pp.     | 419–442,   | Padre   | Island, | Texas.      |            |         |          |        |       |
Morris, H. M. (1987): “How adaptive are adaptive process con-
| trollers?” |     | Control | Engineering, | 34-3, | pp. | 96–100. |     |     |     |
| ---------- | --- | ------- | ------------ | ----- | --- | ------- | --- | --- | --- |
Nachtigal,C.L.(1986a):“Adaptivecontrollerperformanceevaluation:
| Foxboro |     | EXACT | and ASEA | Novatune.” |     | In Proceedings |     | ACC-86, |     |
| ------- | --- | ----- | -------- | ---------- | --- | -------------- | --- | ------- | --- |
pp. 1428–1433.
(1986b):
| Nachtigal, | C.      | L.             | “Adaptive |          | controller | simulated |     | process     | re- |
| ---------- | ------- | -------------- | --------- | -------- | ---------- | --------- | --- | ----------- | --- |
| sults:     | Foxboro |                | EXACT     | and ASEA | Novatune.” |           | In  | Proceedings |     |
| ACC-86,    |         | pp. 1434–1439. |           |          |            |           |     |             |     |
Newton, Jr, G. C., L. A. Gould, and J. F. Kaiser (1957): Analytical
| Design | of  | Linear | Feedback | Controls. | John | Wiley | & Sons. |     |     |
| ------ | --- | ------ | -------- | --------- | ---- | ----- | ------- | --- | --- |
(1980):
| Nicholson, | H.,         | Ed. |     | Modelling | of Dynamical |     | Systems, | Vol. | 1.  |
| ---------- | ----------- | --- | --- | --------- | ------------ | --- | -------- | ---- | --- |
| Peter      | Peregrinus. |     |     |           |              |     |          |      |     |

|     |     |     |     |     |     | Bibliography |     | 333 |
| --- | --- | --- | --- | --- | --- | ------------ | --- | --- |
(1981):
| Nicholson, | H.,         | Ed. | Modelling |     | of Dynamical |     | Systems, | Vol. 2. |
| ---------- | ----------- | --- | --------- | --- | ------------ | --- | -------- | ------- |
| Peter      | Peregrinus. |     |           |     |              |     |          |         |
Nishikawa, Y., N. Sannomiya, T. Ohta, and H. Tanaka (1984): “A
method for auto-tuning of PID control parameters.” Automatica,
| 20, | pp. 321–332. |     |     |     |     |     |     |     |
| --- | ------------ | --- | --- | --- | --- | --- | --- | --- |
(1932):
| Nyquist, | H.  |         | “Regeneration |      | theory.”  | Bell | System Technical |     |
| -------- | --- | ------- | ------------- | ---- | --------- | ---- | ---------------- | --- |
| Journal, |     | 11, pp. | 126–147.      | Also | published |      | in “Mathematical |     |
Trends in Control Theory” edited by R. Bellman and R. Kalaba,
| Dover | Publications, |     | New | York | 1964, pp. | 83–105. |     |     |
| ----- | ------------- | --- | --- | ---- | --------- | ------- | --- | --- |
Oldenburg,R.C.andH.Sartorius(1954):“Auniformapproachtothe
optimumadjustmentofcontrolloops.”TransactionsoftheASME,
| 76, | November, | pp. | 1265–1279. |     |     |     |     |     |
| --- | --------- | --- | ---------- | --- | --- | --- | --- | --- |
(1964):
| Oppelt, | W.      | KleinesHandbuch |     |     | technischer | Regelvorgänge. |     | Ver- |
| ------- | ------- | --------------- | --- | --- | ----------- | -------------- | --- | ---- |
| lag     | Chemie, | Weinheim.       |     |     |             |                |     |      |
Pagano, D. (1991): “Intelligent tuning of PID controllers based on
production rules system.” In Preprints IFAC International Sym-
| posium | on  | Intelligent | Tuning |     | and Adaptive | Control | (ITAC | 91), |
| ------ | --- | ----------- | ------ | --- | ------------ | ------- | ----- | ---- |
Singapore.
Palmor, Z. J. and R. Shinnar (1979): “Design of sampled data con-
| trollers.” | Ind. | Eng.Chem.ProcessDesignandDevelopment, |     |     |     |     |     | 18:1, |
| ---------- | ---- | ------------------------------------- | --- | --- | --- | --- | --- | ----- |
pp. 8–30.
Pao, H. H. (1990): “Use of neural-net technology in control: A sur-
vey and a perspective.” In Preprints 11th IFAC World Congress,
| Tallinn, | Estonia. |     |     |     |     |     |     |     |
| -------- | -------- | --- | --- | --- | --- | --- | --- | --- |
(1992):
| Passino,    | K. M. | and            | P. J. Antsaklis, |          | Eds.   | An       | Introduction | to       |
| ----------- | ----- | -------------- | ---------------- | -------- | ------ | -------- | ------------ | -------- |
| Intelligent |       | and Autonomous |                  | Control. | Kluwer | Academic |              | Publish- |
ers.
(1989):
| Patton, | R. J., | P. M. | Frank, | and R. | N. Clark |     | Fault | Diagno- |
| ------- | ------ | ----- | ------ | ------ | -------- | --- | ----- | ------- |
sis in Dynamic Systems, Theory and Applications. Prentice-Hall,
| Englewood |     | Cliffs, | New Jersey. |     |     |     |     |     |
| --------- | --- | ------- | ----------- | --- | --- | --- | --- | --- |
Patwardhan, A. A., M. N. Karim, and R. Shah (1987): “Controller
tuning by a least squares method.” AIChE Journal, 33, October,
pp. 1735–1737.
Pemberton,T.J.(1972a):“PID:Thelogicalcontrolalgorithm.”Control
| Engineering, |     | May, | pp. 66–67. |     |     |     |     |     |
| ------------ | --- | ---- | ---------- | --- | --- | --- | --- | --- |
(1972b):
| Pemberton, | T.           | J.  | “PID: | The | logical | control | algorithm–II.” |     |
| ---------- | ------------ | --- | ----- | --- | ------- | ------- | -------------- | --- |
| Control    | Engineering, |     | July, | pp. | 61–63.  |         |                |     |
Persson, P. (1992): Towards Autonomous PID Control. PhD thesis
| ISRNLUTFD2/TFRT--1037--SE,Department |      |           |                |     |       |         | ofAutomatic | Con- |
| ------------------------------------ | ---- | --------- | -------------- | --- | ----- | ------- | ----------- | ---- |
| trol,                                | Lund | Institute | of Technology, |     | Lund, | Sweden. |             |      |
(1992):
| Persson, | P. and | K. J. | Åström |     | “Dominant | pole | design—A | uni- |
| -------- | ------ | ----- | ------ | --- | --------- | ---- | -------- | ---- |
fied view of PID controller tuning.” In Preprints 4th IFAC Sym-

334 Bibliography
posium on Adaptive Systems in Control and Signal Processing,
pp. 127–132, Grenoble, France.
Persson, P. and K. J. Åström (1993): “PID control revisited.” In
Preprints IFAC 12th World Congress, Sydney, Australia.
Pessen, B. W. (1954): “How to ‘tune in’ a three mode controller.”
Instrumentation, Second Quarter, pp. 29–32.
Polonoyi, M.J.G.(1989):“PIDcontroller tuning using standard form
optimization.” Control Engineering, March, pp. 102–106.
Porter, B., A. H. Jones, and C. B. McKeown (1987): “Real-time ex-
pert tuners for PI controllers.” IEE Proceedings Part D, 134:4,
pp. 260–263.
Pottman, M.andD.E.Seborg(1993):“Aradialbasisfunction control
strategy and its application to a pH neutralization process.” In
Proceedings 2nd European Control Conference, ECC ’93, Gronin-
gen, The Netherlands.
Rad,A.B.andP.J.Gawthrop(1991):“ExplicitPIDself-tuningcontrol
for systems with unknown time delay.” In Preprints IFAC Inter-
national Symposium on Intelligent Tuning and Adaptive Control
(ITAC 91), volume 5, Singapore.
Radke, F. and R. Isermann (1987): “A parameter-adaptive PID con-
troller with stepwise parameter optimization.” Automatica, 23,
pp. 449–457.
Rake, H. (1980): “Step response and frequency response methods.”
Automatica, 16, pp. 519–526.
Rijnsdorp, J.(1965a):“Interaction intwo-variable controlsystemsfor
distillation columns – I.” Automatica, 1, p. 15.
Rijnsdorp, J.(1965b):“Interaction intwo-variable controlsystemsfor
distillation columns – II.” Automatica, 1, pp. 29–51.
Rivera, D. E., M. Morari, and S. Skogestad (1986): “Internal model
control—4. PID controller design.” Ind. Eng. Chem. Proc. Des.
Dev., 25, pp. 252–265.
Ross,C.W.(1977):“Evaluation ofcontrollersfordeadtimeprocesses.”
ISA Transactions, 16:3, pp. 25–34.
Rovira, A. A., P. W. Murrill, and C. L. Smith (1969): “Tuning con-
trollers for setpoint changes.” Instruments and Control Systems,
December, pp. 67–69.
Rundqwist, L. (1990): “Anti-reset windup for PID controllers.” In
Preprints 11th IFAC World Congress, Tallinn, Estonia.
Schei,T.S.(1992):“Amethod forclosed loopautomatic tuning ofPID
controllers.” Automatica, 28:3, pp. 587–591.
Seborg, D. E., T. F. Edgar, and D. A. Mellichamp (1989): Process

Bibliography 335
Dynamics and Control. Wiley, New York.
Seborg, D. E., T. F. Edgar, and S. L. Shah (1986): “Adaptive con-
trol strategies for process control: A survey.” AIChE Journal, 32,
pp. 881–913.
Shigemasa, T., Y. Iino, and M. Kanda (1987): “Two degrees of free-
dom PID auto-tuning controller.” In Proceedings of ISA Annual
Conference, pp. 703–711.
Shinskey, F. G. (1978): Energy Conservation through Control. Aca-
demic Press, New York.
Shinskey, F. G. (1981): Controlling Multivariable Processes. Instru-
ment Society of America, Research Triangle Park, North Car-
olina.
Shinskey, F. G. (1988): Process-Control Systems. Application, Design,
and Tuning. McGraw-Hill, New York, third edition.
Shinskey, F.G.(1990):“How good areour controllers inabsolute per-
formance and robustness?” Measurement and Control, 23, May,
pp. 114–121.
Shinskey, F. G. (1991a): “Evaluating feedback controllers challenges
users and vendors.” Control Engineering, September, pp. 75–78.
Shinskey, F. G. (1991b): “Model predictors: The first smart con-
trollers.” Instruments and Control Systems, September, pp. 49–
52.
Smith, C. L. (1972): Digital Computer Process Control. Intext Educa-
tional Publishers, Scranton, Pennsylvania.
Smith, C. L., A. B. Corripio, and J. J. Martin (1975): “Controller
tuningfromsimpleprocessmodels.”InstrumentationTechnology,
December, pp. 39–44.
Smith, C. L. and P. W. Murrill (1966): “A more precise method for
tuning controllers.” ISA Journal, May, pp. 50–58.
Smith,O.J.M.(1957):“Closecontrolofloopswithdeadtime.”Chem-
ical Engineering Progress, 53, May, pp. 217–219.
Söderström, T. and P. Stoica (1988): System Identification. Prentice-
Hall International, Hemel Hempstead, UK.
Stephanopoulos (1984):Chemical Process Control. AnIntroduction to
Theory and Practice. Prentice-Hall.
Stock, J. T. (1987–88): “Pneumatic process controllers: The ancestry
of the proportional-integral-derivative controller.” Trans. of the
Newcomen Society, 59, pp. 15–29.
Stojić,M.R.andT.B.Petrović (1986):“Design ofadigitalPIDstand-
alone single-loop controller.” International Journal of Control,
43:4, pp. 1229–1242.

336 Bibliography
Strejc, V. (1959): “Näherungsverfahren für Aperiodische Übertrags-
characteristiken.” Regelungstechnik, 7:7, pp. 124–128.
Suda,N.etal.(1992):PIDControl. Asakura Shoten Co.,Ltd.,Japan.
Sugeno, M., Ed. (1985): Industrial Applications of Fuzzy Control.
Elsevier Science Publishers BV, The Netherlands.
Swiniarski, R. W. (1991): “Neuromorphic self-tuning PID controller
uses pattern recognition approach.” In Preprints IFAC Interna-
tional Symposium on Intelligent Tuning and Adaptive Control
(ITAC 91), Singapore.
Takahashi,Y.,M.J.Rabins,andD.M.Auslander (1972):Controland
Dynamic Systems. Addison-Wesley, Reading, Massachusetts.
Takatsu, H., T. Kawano, and K. ichi Kitano (1991): “Intelligent self-
tuning PID controller.” In Preprints IFAC International Sympo-
sium on Intelligent Tuning and Adaptive Control (ITAC 91), Sin-
gapore.
Tan,L.-Y.andT.W.Weber (1985):“Controller tuning ofathird-order
process under proportional-integral control.” Industrial & Engi-
neeringChemistryProcessDesignandDevelopment,24,pp.1155–
1160.
Tong, R. M. (1977): “A control engineering review of fuzzy system.”
Automatica, 13, pp. 559–569.
Tong, R. M. (1984): “A retrospective view of fuzzy control systems.”
Fuzzy Sets and Systems, 14, pp. 199–210.
Truxal, J. (1955): Automatic Feedback Control System Synthesis.
McGraw-Hill, New York.
Tucker, G. K. and D. M. Wills (1960): A Simplified Technique of
Control System Engineering. Minneapolis-Honeywell Regulator
Company, Philadelphia, Pennsylvania.
Tyreus,B.(1987):“TUNEX–anexpertsystem forcontroller tuning.”
Technical Report, du Pont.
van der Grinten, P. M. E. M. (1963a): “Determining plant controlla-
bility.” Control Engineering, October, pp. 87–89.
van der Grinten, P. M. E. M. (1963b): “Finding optimum controller
settings.” Control Engineering, December, pp. 51–56.
Voda, A. and I. D. Landau (1995): “A method for the auto-calibration
of pid controllers.” Automatica, 31:2.
Walgama, K. S. and J. Sternby (1990): “Inherent observer property
in a class of anti-windup compensators.” International Journal
of Control, 52:3, pp. 705–724.
Wang, L.-X.(1994):Adaptive Fuzzy Systemsand Control: Design and
Stability Analysis. Prentice Hall.

Bibliography 337
Webb, J. C. (1967): “Representative DDC systems.” Instruments &
Control Systems, 40, October, pp. 78–83.
Wellstead, P. E. (1979): Introduction to Physical System Modelling.
Academic Press.
Whatley,M.J.andD.C.Pott(1984):“Adaptive gainimprovesreactor
control.” Hydrocarbon Processing, May, pp. 75–78.
Willis, M. J., C. Di Massimo, G. A. Montague, M. T. Tham, and A. J.
Morris (1991): “Artificial neural networks in process engineer-
ing.” IEE Proceedings D, 138:3, pp. 256–266.
Wills,D.M.(1962a):“Aguidetocontroller tuning.” Control Engineer-
ing, August, pp. 93–95.
Wills, D. M. (1962b): “Tuning maps for three-mode controllers.” Con-
trol Engineering, April, pp. 104–108.
Wolfe, W. A. (1951):“Controller settings for optimum control.” Trans-
actions of the ASME, 64, pp. 413–418.
Wong, S. K. P. and D. E. Seborg (1988): “Control strategy for single-
input single-output non-linear systems with time delays.” Inter-
national Journal of Control, 48:6, pp. 2303–2327.
Yamamoto, S. (1991): “Industrial developments in intelligent and
adaptivecontrol.”InPreprintsIFACInternational Symposiumon
Intelligent Tuning and Adaptive Control (ITAC 91), Singapore.
Yamamoto, S. and I. Hashimoto (1991): “Present status and fu-
ture needs: The view from Japanese industry.” In Arkun and
Ray, Eds., Chemical Process Control—CPCIV. Proceedings of
the FourthInternation Conference on Chemical Process Control,
Texas.
Yarber, W. H. (1984a): “Electromax V plus, A logical progression.” In
Proceedings, Control Expo 84.
Yarber,W.H.(1984b):“Single loop,self-tuning algorithm applied.” In
Preprints AIChE Anaheim Symposium.
Yuwana, M. and D. E. Seborg (1982): “A new method for on-line
controller tuning.” AIChE Journal, 28:3, pp. 434–440.
Zadeh, L. A. (1988): “Fuzzy logic.” IEEE Computer, April, pp. 83–93.
Zervos, C., P. R. Bélanger, and G. A. Dumont (1988): “On PID con-
troller tuning using orthonormal series identification.” Automat-
ica, 24:2, pp. 165–175.
Zhang,C.andR.J.Evans(1988):“Rateconstrainedadaptivecontrol.”
International Journal of Control, 48:6, pp. 2179–2187.
Zhuang, M. and D. Atherton (1991): “Tuning PID controllers with
integral performance criteria.” In Control ’91, Heriot-Watt Uni-
versity, Edinburgh, UK.

338 Bibliography
Ziegler, J. G. and N. B. Nichols (1942): “Optimum settings for auto-
matic controllers.” Trans. ASME, 64, pp. 759–768.
Ziegler, J.G.,N.B.Nichols,andN.Y.Rochester (1943):“Processlags
in automatic-control circuits.” Trans. ASME, 65, July, pp. 433–
444.

INDEX
| Index Terms  | Links  |     |
| ------------ | ------ | --- |

| M-value  | 125  |     |
| -------- | ---- | --- |
s
| λ-tuning  | 156  | 198  |
| --------- | ---- | ---- |
A
| ABB                   | 258  |     |
| --------------------- | ---- | --- |
| Accutune              | 250  |     |
| adaptive control      | 233  |     |
| adaptive feedforward  | 249  |     |
| adaptive techniques   | 232  |     |
adaptive techniques, adaptive
|   control  | 233  |     |
| ---------- | ---- | --- |
adaptive techniques, adaptive
|   feedforward  | 249  |     |
| -------------- | ---- | --- |
adaptive techniques, automatic
|   tuning  | 230  | 234  |
| --------- | ---- | ---- |
adaptive techniques, gain
|   scheduling                  | 232  | 234  |
| ----------------------------- | ---- | ---- |
| adaptive techniques, uses of  |      | 236  |
| air-fuel ratio control        | 291  | 294  |
| Alfa Laval Automation         | 247  |      |
| aliasing                      | 94   |      |
| amplitude margin              | 125  | 126  |
| analytical tuning             | 156  |      |
This page has been reformatted by Knovel to provide easier navigation.

| Index Terms  | Links  |     |
| ------------ | ------ | --- |

| anti-windup             | 80   |      |
| ----------------------- | ---- | ---- |
| antialiasing filter     | 94   |      |
| anticipating action     | 117  |      |
| apparent dead time      | 16   |      |
| apparent time constant  | 16   |      |
| approximate models      | 51   |      |
| area methods            | 24   |      |
| auto-tuning             | 233  | 234  |
| automatic reset         | 67   | 117  |
| automatic tuning        | 230  | 234  |
| average residence time  | 13   | 27   |
| averaging control       | 132  |      |
B
| back propagation     | 298  |      |
| -------------------- | ---- | ---- |
| back-calculation     | 83   |      |
| backlash             | 264  |      |
| batch unit           | 91   |      |
| BO, modulus optimum  | 166  | 198  |
| bumpless transfer    | 103  | 105  |
| Butterworth filter   | 94   |      |
C
| cancellation of process poles  | 163  | 169  |
| ------------------------------ | ---- | ---- |
| cascade control                | 274  |      |
| cascade control, applications  | 279  |      |
cascade control, control
|   modes  | 277  |     |
| -------- | ---- | --- |
This page has been reformatted by Knovel to provide easier navigation.

| Index Terms  | Links  |     |
| ------------ | ------ | --- |

cascade control, disturbance
|   rejection              | 275  |     |
| ------------------------ | ---- | --- |
| cascade control, tuning  | 278  |     |
| cascade control, use of  | 276  |     |
| cascade control, windup  | 278  |     |
| centrifugal governor     | 117  |     |
Chien, Hrones and Reswick
|   method                  | 149  |     |
| ------------------------- | ---- | --- |
| CHR method                | 149  |     |
| Cohen-Coon method         | 180  |     |
| commercial controllers    | 108  |     |
| conditional integration   | 88   |     |
| control error             | 60   |     |
| control paradigms         | 273  |     |
| control signal overshoot  | 129  |     |
| control variable          | 5    |     |
| controllability ratio     | 16   |     |
| controller design         | 120  |     |
| controller gain K         | 61   | 64  |
| controller outputs        | 77   |     |
| crisp variable            | 298  |     |
| cut-back                  | 89   |     |
D
| D-term         | 64   |     |
| -------------- | ---- | --- |
| Dahlin method  | 198  |     |
| DCS Tuner      | 258  |     |
| dead time      | 13   |     |
This page has been reformatted by Knovel to provide easier navigation.

| Index Terms  | Links  |     |
| ------------ | ------ | --- |

| dead time, λ-tuning         | 156  |      |
| --------------------------- | ---- | ---- |
| dead time, apparent         | 16   |      |
| dead time, compensation     | 112  |      |
| dead time, normalized       | 16   |      |
| dead time, PPI controller   | 157  |      |
| dead time, Smith predictor  | 113  |      |
| decay ratio                 | 127  |      |
| defuzzification             | 301  |      |
| derivative action           | 69   | 117  |
| derivative gain limitation  | 76   |      |
  64
derivative time T d
| describing function         | 38   |     |
| --------------------------- | ---- | --- |
| diagnosis                   | 262  |     |
| digital signal processors   | 118  |     |
| direct adaptive control     | 233  |     |
| disturbance models          | 46   |     |
| disturbance rejection       | 193  |     |
| disturbance representation  | 50   |     |
| disturbances                | 53   |     |
| dominant pole design        | 179  |     |
| dominant poles              | 132  |     |
| drum level control          | 283  |     |
| dynamic model               | 8    |     |
E
| ECA400                     | 247  |     |
| -------------------------- | ---- | --- |
| error feedback             | 73   |     |
| error-squared controllers  | 77   |     |
This page has been reformatted by Knovel to provide easier navigation.

| Index Terms  | Links  |     |
| ------------ | ------ | --- |

| EXACT  | 244  |     |
| ------ | ---- | --- |
F
| feedback                       | 60   | 273  |
| ------------------------------ | ---- | ---- |
| feedforward control            | 281  |      |
| feedforward control, adaptive  | 249  |      |
| feedforward control, dynamic   | 282  |      |
| feedforward control, static    | 282  |      |
| feedforward control, tuning    | 287  |      |
| Fisher-Rosemount               | 254  |      |
| four-parameter model           | 19   |      |
| Foxboro                        | 244  |      |
| frequence curve                | 10   |      |
| frequency response             | 9    | 34   |
| friction                       | 262  |      |
| fuzzy control                  | 298  |      |
| fuzzy inference                | 300  |      |
| fuzzy logic                    | 298  |      |
G
| gain margin      | 126  |      |
| ---------------- | ---- | ---- |
| gain ratio k     | 36   |      |
| gain scheduling  | 232  | 234  |
H
| Haalmans method  | 159  |      |
| ---------------- | ---- | ---- |
| Honeywell        | 250  | 257  |
This page has been reformatted by Knovel to provide easier navigation.

| Index Terms  | Links  |     |
| ------------ | ------ | --- |

| hysteresis  | 264  |     |
| ----------- | ---- | --- |
I
| I-PD controller              | 74   |     |
| ---------------------------- | ---- | --- |
| I-term                       | 64   |     |
| IAE                          | 122  |     |
| IE                           | 122  |     |
| IMC, internal model control  | 162  |     |
| impulse                      | 47   |     |
| impulse response             | 9    | 21  |
| incremental algorithm        | 79   |     |
incremental algorithm,
|   discretization  | 99  |     |
| ----------------- | --- | --- |
incremental algorithm,
|   windup                   | 82   |      |
| -------------------------- | ---- | ---- |
| indirect adaptive control  | 233  |      |
| integral action            | 67   | 117  |
| integral time T            | 64   |      |
i
integral windup, SEE
|   WINDUP  | 80  |     |
| --------- | --- | --- |
integrated absolute error,
|   IAE                 | 122  |     |
| --------------------- | ---- | --- |
| integrated error, IE  | 122  |     |
integrated squared error,
|   ISE                | 124  |     |
| -------------------- | ---- | --- |
| integrator clamping  | 88   |     |
integrator windup, SEE
This page has been reformatted by Knovel to provide easier navigation.

Index Terms Links
integrator windup, SEE (Cont.)
WINDUP 80
interacting loops 304
interaction 309
interaction measures 312
internal model control,
IMC 162
ISE 124
ISTE 128
ITAE 128
ITE 128
ITSE 128
J
jump- and rate limiter 288
K
Kappa-Tau tuning 202
KT tuning 202
KT tuning, examples 224
KT tuning, frequency response
methods 212
KT tuning, performance
assessment 220
KT tuning, step response
methods 203
This page has been reformatted by Knovel to provide easier navigation.

| Index Terms  | Links  |     |
| ------------ | ------ | --- |

L
| lambda tuning                 | 156  | 198  |
| ----------------------------- | ---- | ---- |
| Laplace transform             | 11   |      |
| least squares                 | 44   |      |
| least squares, recursive      | 45   |      |
| limiters                      | 287  |      |
| linear time-invariant system  | 8    |      |
| load disturbances             | 54   |      |
load disturbances,
|   specifications  | 121  |     |
| ----------------- | ---- | --- |
| loop gain         | 65   |     |
| loop shaping      | 151  |     |
| Looptune          | 257  |     |
M
| manipulated variable  | 5    |      |
| --------------------- | ---- | ---- |
| maximum selector      | 292  |      |
| measurement noise     | 54   | 121  |
| median selector       | 295  |      |
| methods of moments    | 24   |      |
| minimum selector      | 292  |      |
| mode switches         | 103  |      |
| model approximation   | 55   |      |
| model following       | 284  |      |
| model uncertainty     | 121  |      |
This page has been reformatted by Knovel to provide easier navigation.

| Index Terms  | Links  |     |
| ------------ | ------ | --- |

| model-based tuning   | 237  |     |
| -------------------- | ---- | --- |
| modulus optimum, BO  | 166  |     |
N
| negative feedback  | 5    | 60  |
| ------------------ | ---- | --- |
| neural network     | 295  |     |
neural network, hidden
|   layers                  | 297  |     |
| ------------------------- | ---- | --- |
| neural network, learning  | 297  |     |
| neuron                    | 296  |     |
| noise                     | 47   |     |
| non-minimum phase         | 13   |     |
| nonlinear elements        | 287  |     |
| nonlinearities            | 52   |     |
| normalized dead time τ    | 16   |     |
| notch filter              | 113  |     |
| Nyquist curve             | 10   |     |
O
| observers                  | 280  |     |
| -------------------------- | ---- | --- |
| on-off control             | 60   |     |
| operational aspects        | 103  |     |
| optimization methods       | 164  |     |
| oscillatory systems        | 23   |     |
| overshoot                  | 127  |     |
| overshoot, control signal  | 129  |     |
This page has been reformatted by Knovel to provide easier navigation.

| Index Terms  | Links  |     |
| ------------ | ------ | --- |

P
| P-term                       | 64   |      |
| ---------------------------- | ---- | ---- |
| pairing                      | 309  |      |
| parallel systems             | 305  |      |
| parameter estimation         | 43   | 241  |
| parametric models            | 43   |      |
| phase margin                 | 126  |      |
| PI-D controller              | 74   |      |
| PID control                  | 59   | 64   |
| PID, classical form          | 73   |      |
| PID, digital implementation  | 93   |      |
| PID, discretization          | 95   |      |
| PID, ideal form              | 73   |      |
| PID, interacting form        | 71   |      |
| PID, ISA form                | 73   |      |
| PID, non-interacting form    | 71   |      |
| PID, parallel form           | 73   |      |
| PID, series form             | 73   |      |
| PID, standard form           | 73   |      |
| pole placement               | 173  |      |
| pole-zero cancellation       | 160  | 261  |
| PPI controller               | 157  |      |
| pre-act                      | 117  |      |
| predictive PI controller     | 157  |      |
| prefiltering                 | 94   |      |
| preload                      | 89   |      |
| process gain                 | 13   |      |
This page has been reformatted by Knovel to provide easier navigation.

| Index Terms  | Links  |     |
| ------------ | ------ | --- |

| process models        | 5   |      |
| --------------------- | --- | ---- |
| process noise         | 7   |      |
| process variable, PV  | 5   |      |
| process variations    | 53  |      |
| proportional action   | 64  | 117  |
| proportional band     | 61  | 87   |
| proportional control  | 61  |      |
proportional control, static
|   analysis  | 62   |     |
| ----------- | ---- | --- |
| Protuner    | 259  |     |
ProvoxTM
254
| pulse transfer function  | 43  |     |
| ------------------------ | --- | --- |
| pulse width modulation   | 78  |     |
| PV, process variable     | 5   |     |
Q
| quantization  | 100  |     |
| ------------- | ---- | --- |
R
| ramp                         | 47   |     |
| ---------------------------- | ---- | --- |
| ramp unit                    | 288  |     |
| rate limiter                 | 288  |     |
| ratio control                | 290  |     |
| ratio control, for air-fuel  | 291  |     |
| ratio controllers            | 290  |     |
| ratio PI controller          | 290  |     |
| reaction curve               | 9    |     |
This page has been reformatted by Knovel to provide easier navigation.

| Index Terms  | Links  |     |     |
| ------------ | ------ | --- | --- |

reference variable, SEE
|   SETPOINT                    | 5    |     |     |
| ----------------------------- | ---- | --- | --- |
| relative damping              | 130  |     |     |
| relative gain array           | 312  |     |     |
| relay auto-tuning             | 239  |     |     |
| relay feedback                | 37   |     |     |
| relay with hysteresis         | 39   |     |     |
| reset                         | 64   | 67  |     |
| residence time approximation  | 14   |     |     |
| response curve                | 58   |     |     |
| RGA, relative gain array      | 312  |     |     |
| rise time                     | 127  |     |     |
| robustness                    | 164  |     |     |
| Rosenbrock’s system,          | 310  |     |     |
| RPI controller                | 290  |     |     |
| RS3TM                         | 254  |     |     |
| rule-based methods            | 241  |     |     |
S
| sampling                        | 93   |      |      |
| ------------------------------- | ---- | ---- | ---- |
| selector control                | 292  |      |      |
| selector control, applications  | 294  |      |      |
| selector control, of air-fuel   | 294  |      |      |
| selector control, tuning        | 294  |      |      |
| sensitivity                     | 124  |      |      |
| sensitivity function            | 124  | 125  | 158  |
| sensitivity, maximum M          | 125  |      |      |
s
This page has been reformatted by Knovel to provide easier navigation.

| Index Terms  | Links  |     |     |
| ------------ | ------ | --- | --- |

sensitivity, to measurement
|   noise  | 124  |     |     |
| -------- | ---- | --- | --- |
sensitivity, to process
|   characteristics              | 124  |      |      |
| ------------------------------ | ---- | ---- | ---- |
| series form                    | 91   |      |      |
| setpoint limitation            | 82   |      |      |
| setpoint, following            | 53   |      |      |
| setpoint, SP                   | 5    |      |      |
| setpoint, specifications       | 121  | 126  |      |
| setpoint, weighting            | 73   | 192  |      |
| settling time                  | 127  |      |      |
| sinusoid                       | 47   |      |      |
| SLPC-181                       | 281  | 253  |      |
| Smith predictor                | 113  |      |      |
| SO, symmetrical optimum        | 166  | 198  |      |
| SP, setpoint                   | 5    |      |      |
| specifications                 | 121  |      |      |
| spectral density               | 48   |      |      |
| split range control            | 291  | 319  |      |
| state feedback                 | 281  |      |      |
| static analysis                | 62   |      |      |
| static model                   | 6    |      |      |
| static process characteristic  | 6    | 62   |      |
| steady-state error             | 64   | 66   | 127  |
| step                           | 47   |      |      |
| step response                  | 9    |      |      |
| step response models           | 11   |      |      |
| step response, integrating     | 12   |      |      |
This page has been reformatted by Knovel to provide easier navigation.

| Index Terms  | Links  |     |     |
| ------------ | ------ | --- | --- |

| step response, monotone     | 12  |     |     |
| --------------------------- | --- | --- | --- |
| step response, oscillating  | 12  |     |     |
step response, parametric
|   models                 | 53   |     |     |
| ------------------------ | ---- | --- | --- |
| stick-slip motion        | 262  |     |     |
| stiction                 | 262  |     |     |
| superposition principle  | 8    |     |     |
| surge tank control       | 289  |     |     |
| symmetrical optimum, SO  | 166  |     |     |
| system structuring       | 313  |     |     |
T
| Techmation                        | 259  |      |     |
| --------------------------------- | ---- | ---- | --- |
| three-parameter model             | 15   | 28   | 32  |
| three-position pulse output       | 101  |      |     |
| thyristors                        | 77   |      |     |
| tracking                          | 83   | 105  |     |
| tracking time constant            | 85   | 88   |     |
| transfer function                 | 11   |      |     |
| transient response                | 8    | 11   |     |
| triacs                            | 77   |      |     |
| tuning maps                       | 146  |      |     |
| two-degree-of-freedom controller  | 74   | 285  |     |
| two-parameter model               | 13   |      |     |
U
| UDC 6000            | 250  |     |     |
| ------------------- | ---- | --- | --- |
| ultimate frequency  | 10   |     |     |
This page has been reformatted by Knovel to provide easier navigation.

| Index Terms  | Links  |     |
| ------------ | ------ | --- |

| ultimate gain               | 36   |     |
| --------------------------- | ---- | --- |
| ultimate point              | 10   |     |
| undamped natural frequency  | 130  |     |
| unmodeled dynamics          | 51   |     |
V
| velocity algorithms  | 79  | 99  |
| -------------------- | --- | --- |
W
| weighted moments                 | 32   |     |
| -------------------------------- | ---- | --- |
| windup                           | 80   |     |
| windup, back-calculation         | 83   |     |
| windup, cascade control          | 278  |     |
| windup, conditional integration  | 88   |     |
| windup, incremental algorithm    | 82   |     |
| windup, selector control         | 294  |     |
| windup, setpoint limitation      | 82   |     |
| windup, tracking                 | 83   |     |
| word length                      | 100  |     |
Y
| Yokogawa  | 253  |     |
| --------- | ---- | --- |
Z
| Ziegler-Nichols methods  | 134  |     |
| ------------------------ | ---- | --- |
Ziegler-Nichols, frequency
|   response method  | 34  | 136  |
| ------------------ | --- | ---- |
This page has been reformatted by Knovel to provide easier navigation.

Index Terms Links
Ziegler-Nichols, modified 140
Ziegler-Nichols, properties 142
Ziegler-Nichols, relations 138
Ziegler-Nichols, step response
method 135
This page has been reformatted by Knovel to provide easier navigation.