| ELEC 6061        |         |     |          |             | Winter | 2006 |
| ---------------- | ------- | --- | -------- | ----------- | ------ | ---- |
|                  | Lecture | 6:  | Discrete | Equivalents |        |      |
| Lecturer: Peyman | Gohari  |     |          |             |        |      |
Finding the discrete equivalent of a continuous system is desired when:
1. Adiscreteequivalentofacontinuousplantisneededtosimulateasampled-datasystem.
In a sampled-data system controller is discrete while plant is continuous. To simulate
the entire system as a discrete-time system one needs to flnd the discrete equivalent of
the plant (preceded by a hold circuit, and followed by a sampler).
2. Todesignadigitalcontrollerforacontinuous-timeplantonemaystartfromscratchand
directly design a digital controller (this will be discussed in future lectures). Alterna-
tively, one may take advantage of the vast body of knowledge available on continuous-
| control design | by taking | the following | two | steps: |     |     |
| -------------- | --------- | ------------- | --- | ------ | --- | --- |
(a) Design (or have designed) a continuous-time controller for the plant. In his cal-
culations the designer should take into account the T=2 seconds delay introduced
| by sampling | and | hold. |     |     |     |     |
| ----------- | --- | ----- | --- | --- | --- | --- |
(b) Find the discrete equivalent of the above design, for implementation by a digital
computer.
| This method | of design | is called | emulation. |     |     |     |
| ----------- | --------- | --------- | ---------- | --- | --- | --- |
In this chapter three methods for flnding discrete equivalents are discussed. The flrst method
istousenumericalintegration toapproximateasystemdescribedbyasetoflineardifierential
equations. The second method uses the idea of pole-zero mapping to flnd the discrete-
time counterpart of a continuous-time transfer function. Recall that a continuous-time pole
es0T.
located at s = s corresponds to a discrete-time pole at z = Finally, we discuss
0
hold equivalents, which uses difierent extrapolation techniques to convert samples into a
| continuous-time | signal.     |     |             |     |               |       |
| --------------- | ----------- | --- | ----------- | --- | ------------- | ----- |
| 6.1 Design      | of discrete |     | equivalents |     | via numerical | inte- |
gration
To obtain the discrete equivalent of a transfer function via numerical integration, we flrst
write the system difierential equation, and then apply one of the following numerical inte-
6-1

