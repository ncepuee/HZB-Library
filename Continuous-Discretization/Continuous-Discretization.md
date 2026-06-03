Massachusetts Institute of Technology
Department of Mechanical Engineering
2.161 Signal Processing - Continuous and Discrete
Fall Term 2008
Lecture 191
Reading:
• Proakis and Manolakis: Sec. 10.3.3
• Oppenheim, Schafer, and Buck: Sec. 7.1
1 The Design of IIR Filters (continued)
1.1 Design by the Matched z-Transform (Root Matching)
Given a prototype continuous filter H (s),
p
�
M (s − z )
H (s) = K �k=1 k
p N (s − p )
k=1 k
with zeros z , poles p , and gain K, the matched z-transform method approximates the ideal
k k
mapping
H (s) −→ H(z)|
p z=esT
by mapping the poles and zeros
�
M (z − ezk T )
H(z) = K� �k=1
N (z − epkT )
k=1
where K� must be determined from some empirical response comparison between the pro­
totype and digital filters. Note that an implicit assumption is that all s-plane poles and
zeros must lie in the primary strip in the s-plane (that is |�(s)| < π/T ). Poles/zeros on the
s-plane imaginary axis will map to the unit circle, and left-half s-plane poles and zeros will
map to the interior of the unit circle, preserving stability.
W Á
j {z }
p rim a ry s -p la n e
z -p la n e
s trip
p
j /T x
o
x o
x o s x o Â {z }
x o
o
p x
-j /T
1copyright �c D.Rowell 2008
19–1

The steps in the design procedure are:
1. Determine the poles and zeros of the prototype filter H (s).
p
2. Map the poles and zeros to the z-plane using z = esT .
3. Form the z-plane transfer function with the transformed poles/zeros.
4. Determine the gain constant K� by matching gains at some frequency (for a low-pass
filter this is normally the low frequency response).
5. Add poles or zeros at z = 0 to adjust the delay of the filter (while maintaining causal­
ity).
Example 1
Use the matched z-transform method to design a filter based on the prototype
first-order low-pass filter
a
H (s) = .
p
s + a
Solution: The prototype has a single pole at s = −a, and therefore the digital
filter will have a pole at z = e−aT . The transfer function is
1
H(z) = K� .
z − e−aT
To find K�, compare the low frequency gains of the two filters:
lim H (jΩ) = 1
p
Ω→0
K�
lim H(ejΩ) = ,
Ω→0 1 − e−aT
therefore choose K� = 1 − e−aT . Then
1 − e−aT (1 − e−aT )z−1
H(z) = =
z − e−aT 1 − e−aT z−1
and the difference equation is
y = e−aT y + (1 − e−aT )f .
n n−1 n−1
Note that this is not a minimum delay filter, because it does not use f . Therefore
n
we can optionally add a zero at the origin, and take
(1 − e−aT )z (1 − e−aT )
H(z) = =
z − e−aT 1 − e−aT z−1
as the final filter design.
19–2

5
4
3
2
1
0
0 1 2 3 4 5 6
F re q u e n c y (ra d /s )
e
d
uti
n
g
a
M
e
s
n
o
p
s
e
R y
c
n
e
u
q
er
F
Example 2
Use the matched z-transform method to design a second-order band-pass filter
based on the prototype filter
s
H (s) =
p s2 +0.2s +1
with a sampling interval T = 0.5 sec. Make frequency response plots to compare
the prototype and digital filters.
Solution: The prototype filter as a zero at s = 0, and a complex conjugate
pole pair at s = −0.1 ± j0.995, so that
z − 1
H(z) = K�
(z − e(−0.1+j0.995)T )(z − e(−0.1−j0.995)T )
z − 1
= K�
z2 − 1.6718z +0.9048
To find K�, compare the gains at Ω = 1 rad/s (the peak response of H (jΩ)),
p
|H (jΩ)| = 5
� p �Ω=1
�H(ejΩT )� = 10.54K�.
Ω=1
and to match the gains K� = 5/10.54 = 0.4612, and
0.4612(z − 1)
H(z) =
z2 − 1.6718z +0.9048
p ro to ty p e
m a tc h e d z -tra n s fro m
19–3