| Lecture | 6: Discrete |       | Equivalents |         |             |     |         |     |             |     |      | 6-2 |
| ------- | ----------- | ----- | ----------- | ------- | ----------- | --- | ------- | --- | ----------- | --- | ---- | --- |
| gration | techniques  |       | introduced  | before: |             |     |         |     |             |     |      |     |
|         |             |       |             | …       | x(k+1)¡x(k) |     |         |     |             |     |      |     |
|         |             | x_(k) |             |         |             |     | Forward |     | rectangular |     | rule |     |
T
|     |     |      |     | …   | x(k+1)¡x(k) |     |          |     |             |     |      |     |
| --- | --- | ---- | --- | --- | ----------- | --- | -------- | --- | ----------- | --- | ---- | --- |
|     |     | x_(k | +1) |     |             |     | Backward |     | rectangular |     | rule |     |
T
|     |     | x_(k)+x_(k+1) |     | …   | x(k+1)¡x(k) |     |           |     |      |     |     |     |
| --- | --- | ------------- | --- | --- | ----------- | --- | --------- | --- | ---- | --- | --- | --- |
|     |     |               |     |     |             |     | Trapezoid |     | rule |     |     |     |
|     |     |               | 2   |     |             | T   |           |     |      |     |     |     |
The operation can be carried out directly on transfer function if one translates the above
equations into frequency domain. In our translation, each discrete-time left-shift by n cor-
dn
responds to a zn multiplying factor in z-domain, and each in continuous-time domain
dtn
sn
corresponds to an multiplying factor in Laplace domain. Thus we have:
|     |     |     | s   | ˆ¡  | z¡1 | Forward |     | rectangular |     | rule |     |     |
| --- | --- | --- | --- | --- | --- | ------- | --- | ----------- | --- | ---- | --- | --- |
z¡1 T
|     |     |     | sz  | ˆ¡  |     | Backward |     | rectangular |     |     | rule |     |
| --- | --- | --- | --- | --- | --- | -------- | --- | ----------- | --- | --- | ---- | --- |
z¡1 T
|                  |     |     | s+sz | ˆ¡  |     | Trapezoid |     | rule        |     |      |     |     |
| ---------------- | --- | --- | ---- | --- | --- | --------- | --- | ----------- | --- | ---- | --- | --- |
|                  |     |     | 2    |     | T   |           |     |             |     |      |     |     |
| which simplifles |     | to: |      |     |     |           |     |             |     |      |     |     |
|                  |     |     |      | ˆ¡  | z¡1 |           |     |             |     |      |     |     |
|                  |     |     | s    |     |     | Forward   |     | rectangular |     | rule |     |     |
T
|     |     |     |     | ˆ¡  | z¡1 |          |     |             |     |      |     |     |
| --- | --- | --- | --- | --- | --- | -------- | --- | ----------- | --- | ---- | --- | --- |
|     |     |     | s   |     |     | Backward |     | rectangular |     | rule |     |     |
Tz
|     |     |     |     | ˆ¡  | 2 z¡1 |           |     |      |     |     |     |     |
| --- | --- | --- | --- | --- | ----- | --------- | --- | ---- | --- | --- | --- | --- |
|     |     |     | s   |     |       | Trapezoid |     | rule |     |     |     |     |
T z+1
The trapezoid rule is also called Tustin’s method in digital control community.
Each of the above relations can be viewed as a map from z-plane to s-plane1. Since we
are more familiar with s-plane characteristics, it would be useful to flnd the inverse of each
| transformation |     | as a | map from | s-plane |     | to z-plane: |     |             |     |      |     |     |
| -------------- | --- | ---- | -------- | ------- | --- | ----------- | --- | ----------- | --- | ---- | --- | --- |
|                |     |      | z =      | sT +1   |     | Forward     |     | rectangular |     | rule |     |     |
1
|     |     |     | z = |     |     | Backward |     | rectangular |     | rule |     |     |
| --- | --- | --- | --- | --- | --- | -------- | --- | ----------- | --- | ---- | --- | --- |
1¡Ts
1+Ts=2
|     |     |     | z = |     |     | Trapezoid |     | rule |     |     |     |     |
| --- | --- | --- | --- | --- | --- | --------- | --- | ---- | --- | --- | --- | --- |
1¡Ts=2
It is interesting to see how the stable region of s-plane (that is, the right-half plane described
by Re(s) > 0) is mapped to z-plane. As illustrated in Figure 6.1, under trapezoid rule the
stable region of s-plane is mapped exactly to the stable region of z-plane. This and other
| observations | are | summarized |     | below. |     |     |     |     |     |     |     |     |
| ------------ | --- | ---------- | --- | ------ | --- | --- | --- | --- | --- | --- | --- | --- |
1 Under trapezoid rule, the discrete-time system is stable if and only if the continuous-time
| system | is  | stable. |     |     |     |     |     |     |     |     |     |     |
| ------ | --- | ------- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
2 Underbackwardrectangularrule, thediscrete-timesystemisstableif thecontinuous-time
| system | is            | stable. |           |          |     |                 |     |     |     |     |     |     |
| ------ | ------------- | ------- | --------- | -------- | --- | --------------- | --- | --- | --- | --- | --- | --- |
|        |               |         |           | bilinear |     | transformation. |     |     |     |     |     |     |
| 1The   | third mapping |         | is called | a        |     |                 |     |     |     |     |     |     |

| Lecture | 6:  | Discrete | Equivalents |     |     |     |     |      |     | 6-3 |
| ------- | --- | -------- | ----------- | --- | --- | --- | --- | ---- | --- | --- |
| 3       |     |          |             |     |     |     |     | only | if  |     |
Under forward rectangular rule, the discrete-time system is stable the continuous-
|     | time                                                                     | system                                                    | is stable.                                                                                            |     |     |                                                                          |                |                                                                                        |                                                                          |     |
| --- | ------------------------------------------------------------------------ | --------------------------------------------------------- | ----------------------------------------------------------------------------------------------------- | --- | --- | ------------------------------------------------------------------------ | -------------- | -------------------------------------------------------------------------------------- | ------------------------------------------------------------------------ | --- |
|     | (cid:5)(cid:1) (cid:5)(cid:1)(cid:6)(cid:1) (cid:5)(cid:1)(cid:6)(cid:1) | (cid:5)(cid:1)(cid:6)(cid:1) (cid:5)(cid:1)(cid:6)(cid:1) | (cid:5)(cid:1)(cid:6)(cid:1) (cid:5)(cid:1)(cid:6)(cid:1) (cid:5)(cid:1)(cid:6)(cid:1) (cid:5)(cid:6) |     |     |                                                                          |                |                                                                                        |                                                                          |     |
|     | (cid:5)(cid:1) (cid:5)(cid:1)(cid:6)(cid:1) (cid:5)(cid:1)(cid:6)(cid:1) | (cid:5)(cid:1)(cid:6)(cid:1) (cid:5)(cid:1)(cid:6)(cid:1) | (cid:5)(cid:1)(cid:6)(cid:1) (cid:5)(cid:1)(cid:6)(cid:1) (cid:5)(cid:1)(cid:6)(cid:1) (cid:5)(cid:6) |     |     |                                                                          |                |                                                                                        |                                                                          |     |
|     |                                                                          |                                                           |                                                                                                       |     |     |                                                                          | (cid:0)(cid:1) | (cid:0)(cid:1)(cid:2)(cid:1) (cid:0)(cid:1)(cid:2)(cid:1) (cid:0)(cid:1)(cid:2)(cid:1) | (cid:0)(cid:1)(cid:2)(cid:1) (cid:0)(cid:1)(cid:2)(cid:1) (cid:0)(cid:2) |     |
|     | (cid:5)(cid:1) (cid:5)(cid:1)(cid:6)(cid:1) (cid:5)(cid:1)(cid:6)(cid:1) | (cid:5)(cid:1)(cid:6)(cid:1) (cid:5)(cid:1)(cid:6)(cid:1) | (cid:5)(cid:1)(cid:6)(cid:1) (cid:5)(cid:1)(cid:6)(cid:1) (cid:5)(cid:1)(cid:6)(cid:1) (cid:5)(cid:6) |     |     |                                                                          |                |                                                                                        |                                                                          |     |
|     |                                                                          |                                                           |                                                                                                       |     |     |                                                                          | (cid:0)(cid:1) | (cid:0)(cid:1)(cid:2)(cid:1) (cid:0)(cid:1)(cid:2)(cid:1) (cid:0)(cid:1)(cid:2)(cid:1) | (cid:0)(cid:1)(cid:2)(cid:1) (cid:0)(cid:1)(cid:2)(cid:1) (cid:0)(cid:2) |     |
|     | (cid:5)(cid:1) (cid:5)(cid:1)(cid:6)(cid:1) (cid:5)(cid:1)(cid:6)(cid:1) | (cid:5)(cid:1)(cid:6)(cid:1) (cid:5)(cid:1)(cid:6)(cid:1) | (cid:5)(cid:1)(cid:6)(cid:1) (cid:5)(cid:1)(cid:6)(cid:1) (cid:5)(cid:1)(cid:6)(cid:1) (cid:5)(cid:6) |     |     | (cid:3)(cid:1)(cid:4)(cid:1) (cid:3)(cid:1)(cid:4)(cid:1) (cid:3)(cid:4) |                |                                                                                        |                                                                          |     |
|     |                                                                          |                                                           |                                                                                                       |     |     |                                                                          | (cid:0)(cid:1) | (cid:0)(cid:1)(cid:2)(cid:1) (cid:0)(cid:1)(cid:2)(cid:1) (cid:0)(cid:1)(cid:2)(cid:1) | (cid:0)(cid:1)(cid:2)(cid:1) (cid:0)(cid:1)(cid:2)(cid:1) (cid:0)(cid:2) |     |
|     | (cid:5)(cid:1) (cid:5)(cid:1)(cid:6)(cid:1) (cid:5)(cid:1)(cid:6)(cid:1) | (cid:5)(cid:1)(cid:6)(cid:1) (cid:5)(cid:1)(cid:6)(cid:1) | (cid:5)(cid:1)(cid:6)(cid:1) (cid:5)(cid:1)(cid:6)(cid:1) (cid:5)(cid:1)(cid:6)(cid:1) (cid:5)(cid:6) |     |     | (cid:3)(cid:1)(cid:4)(cid:1) (cid:3)(cid:1)(cid:4)(cid:1) (cid:3)(cid:4) |                |                                                                                        |                                                                          |     |
(cid:5)(cid:1) (cid:5)(cid:1)(cid:6)(cid:1) (cid:5)(cid:1)(cid:6)(cid:1) (cid:5)(cid:1)(cid:6)(cid:1) (cid:5)(cid:1)(cid:6)(cid:1) (cid:5)(cid:1)(cid:6)(cid:1) (cid:5)(cid:1)(cid:6)(cid:1) (cid:5)(cid:1)(cid:6)(cid:1) (cid:5)(cid:6) (cid:0)(cid:1) (cid:0)(cid:1)(cid:2)(cid:1) (cid:0)(cid:1)(cid:2)(cid:1) (cid:0)(cid:1)(cid:2)(cid:1) (cid:0)(cid:1)(cid:2)(cid:1) (cid:0)(cid:1)(cid:2)(cid:1) (cid:0)(cid:2)
|     |     |     |     |     |     | (cid:3)(cid:1)(cid:4)(cid:1) (cid:3)(cid:1)(cid:4)(cid:1) (cid:3)(cid:4) |     |     |     |     |
| --- | --- | --- | --- | --- | --- | ------------------------------------------------------------------------ | --- | --- | --- | --- |
(cid:5)(cid:1) (cid:5)(cid:1)(cid:6)(cid:1) (cid:5)(cid:1)(cid:6)(cid:1) (cid:5)(cid:1)(cid:6)(cid:1) (cid:5)(cid:1)(cid:6)(cid:1) (cid:5)(cid:1)(cid:6)(cid:1) (cid:5)(cid:1)(cid:6)(cid:1) (cid:5)(cid:1)(cid:6)(cid:1) (cid:5)(cid:6) (cid:0)(cid:1) (cid:0)(cid:1)(cid:2)(cid:1) (cid:0)(cid:1)(cid:2)(cid:1) (cid:0)(cid:1)(cid:2)(cid:1) (cid:0)(cid:1)(cid:2)(cid:1) (cid:0)(cid:1)(cid:2)(cid:1) (cid:0)(cid:2)
(cid:5)(cid:1) (cid:5)(cid:1)(cid:6)(cid:1) (cid:5)(cid:1)(cid:6)(cid:1) (cid:5)(cid:1)(cid:6)(cid:1) (cid:5)(cid:1)(cid:6)(cid:1) (cid:5)(cid:1)(cid:6)(cid:1) (cid:5)(cid:1)(cid:6)(cid:1) (cid:5)(cid:1)(cid:6)(cid:1) (cid:5)(cid:6) (cid:0)(cid:1) (cid:0)(cid:1)(cid:2)(cid:1) (cid:0)(cid:1)(cid:2)(cid:1) (cid:0)(cid:1)(cid:2)(cid:1) (cid:0)(cid:1)(cid:2)(cid:1) (cid:0)(cid:1)(cid:2)(cid:1) (cid:0)(cid:2)
|     | (cid:5)(cid:1) (cid:5)(cid:1)(cid:6)(cid:1) (cid:5)(cid:1)(cid:6)(cid:1) | (cid:5)(cid:1)(cid:6)(cid:1) (cid:5)(cid:1)(cid:6)(cid:1) | (cid:5)(cid:1)(cid:6)(cid:1) (cid:5)(cid:1)(cid:6)(cid:1) (cid:5)(cid:1)(cid:6)(cid:1) (cid:5)(cid:6) |     |     |     |     |     |     |     |
| --- | ------------------------------------------------------------------------ | --------------------------------------------------------- | ----------------------------------------------------------------------------------------------------- | --- | --- | --- | --- | --- | --- | --- |
|     | (cid:5)(cid:1) (cid:5)(cid:1)(cid:6)(cid:1) (cid:5)(cid:1)(cid:6)(cid:1) | (cid:5)(cid:1)(cid:6)(cid:1) (cid:5)(cid:1)(cid:6)(cid:1) | (cid:5)(cid:1)(cid:6)(cid:1) (cid:5)(cid:1)(cid:6)(cid:1) (cid:5)(cid:1)(cid:6)(cid:1) (cid:5)(cid:6) |     |     |     |     |     |     |     |
Discrete =) Continuous Discrete (= Continuous Discrete () Continuous
|     | stable                   |     | stable | stable                     |     | stable | stable |     | stable |     |
| --- | ------------------------ | --- | ------ | -------------------------- | --- | ------ | ------ | --- | ------ | --- |
|     | Canhavecontinuousstable, |     |        | Canhavecontinuousunstable, |     |        |        |     |        |     |
|     | discreteunstable.        |     |        | discretestable.            |     |        |        |     |        |     |
|     |                          | (a) |        |                            | (b) |        |        | (c) |        |     |
Figure 6.1: The image of the stable region of s-plane under three transformations: (a)
| forward | rectangular, |     | (b) backward | rectangular, |     | and (c) | bilinear. |     |     |     |
| ------- | ------------ | --- | ------------ | ------------ | --- | ------- | --------- | --- | --- | --- |
Despitethecongruenceofstabilityunderthetrapezoidrule, theschemesufiersfromaserious
drawback: the entire imaginary axis is mapped to only 2…-length of the unit circle! This
is a great amount of distortion, which is overcome by introducing an extension of Tustin’s
rule. The approach is called bilinear with prewarping. The idea is to ensure that at a pre-
specifled frequency, discrete-time transfer function has exactly the same characteristics (gain
and phase) as the corresponding continuous-time transfer function. The transformation is
bilinear like Tustin’s, however the constant coe–cient (which used to be 2) is difierent:
T
¡1
|     |     |     |     |     | !     | z        |     |     |     |     |
| --- | --- | --- | --- | --- | ----- | -------- | --- | --- | --- | --- |
|     |     |     |     | s = |       | 0        |     |     |     |     |
|     |     |     |     |     | tan(! | T=2)z +1 |     |     |     |     |
0
Thus, denoting the discrete equivalent of H(s) by H (z) (for bilinear with prewarping), the
BP
relation between the continuous- and discrete-time transfer functions is:
|     |     |     |     | H (z) = | H(s) |       |     |     |     |     |
| --- | --- | --- | --- | ------- | ---- | ----- | --- | --- | --- | --- |
|     |     |     |     | BP      |      | fl !0 | z¡1 |     |     |     |
fl s =
tan(!0T=2)z+1
fl

| Lecture | 6: Discrete Equivalents |     |     |     | 6-4 |
| ------- | ----------------------- | --- | --- | --- | --- |
Now suppose a sinusoid at the continuous frequency of s = j! , which corresponds to the
0
discrete frequency of z = ej!0T, is applied to the systems. We have:
|     |     |     | ! ej!0T | ¡1  |     |
| --- | --- | --- | ------- | --- | --- |
0
|     | H   | (ej!0T) = H( |     | )   |     |
| --- | --- | ------------ | --- | --- | --- |
BP
|     |     |     | tan(! T=2)ej!0T | +1  |     |
| --- | --- | --- | --------------- | --- | --- |
0
¡j!0T=2
|     |     |     | ! ej!0T=2 | ¡e  |     |
| --- | --- | --- | --------- | --- | --- |
0
= H( )
|     |     |     | tan(! T=2) ej!0T=2 | +ej!0T=2 |     |
| --- | --- | --- | ------------------ | -------- | --- |
0
|     |     |      | ! 2sin(!          | T=2) |     |
| --- | --- | ---- | ----------------- | ---- | --- |
|     |     | = H( | 0 j               | 0    |     |
|     |     |      | tan(! T=2) 2cos(! | T=2) |     |
|     |     |      | 0                 | 0    |     |
= H(j! )
0
That is, a sinusoid at frequency ! experience the same transfer function in both continuous
0
| and discrete | domains. |     |     |     |     |
| ------------ | -------- | --- | --- | --- | --- |
Example 1 A third-order low-pass Butterworth fllter is described by
1
|     |     | H(s) | =   |     |     |
| --- | --- | ---- | --- | --- | --- |
s3 +2s2 +2s+1
The discrete equivalent of the fllter is calculated using forward rectangular rule, backward
rectangular rule, Tustin’s bilinear rule, and bilinear rule with prewarping at ! = 1, at
sampling rates f = 10; 1; 0:5 Hertz (Figure 6.4). Observe that at the high sampling rate of
s
f = 10 Hertz (60 times the bandwidth) all discrete approximations perform equally well. At
s
the slow rate of f = 1 Hertz, the forward rule results in an unstable discrete-time system.
s
(Recall that according to Figure 6.1 in this case it is possible for the discrete equivalent
of a continuous-time, stable system to be unstable.) At the very slow rate of f = 0:5Hz,
s
although all techniques are inaccurate, bilinear rule with prewarping has the advantage of
generating the same magnitude and phase at the cutofi frequency, which was selected as the
| prewarping | frequency. |     |     |     |     |
| ---------- | ---------- | --- | --- | --- | --- |
2
| 6.2 | Zero-pole | matching | equivalents |     |     |
| --- | --------- | -------- | ----------- | --- | --- |
As we saw before a pole s of the Laplace transform of a continuous-time signal is related to
0
a pole z of the z-transform of signal samples according to z = es0T. The idea of zero-pole
|     | 0   |     |     | 0   |     |
| --- | --- | --- | --- | --- | --- |
matching is to use this mapping to determine the location of zeros as well. The procedure
| is outlined | below. |     |     |     |     |
| ----------- | ------ | --- | --- | --- | --- |
1. A continuous-time pole at s = s is mapped to a discrete-time pole at z = es0T.
0

| Lecture | 6: Discrete | Equivalents |     |     | 6-5 |
| ------- | ----------- | ----------- | --- | --- | --- |
es0T.
2. A continuous-time, flnite, zero at s = s is mapped to a discrete-time zero at z =
0
3. Let m and n be the degree of numerator and denominator of a continuous-time transfer
function. If m < n, then the system will have n¡m zeros at inflnity. Each continuous-
1 ¡1.
time zero at s = is mapped to a discrete-time zero at z = The rationale is that
j1
we would like the highest continuous-time frequency of s = to correspond to the
|         |               |           | of2 | ej … T ¡1. |     |
| ------- | ------------- | --------- | --- | ---------- | --- |
| highest | discrete-time | frequency | z   | = T =      |     |
4. Finally, we adjust gain of the discrete equivalent by making continuous-time and
discrete-time systems gains equal at a pre-specifled frequency, in other words, we de-
| mand | the following | equality: |     |     |     |
| ---- | ------------- | --------- | --- | --- | --- |
(ej!0T)
|     |     |     | H   | = H(j! ) |     |
| --- | --- | --- | --- | -------- | --- |
zp 0
Often in practice we require the DC gains to be equal, that is, ! = 0, in which case
0
| we  | must have: |     |     |            |     |
| --- | ---------- | --- | --- | ---------- | --- |
|     |            |     | H   | (1) = H(0) |     |
zp
| Exercise | 1 Compute | the discrete | equivalent | to  |     |
| -------- | --------- | ------------ | ---------- | --- | --- |
a
|     |     |     | H(s) | =   |     |
| --- | --- | --- | ---- | --- | --- |
s+a
by zero-pole matching such that the DC gains of discrete equivalent and original system are
equal.
Answer:
1¡e ¡aT
|     |     |     | H (z) | =       |     |
| --- | --- | --- | ----- | ------- | --- |
|     |     |     | zp    | z ¡e¡aT |     |
2
| 6.3 | Hold equivalents |     |     |     |     |
| --- | ---------------- | --- | --- | --- | --- |
In the flnal method of computing a discrete equivalent for a continuous-time system, we
assume that the system is part of a digital loop, and as such is preceded by a hold cir-
cuit and is followed by a sampler (Figure 6.2). It is then desired to flnd the discrete-time
transfer function from input samples e(k) to output samples u(k), which will be a discrete
approximation to the continuous-time transfer function from continuous-time input e(t) to
| continuous-time | output | u(t). |     |     |     |
| --------------- | ------ | ----- | --- | --- | --- |
Naturally the quality of approximation depends on the method used for extrapolating sam-
ples.
2If
it is desired to have a delay of one sampling period (for example, to allow enough time for the
computation of output) then one of the continuous-time zeros at s = 1 should be mapped to a discrete-
time zero at z = 1. Note that in this case after dividing numerator by denominator we would have
H(z)=Az¡1+Bz¡2+¢¢¢, z¡1.
|     |     | which gives | us the desired | unit delay of |     |
| --- | --- | ----------- | -------------- | ------------- | --- |

| Lecture | 6: Discrete | Equivalents |     |     |     | 6-6 |
| ------- | ----------- | ----------- | --- | --- | --- | --- |
H (z)
h0
|     |     | e(k) | e(t) | u(t) | u(k) |     |
| --- | --- | ---- | ---- | ---- | ---- | --- |
D/A
H(s)
|     |     |     | &   |     | Sampler |     |
| --- | --- | --- | --- | --- | ------- | --- |
hold
|       |            |      | Figure 6.2: | Hold equivalent. |     |     |
| ----- | ---------- | ---- | ----------- | ---------------- | --- | --- |
| 6.3.1 | Zero-order | hold | equivalent  |                  |     |     |
In the simplest extrapolation method introduced earlier, samples are held constant until the
next sampling instant. We found that in this case the discrete equivalent can be calculated
| using the | following | formula: |     |     |     |     |
| --------- | --------- | -------- | --- | --- | --- | --- |
H(s)
|     |     |     |     | (1¡z ¡1)Z |     |     |
| --- | --- | --- | --- | --------- | --- | --- |
H (z) =
|     |     |     | h0  |     | n o |     |
| --- | --- | --- | --- | --- | --- | --- |
s
| Exercise | 2 Compute | zero-order-hold | equivalent | to  |     |     |
| -------- | --------- | --------------- | ---------- | --- | --- | --- |
a
|     |     |     | H(s) | =   |     |     |
| --- | --- | --- | ---- | --- | --- | --- |
s+a
Answer:
1¡e ¡aT
|     |     |     | H (z) | =       |     |     |
| --- | --- | --- | ----- | ------- | --- | --- |
|     |     |     | zp    | z ¡e¡aT |     |     |
Note that incidentally the answer is the same as previous exercise where pole-zero matching
| was used; | however, | this is not     | true in general. |     |     | 2   |
| --------- | -------- | --------------- | ---------------- | --- | --- | --- |
| 6.3.2     | Triangle | hold equivalent |                  |     |     |     |
We now consider a flrst-order hold, which extrapolates samples by connecting them using
straight lines. The impulse response of a flrst-order hold is shown in Figure 6.3. As evident
from the flgure, a flrst-order hold is noncausal, but this does not cause any problem as the
| resulting | discrete-equivalent | is  | in fact causal. |     |     |     |
| --------- | ------------------- | --- | --------------- | --- | --- | --- |
The derivation of flrst-order and zero-order equivalents are similar (the latter was carried out
in Section 4, Lecture 3; the former is left as an exercise). The flrst-order equivalent H (z)
tri
| of a continuous-time |     | transfer | function H(s) | is:     |      |     |
| -------------------- | --- | -------- | ------------- | ------- | ---- | --- |
|                      |     |          |               | (z ¡1)2 | H(s) |     |
Z
H (z) =
|     |     |     | tri | Tz  | n s2 o |     |
| --- | --- | --- | --- | --- | ------ | --- |

| Lecture | 6: Discrete Equivalents |     |     |     |     |     | 6-7 |
| ------- | ----------------------- | --- | --- | --- | --- | --- | --- |
1
¡T
T
|     | Figure 6.3: | The impulse | response | of a triangle | (flrst-order) | hold. |     |
| --- | ----------- | ----------- | -------- | ------------- | ------------- | ----- | --- |
In MATLAB, the statement sysD=c2d(sys,T,parameter) computes the discrete equivalent
sysD of a continuous-time system sys when the sampling period is T, using the method
specifled by parameter: ’tustin’ for Tustin’s, ’prewarp’ for bilinear with prewarping,
’matched’ for pole-zero matching, ’zoh’ for zero-order hold, and flnally ’foh’ for flrst-
| order (triangular) | hold. |     |     |     |     |     |     |
| ------------------ | ----- | --- | --- | --- | --- | --- | --- |
Example 2 Figure6.5comparesdiscreteequivalentsofaButterworthflltercalculatedusing
pole-zero matching, zero-order hold and flrst-order (triangular) hold, when sampling rates
are f = 1 and f = 0:5 Hertz. Observe that even at the very low sampling rate of f = 0:5
| s   | s   |     |     |     |     |     | s   |
| --- | --- | --- | --- | --- | --- | --- | --- |
2
| Hz the | triangular equivalent | shows | a very good | phase response. |     |     |     |
| ------ | --------------------- | ----- | ----------- | --------------- | --- | --- | --- |

Lecture 6: Discrete Equivalents 6-8
Fig. 6.4a Magnitude and phase of discrete equivalents
1.4
1.2
1
0.8
0.6
0.4
0.2
0
0 0.5 1 1.5 2 2.5
bilinr = o,warp = +, backwd = *, forwd = x
0
−50
−100
−150
−200
−250
0 0.5 1 1.5 2 2.5
normalized frequency w/wp
Fig. 6.4b Magnitude and phase of discrete equivalents
1
0.8
0.6
0.4
0.2
0
0 0.5 1 1.5 2 2.5
bilinr = o,warp = +, backwd = *, forwd = x
0
−50
−100
−150
−200
−250
0 0.5 1 1.5 2 2.5
normalized frequency w/wp

Lecture 6: Discrete Equivalents 6-9
Fig. 6.4c Magnitude and phase of discrete equivalents
1
0.8
0.6
0.4
0.2
0
0 0.5 1 1.5 2 2.5
bilinr = o,warp = +, backwd = *, forwd = x
0
−50
−100
−150
−200
−250
0 0.5 1 1.5 2 2.5
normalized frequency w/wp
Figure 6.4: Numerical integration of a third-order low-path Butterworth fllter using forward
rectangular rule, backward rectangular rule, Tustin’s bilinear rule, and bilinear rule with
prewarping at ! = 1, at sampling rates a) f = 10, b) f = 1, and c) f(s) = 0:5 Hertz.
s s

Lecture 6: Discrete Equivalents 6-10
Fig. 6.9a (zoh = o, zero−pole = + ,triangle = x)
1
0.8
0.6
0.4
0.2
0
0 0.5 1 1.5 2 2.5
0
−50
−100
−150
−200
−250
−300
−350
0 0.5 1 1.5 2 2.5
normalized frequency w/wp
Fig. 6.9b (zoh = o, zero−pole = + ,triangle = x)
1
0.8
0.6
0.4
0.2
0
0 0.5 1 1.5 2 2.5
0
−100
−200
−300
−400
−500
−600
−700
0 0.5 1 1.5 2 2.5
normalized frequency w/wp
Figure6.5: Comparingtheperformanceofpole-zeromatching,zero-orderholdandtriangular
hold, when sampling rate is a) f = 1, and b) f = 0:5 Hertz.
s s