To create a minimum delay filter, make the order of the numerator and denomi­
nator equal by adding a zero at the origin,
|     |      |                       | 0.4612z(z − 1)  |     |     |                           | 0.4612(1 − z−1) |     |     |
| --- | ---- | --------------------- | --------------- | --- | --- | ------------------------- | --------------- | --- | --- |
|     | H(z) | =                     |                 |     | =   |                           |                 |     |     |
|     |      | z2 − 1.6718z +0.9048  |                 |     |     | 1 − 1.6718z−1 +0.9048z−2  |                 |     |     |
and implement the filter as
|     |     | y = | 1.6718y | − 0.9048y |     | +0.4612(f |     | − f ).  |     |
| --- | --- | --- | ------- | --------- | --- | --------- | --- | ------- | --- |
|     |     | n   |         | n−1       |     | n−2       |     | n  n−1  |     |
1.2  Design by the Bilinear Transform
As noted above, the ideal mapping of a prototype filter to the z-plane is
|     |     |     |     | H (s) −→ H(z)| |     |     |     |     |     |
| --- | --- | --- | --- | -------------- | --- | --- | --- | --- | --- |
p
z=esT
or
1
|     |     |     |     | s −→  |     | ln(z)  |     |     |     |
| --- | --- | --- | --- | ----- | --- | ------ | --- | --- | --- |
T
so that
|     |     |     |     | H(z) = H | p (s)| |     | .   |     |     |
| --- | --- | --- | --- | -------- | ------ | --- | --- | --- | --- |
s= 1 ln(z)
T
The Laurent series expansion for ln(z) is
|         | �     |     |          |     |          |     | �     |                   |     |
| ------- | ----- | --- | -------- | --- | -------- | --- | ----- | ----------------- | --- |
|         |       |     | �        | �   | �        | �   |       |                   |     |
|         |       |     |          | 3   |          | 5   |       |                   |     |
|         | z − 1 |     | 1  z − 1 |     | 1  z − 1 |     |       |                   |     |
| ln(z) = | 2     | +   |          | +   |          |     | +···  | for �{z} ≥ 0,z �= | 0.  |
|         | z +1  |     | 3  z +1  |     | 5  z +1  |     |       |                   |     |
The bilinear transform method uses the truncated series approximation
|     |     |     |       |          |     | �        | �   |     |     |
| --- | --- | --- | ----- | -------- | --- | -------- | --- | --- | --- |
|     |     |     |       | 1        |     | 2  z − 1 |     |     |     |
|     |     |     | s −→  | ln(z) ≈  |     |          |     |     |     |
|     |     |     |       | T        |     | T z +1   |     |     |     |
In a more general sense, any transformation of the form
|     |     |        | �     | �              |     |     |        | � �    |     |
| --- | --- | ------ | ----- | -------------- | --- | --- | ------ | ------ | --- |
|     |     |        | z − 1 |                |     |     |        | s + A  |     |
|     |     | s = A  |       | which implies  |     |     | z = −  |        |     |
|     |     |        | z +1  |                |     |     |        | s − A  |     |
is a bilinear transform.  In particular,  when A  = 2/T  the method is known as
Tustin’s method.
With this transformation the digital filter is designed from the prototype using
|     |     |     |     | H(z) = H | (s)| |             |      |     |     |
| --- | --- | --- | --- | -------- | ---- | ----------- | ---- | --- | --- |
|     |     |     |     |          | p    | s= 2 (z−1 ) |      |     |     |
|     |     |     |     |          |      | T           | z+1  |     |     |
19–4

Example 3
Find the bilinear transform equivalent of an integrator
1
|     | H (s) =  | .   |     |     |
| --- | -------- | --- | --- | --- |
p
s
Solution:
|     | � �� | �   | �       |     |
| --- | ---- | --- | ------- | --- |
|     | 1 �  | T   | 1+ z−1  |     |
�
| H(z) =  | �   | =   |          |     |
| ------- | --- | --- | -------- | --- |
|         | s   | 2   | 1 − z−1  |     |
s= 2 (z−1 )
T z+1
and the difference equation is
T
| y   | = y + | (f + f | )   |     |
| --- | ----- | ------ | --- | --- |
| n   | n−1   | n      | n−1 |     |
2
which is the classical trapezoidal (or mid-point) rule for numerical integration.
The bilinear transform maps the left half s-plane to the interior of the unit circle, and thus
preserves stability. In addition, we will see below that it maps the entire imaginary axis of
the s-plane to the unit circle, and thus avoids aliasing in the frequency response.
| jW  |     |     | Á {z } |     |
| --- | --- | --- | ------ | --- |
z -p la n e
s -p la n e
jW
p
W
|     | s   |     | T   | Â   |
| --- | --- | --- | --- | --- |
{z }
Thus every point on the frequency response of the continuous-time prototype filter, is mapped
to a corresponding point in the frequency response of the discrete-time filter, although with a
different frequency. This means that every feature in the frequency response of the prototype
filter is preserved, with identical gain and phase shift, at some frequency the digital filter.
Example 4
Find the bilinear transform equivalent of a first-order low-pass filter
a
|     | H (s) =  | .      |     |     |
| --- | -------- | ------ | --- | --- |
|     | p        | s + a  |     |     |
19–5

Solution:
� ��
a �
H(z) = �
�
s + a
s= 2 (z−1 )
T z+1
(aT/2)(z + 1)
=
(z − 1) + (aT/2)(z + 1)
(aT/2)(1 + z−1)
=
(1 + aT/2) − (1 − aT/2)z−1
and the difference equation is
1 − aT/2 aT/2
y = y + f .
n n−1 n
1+ aT/2 1+ aT/2
Comparing the frequency responses of the two filters,
�
H(ejΩT )� = 1� 0 = H (j0)
Ω=0 p
� �
π
lim H(ejΩT ) = 0� − = lim H (jΩ),
p
Ω→π/T 2 Ω→∞
demonstrating the assertion above that the entire frequency response of the pro­
totype filter has been transformed to the unit circle.
1.2.1 Frequency Warping in the Bilinear Transform
The mapping
� �
2 z − 1
s ←→
T z +1
implies that when z = ejΩT ,
� � � �
2 ejΩT − 1 2 ΩT
s = = j tan
T ejΩT +1 T 2
so that � � ��
2 ΩT
H(ejΩT ) = H j tan
p
T 2
which gives a nonlinear warping of the frequency scales in the frequency response of the two
filters.
19–6

W p
2 W T
ta n
T 2
-p /T
W
W p /T d
fre q u e n c y in d ig ita l filte r
|H (j W )|2
1
1
1 + e 2
1
1 + l 2
0
0 W c W r W ( ra d /s e c )
p a s s b a n d tra n s itio n b a n d s to p b a n d
r etlif
e
p
yt
ot
or
p
ni
y
c
n
e
u
q
erf
In particular
H(ej0) = H (j0) , and H(ej π) = H (j ∞)
p p
and there is no aliasing in the frequency response.
1.2.2 Pre-warping of Critical Frequencies in Bilinear Transform Filter Design
The specifications for a digital filter must be done in the digital domain, that is the critical
band-edge frequencies must relate to the performance of the final design - not the continuous
prototype.
Therefore, in designing the continuous prototype we need to choose band-edge frequencies
that will warp to the correct values after the bilinear transform. This procedure is known as
pre-warping. For example, if we are given a specification for a digital low-pass filter such as
19–7

| we would pre-warp the frequencies Ω | and Ω          | to  |         |      |     |
| ----------------------------------- | -------------- | --- | ------- | ---- | --- |
|                                     | c              | r   |         |      |     |
| 2                                   | Ω T            |     | 2       | Ω T  |     |
| Ω� =                                | tan  c ,  and  | Ω�  | =  tan  | r    |     |
| c  T                                | 2              | r   | T       | 2    |     |
and design the prototype to meet the specifications with Ω� and Ω�
as the band edges.
|     |     |     | c   |     | c   |
| --- | --- | --- | --- | --- | --- |
Design Procedure:  For any class of filter (band-pass, band-stop) the procedure is:
(1) Define all band-edge critical frequencies for the digital filter.
(2) Pre-warp all critical frequencies using Ω� =
(T/2)tan(ΩT/2).
(3) Design the continuous prototype using the pre-warped frequencies.
(4) Use the bilinear transform to transform H (s) to H(z).
p
(5) Realize the digital filter as a difference equation.
Example 5
Use the bilinear transform method to design a low-pass filter, with T = .01 sec.,
based on a prototype Butterworth filter to meet the following specifications.
p 2
|H (j2 F )|
1
1
e =  0 .9
1  +   2
1
=  0 .0 5
1  +   l 2
0
0
|       | 1 0                       | 2 0      |           |       | F  (H z ) |
| ----- | ------------------------- | -------- | --------- | ----- | --------- |
| p a s | s  b a n d tra n s itio n |  b a n d | s to p  b | a n d |           |
Solution:  Pre-warp the band-edges:
|       | �       | �                  |     |     |     |
| ----- | ------- | ------------------ | --- | --- | --- |
|       | 2  Ω T  |                    |     |     |     |
| Ω�    | c       |                    |     |     |     |
| =     | tan     | = 64.9839 rad/s    |     |     |     |
| c     | T  2    |                    |     |     |     |
|       | �       | �                  |     |     |     |
|       | 2  Ω T  |                    |     |     |     |
| Ω� =  | tan  r  | = 145.3085 rad/s.  |     |     |     |
r
T  2
From the specifications � = 0.3333 and λ = 4.358, and the required order for the
prototype Butterworth filter is
log(λ/�)
|     | N ≥  | = 3.1946  |     |     |     |
| --- | ---- | --------- | --- | --- | --- |
log(Ω�/Ω�)
|     | r   | c   |     |     |     |
| --- | --- | --- | --- | --- | --- |
19–8

so take N  = 4.  The four poles (p ,...,p ) lie on a circle of radius Ω��−1/N  =
|     |     | 1 4 |     |     | c   |
| --- | --- | --- | --- | --- | --- |
82.526,
|     | |p |  | =  82.526,  |     |     |     |
| --- | ----- | ----------- | --- | --- | --- |
n
|     | �  p | =  π(2n + 3)/8  |     |     |     |
| --- | ---- | --------------- | --- | --- | --- |
n
for n = 1 ... 4. The prototype transfer function is
|     | p p p | p   |     |     |     |
| --- | ----- | --- | --- | --- | --- |
|     | 1 2   | 3 4 |     |     |     |
H (s) =
| p (s − p | )(s − p )(s − p | )(s − p | )   |     |     |
| -------- | --------------- | ------- | --- | --- | --- |
|          | 1 2             | 3       | 4   |     |     |
5.3504 × 107
=  .
s4 + 223.4897s3 + 24974s2 +1.6348 × 106s +5.3504 × 107
Applying the bilinear transform
|     | H(z) | = H (s)| |     |     |     |
| --- | ---- | -------- | --- | --- | --- |
p s= 2 (z−1 )
T z+1
gives
0.0112(1 + z−1)4
H(z) =
1.0000 − 1.9105z−1 +1.6620z−2 − 0.6847z−3 +0.1128z−4
and the frequency response of the digital filter (as a power gain) is shown below:
1
2|)
F
p 0 .8
2j(
H|
e
s
n
o p 0 .6
s
e
R r
e
w 0 .4
o
P
0 .2
0
F
| 0   | 1 0 | 2 0 | 3 0  | 4 0                 | 5 0 |
| --- | --- | --- | ---- | ------------------- | --- |
|     |     |     | F re | q u e n c y  (H z ) |     |
19–9