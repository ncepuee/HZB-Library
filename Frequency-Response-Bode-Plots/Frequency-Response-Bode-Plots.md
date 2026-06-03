1
  Frequency Response
and Bode Plots

1.1  Preliminaries
The steady-state sinusoidal frequency-response of a circuit is described by the phasor transfer
function  H(j).  A Bode plot is a graph of the magnitude (in dB) or phase of the transfer
function versus frequency.  Of course we can easily program the transfer function into a
computer to make such plots, and for very complicated transfer functions this may be our
only recourse.  But in many cases the key features of the plot can be quickly sketched by
hand using some simple rules that identify the impact of the poles and zeroes in shaping the
frequency response.  The advantage of this approach is the insight it provides on how the
circuit elements influence the frequency response.  This is especially important in the design
of frequency-selective circuits.  We will first consider how to generate Bode plots for simple
poles, and then discuss how to handle the general second-order response.  Before doing this,
however, it may be helpful to review some properties of transfer functions, the decibel scale,
and properties of the log function.
Poles, Zeroes, and Stability
The s-domain transfer function is always a rational polynomial function of the form
|     |        | N(s) | sm a sm1a | sm2 a sa |     |        |
| --- | ------ | ---- | ------------ | ------------ | --- | ------ |
|     |        |      | m1          | m2 1        | 0   |        |
|     | H(s)K | K   |              |              |     | (1.1)  |
|     |        | D(s) | sn sn1b    | sn2         |     |        |
|     |        |      | b           | bsb       |     |        |
|     |        |      | n1          | n2 1        | 0   |        |
As we have seen already, the polynomials in the numerator and denominator are factored to
find the poles and zeroes; these are the values of s that make the numerator or denominator
zero.  If we write the zeroes as z ,z ,z etc., and similarly write the poles as  p ,p ,p ,
|     |     | 1 2 | 3   |     | 1   | 2 3 |
| --- | --- | --- | --- | --- | --- | --- |
then H(s) can be written in factored form as
|     |     |        | (sz )(sz )(sz  | )   |                  |        |
| --- | --- | ------ | ------------------ | --- | ---------------- | ------ |
|     |     | H(s)K | 1 2                | m   |                  | (1.2)  |
|     |     |        | (s p )(s p )(s | p ) |                  |        |
|     |     |        | 1 2                | n   |                  |        |
|     |     |        | 1                  |     | © Bob York 2009  |        |

| 2   |     |     |     |     |     |     | Frequency Response and Bode Plots  |     |     |     |
| --- | --- | --- | --- | --- | --- | --- | ---------------------------------- | --- | --- | --- |

The pole and zero locations can be real or complex.  When the roots are real they are called
simple poles or simple zeros.  When the roots are complex they always occur in pairs that are
complex conjugates of each other.
Another important observation is that stable networks must always have poles and zeroes
in the left-half of the complex s-plane, such that the real parts of the poles/zeroes will be
negative. As an example, lets assume a stable network with simple poles at  p 1 and
1
p 10.  The transfer function would then be
2
|     |     |     |       | 1          |     |               | 1   |     |     |        |
| --- | --- | --- | ----- | ---------- | --- | ------------- | --- | --- | --- | ------ |
|     |     |     | H(s) |            |     |              |     |     |     | (1.3)  |
|     |     |     |       | (s p )(s | p   | ) (s1)(s10) |     |     |     |        |
|     |     |     |       | 1          | 2   |               |     |     |     |        |
Thus for stable networks we always will find terms of the form (sa) in the denominator,
where  a is a positive number.  Students sometimes get confused by the use of  (s p) or
(sa) to represent the same pole location; just remember that the poles are the values of s
that make the denominator zero, i.e.  s p or  sa in this example; clearly these will
represent  the  same  pole  if  pa,  and  will  represent  a  stable  pole  if  Re{a}0  or
Re{p}0.
When there are multiple roots at the same location the denominator will contain factors of
the form (sa)r, where r is an integer that tells us how many times the root is repeated. For
example, a critically-damped second-order response would have r2.
 When the stable network includes a complex-conjugate pole pair, we can represent the
pole locations as s j where  and  are both positive real numbers. The transfer
function will then have a factor of the form
|         |         |     | 1           |      |     |            | 1   |            | 1   |          |
| ------- | ------- | --- | ----------- | ---- | --- | ---------- | --- | ---------- | --- | -------- |
|   H(s) |         |     |             |      |    |            |     |           |     |   (1.4)  |
|         | s( |     | j)s( | j) |     | s2 2s2 |     | 2 (s)2 | 2 |          |
and thus all the coefficients in the denominator are positive, even though the roots in fact
have negative real parts.    For reasons which will become clear later it is more convenient to
write the second-order polynomial in the “standard form”
|     |     |     |     | s2 2s2  |     |     |     |     |     | (1.5)  |
| --- | --- | --- | --- | ------------ | --- | --- | --- | --- | --- | ------ |
|     |     |     |     |              | n   | n   |     |     |     |        |
where   is called the corner frequency or break point, and  is called the damping factor.
n
Comparing (1.4) and (1.5) we can relate the corner frequency and damping factor to the poles
using
|     |     |    |  2 2 |     | / | / | 2  | 2   |     | (1.6)  |
| --- | --- | --- | -------- | --- | ----- | --- | --- | ----- | --- | ------ |
|     |     | n   |          |     |       | n   |     |       |     |        |
Decibel Scale and Log Functions
Logarithmic  scales  are  useful  when  plotting  functions  that  vary  over  many  orders  of
magnitude.  This is certainly the case with electrical signals; for example, the signal received
by your cell phone is often more than 12 orders of magnitude lower in power than the signal
transmitted from the base station! In a filter circuit, the magnitude of the transfer function in
the passband may be several orders of magnitude larger than it is in the stop band. We are
also interested in the frequency response of circuits over a wide range of frequencies, so it
makes sense to use a logarithmic scale for frequencies as well as signal intensity.   Electrical
engineers use the base-ten logarithm function and denote that as “log”, reserving “ln” for the
natural log function (base e), such that
|     |     |     | logxlog | x   |     | lnxlog |     | x   |     | (1.7)  |
| --- | --- | --- | -------- | --- | --- | ------- | --- | --- | --- | ------ |
|     |     |     |          | 10  |     |         |     | e   |     |        |
© Bob York 2009

| Preliminaries  |     |     |     |     | 3   |
| -------------- | --- | --- | --- | --- | --- |

This notation is not universal; some computer math programs (such as Mathematica) use
Log[x] for the natural log.  In order to compute the base-ten log in Mathematica, you have to
specify the base by writing Log[10, x]. Fortunately all log functions share the following
useful properties regardless of base
logABlogAlogB
|     |     | logA/BlogAlogB  |         |     | (1.8)  |
| --- | --- | ----------------- | ------- | --- | ------ |
|     |     | logyx             | x logy |     |        |
The “bel” scale (after inventor Alexander Graham Bell) is defined as the log-base-ten of
the ratio of two signal “intensities” (quantities relating to the power or energy associated with
the signal).    In circuits work we are often interested in the output-to-input power ratio,
P /P , but the bel scale can be used to compare any two like quantities (for example, the
out in
ratio of signal power to carrier in an AM signal, or the ratio of signal power to noise power in
a certain bandwidth).   Since there are 10 “decibels” per bel the power ratio in dB is defined
as
P
|     |     | 10log out | (power ratio in dB)  |     | (1.9)  |
| --- | --- | --------- | -------------------- | --- | ------ |
10 P
in
Each time the power increases by a factor of ten, the power ratio in dB increases linearly by
10dB.  Since power is related to the square of voltage or current, the dB scale for those
quantities becomes (assuming identical source and load impedances1)
V2
V
|     | 10log | out 20log | out (voltage ratio in dB)  |     | (1.10)  |
| --- | ----- | ---------- | -------------------------- | --- | ------- |
|     | 10    |            | 10                         |     |         |
|     |       | V2         | V                          |     |         |
|     |       | in         | in                         |     |         |
In most cases our transfer function is a voltage or current ratio, so we will use 20log H(j)
to  compute  the  magnitude  in  dB.    Some  important  dB  conversions  to  remember  are
summarized below:

|     |     | |H|  | |H|   |     |     |
| --- | --- | ---- | ----- | --- | --- |
dB
1  20log10 dB
 
|     |     | 2   20log | 2 10log23 dB |     |     |
| --- | --- | --------- | -------------- | --- | --- |
2  20log26 dB
20log412 dB
4
5  20log514 dB
10  20log1020 dB

A logarithmic scale like the dB scale prove to be a great advantage when dealing with circuit
transfer functions, which are always of the form of a rational polynomial function as in (1.2).
Two related terms we will use in our discussion of frequency response plots are “decade”
and “octave”.    A decade change in frequency is a factor of ten.  So, for example, 1 kHz is a
decade above 100 Hz and a decade below 10 kHz.  An “octave” is a factor of two, so
similarly 1 kHz is an octave above 500 Hz and an octave below 2 kHz.

1 If the source and load impedances are not the same this shows up as an additive constant in (1.10),
not especially critical for the discussion of this chapter.
|     |     |     | 3   | © Bob York 2009  |     |
| --- | --- | --- | --- | ---------------- | --- |

| 4   |     |     |     |     |     |     | Frequency Response and Bode Plots  |     |     |     |
| --- | --- | --- | --- | --- | --- | --- | ---------------------------------- | --- | --- | --- |

1.2
Bode Amplitude Plots
Simple Poles and Zeroes
Consider the transfer function of a first-order circuit with a simple pole at s1.  The AC
| steady-state frequency-response is determined by letting s |     |     |     |       |     |        | j   |     |     |         |
| ----------------------------------------------------------- | --- | --- | --- | ----- | --- | ------ | ---- | --- | --- | ------- |
|                                                             |     |     |     | 1     |     |        | 1    |     |     |         |
|                                                             |     |     |     | H(s) |    | H(j) |      |     |     | (1.11)  |
|                                                             |     |     |     | s1   |     |        | j1 |     |     |         |
The magnitude of the transfer function is then given by
1/2
|     |     |     |     | H(j) | 2 | 1 |     |     |     | (1.12)  |
| --- | --- | --- | --- | ----- | ---- | --- | --- | --- | --- | ------- |
|     |     |     |     |       |      |   |     |     |     |         |
This function is plotted in Figure 1-1 below for frequencies that are two orders of magnitude
above and below 1;  clearly the response is quite different on either side of this point.
The asymptotic behavior for 1 and 1 can be found from (1.12) as
|     |     |     |       |              | 0 dB |     | 1 |     |     |         |
| --- | --- | --- | ----- | ------------- | ---- | --- | --- | --- | --- | ------- |
|     |     |     | H(j) |             |      |     |     |     |     | (1.13)  |
|     |     |     |       | dB 20logdB |      |     | 1 |     |     |         |
These asymptotes are just straight
Break point at ω= 1
| lines  on  | the  dB  | vs.  | log  | plot.   |     |     |     |     |     |     |
| ---------- | -------- | ---- | ----- | ------- | --- | --- | --- | --- | --- | --- |
0dB
| For  1  | the  | function  |     | is  a  |     |     |     |     |     |     |
| --------- | ---- | --------- | --- | ------ | --- | --- | --- | --- | --- | --- |
-3dB
| constant,            | H 1, or 0 dB.  At the  |     |           |     |     |     |     |     |         |           |
| -------------------- | ----------------------- | --- | --------- | --- | --- | --- | --- | --- | ------- | --------- |
| other extreme where  |                         |     | 1, the  |     |     |     |     |     | Slope:  | -20dB/dec |
or -6dB/octave
| transfer  | function  | decreases  |     | as  |     |     |     |     |     |     |
| --------- | --------- | ---------- | --- | --- | --- | --- | --- | --- | --- | --- |
1
| 20log  | in  | dB;  | on  a  | log- |     |     |     |     |     |     |
| -------- | --- | ---- | ------ | ---- | --- | --- | --- | --- | --- | --- |
H(s)
| frequency scale this is a straight  |     |     |     |     |     |     | s1 |     | 20log |    |
| ----------------------------------- | --- | --- | --- | --- | --- | --- | --- | --- | ------ | --- |
10
| line  with     | a          | slope     | of        | -20  |     |     |     |     |     |     |
| -------------- | ---------- | --------- | --------- | ---- | --- | --- | --- | --- | --- | --- |
| dB/decade;     | that       | is,  the  | transfer  |      |     |     |     |     |     |     |
| function       | decreases  | by        | 20dB      | for  |     |     |     |     |     |     |
| every  factor  | of         | ten       | increase  | in   |     |     |     |     |     |     |

frequency.  This slope is equiv- Figure 1-1 – Frequency response for a simple pole at s1
| alent  to  | -6dB/octave,  |     | a  helpful  |     |     |     |     |     |     |     |
| ---------- | ------------- | --- | ----------- | --- | --- | --- | --- | --- | --- | --- |
thing to remember.
| The         | two      |      | straight-line  |     |     |     |     |     |     |     |
| ----------- | -------- | ---- | -------------- | --- | --- | --- | --- | --- | --- | --- |
| asymptotes  | capture  | the  | essential      |     |     |     |     |     |     |     |
H(s)s1
features of the plot, meeting at a
|            |                |     |     |      |     |     |     |     | 20log |    |
| ---------- | -------------- | --- | --- | ---- | --- | --- | --- | --- | ------ | --- |
| frequency  | corresponding  |     | to  | the  |     |     |     |     |        | 10  |
pole location.  This is the “break
|     |     |     |     |     |     |     |     |     | Slope:  -20dB/dec |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | ----------------- | --- |
point”.  At this point the transfer
or -6dB/octave
| function has a magnitude  |     |     |     |     |     | 0dB |     |     |     |     |
| ------------------------- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
+3dB
1
| H(j1) |    | , or   -3 dB     |     |     |     |     |     | Break point at ω= 1 |     |     |
| ----- | --- | ---------------- | --- | --- | --- | --- | --- | ------------------- | --- | --- |
2
| A  transfer  |     | function  | with  | a   |     |     |     |     |     |     |
| ------------ | --- | --------- | ----- | --- | --- | --- | --- | --- | --- | --- |

simple zero behaves similarly, as  Figure 1-2 – Frequency response for a simple zero at s1
shown in Figure 1-2, except that
© Bob York 2009

| Bode Amplitude Plots  |     |     |     |     |     |     |     |     |     | 5   |
| --------------------- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |

the function turns up at the break point instead of down.  Otherwise the rate of change is the
same (20 dB per decade above the breakpoint).
This general behavior can be demonstrated for any simple pole or zero, including repeated
roots.  For example, let’s take a repeated pole at sa
|     |     |     |       | 1      |     |        |         | 1   |     |         |
| --- | --- | --- | ----- | ------ | --- | ------ | ------- | --- | --- | ------- |
|     |     |     | H(s) |        |    | H(j) |         |     |     | (1.14)  |
|     |     |     |       | (sa)r |     |        | (ja)r |     |     |         |
where  r is an integer representing the number of times the pole is repeated.  The magnitude
of the frequency response is now
r/2
|     |     |     |     | H(j) | 2 | a2 |     |     |     | (1.15)  |
| --- | --- | --- | --- | ----- | ---- | ---- | --- | --- | --- | ------- |
|     |     |     |     |       |      |     |    |     |     |         |
In this case the asymptotic behavior for a and a can be found from (1.15)
|     |     |       |     | 20rloga |     | a |     |       |     |         |
| --- | --- | ----- | --- | --------- | --- | --- | --- | ----- | --- | ------- |
|     |     | H(j) |     |         |     |     |     | [dB]  |     | (1.16)  |
dB
|     |     |     |     | 20rlog |     | a |     |     |     |     |
| --- | --- | --- | --- | --------- | --- | --- | --- | --- | --- | --- |
Once again the asymptotes are
Break point at ω= a
| just  straight                | lines  | meeting  | at  |     |     |         |     |     |     |     |
| ----------------------------- | ------ | -------- | --- | --- | --- | ------- | --- | --- | --- | --- |
| a, shown in Figure 1-3  as  |        |          |     |     |     | 20rlog | a   |     |     |     |
10
the dashed lines.  In this case
Bd ,|H| ,edutingaM
Correction: -3rdB
the slope breaks downward by
Slope: -20rdB/dec
20rdB/decade, or 20dB/decade
-6rdB/octave
| for  each                       | time  the  | pole  |     | is  |     |     |     |     |     |           |
| ------------------------------- | ---------- | ----- | --- | --- | --- | --- | --- | --- | --- | --------- |
| repeated. The dashed lines are  |            |       |     |     |     |     | 1   |     |     | 20rlog  |
H(s)
| called  | the  uncorrected  |     | or  |     |     |     |     |     |     | 10  |
| ------- | ----------------- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
(sa)r
“straight-line” Bode plot for the
| transfer     | function.  |   Clearly  | the  |     |       |     |                       |     |     |      |
| ------------ | ---------- | ---------- | ---- | --- | ----- | --- | --------------------- | --- | --- | ---- |
| uncorrected  | plot       | captures   | the  |     |       |     |                       |     |     |      |
| essential    | behavior   | of         | the  |     | 0.01a |     | 0.1a                  | a   | 10a | 100a |
| frequency    | response   | with       |      | a   |       |     | Frequency, ω, [rad/s] |     |     |      |

minimum  of  effort.    We  can  Figure 1-3 – Bode plot for a repeated pole at sa.  The
dashed line is a quick estimate called the “uncorrected” Bode
always improve the accuracy of
plot.  The solid line is the “corrected” Bode plot, passing
| the  sketch  | by  drawing  |     | in  | a   |     |     |     |     |     |     |
| ------------ | ------------ | --- | --- | --- | --- | --- | --- | --- | --- | --- |
through the correct location at the break point.
smoothed or “corrected” version
that meets the straight-line asymptotes away from the break-point and passes through the true
value of the transfer function immediately at the break point, which in this case is given by
|     |     |       |     |          |    |                   |     |     |     |         |
| --- | --- | ----- | --- | -------- | --- | ------------------ | --- | --- | --- | ------- |
|     |     | H(ja) |     | 20rlog | a   | 2 (20rloga3r)dB  |     |     |     | (1.17)  |
dB
This shows that the corrected plot should passes through a point that is  3rdBbelow the
uncorrected curve at the break point, or 3dB for each time the pole is repeated.  The corrected
Bode plot is shown as the solid line in Figure 1-3.
Transfer Functions with Multiple Simple Poles and Zeroes
Suppose we have a transfer function with more than one pole or zero, or a combination of
simple poles and zeroes. For example:
(sz)
|     |     |     |     |     | H(s) | A   |     |     |                  | (1.18)  |
| --- | --- | --- | --- | --- | ----- | --- | --- | --- | ---------------- | ------- |
|     |     |     |     |     |       | (s | p)  |     |                  |         |
|     |     |     |     |     |       | 5   |     |     | © Bob York 2009  |         |

| 6   |     |     |     | Frequency Response and Bode Plots  |     |     |
| --- | --- | --- | --- | ---------------------------------- | --- | --- |

An interesting thing happens when we express the magnitude of this transfer function in dB:
using the properties of the log function (1.8), we get
1
|     | H(s)dB20log | A   | 20log sz | 20log |     | (1.19)  |
| --- | ------------ | --- | ---------- | ------ | --- | ------- |
|     |              |     |            | s     | p   |         |
Thus converting to dB breaks the transfer function into a simple sum of the individual factors
that we have already considered.  The composite response is then just a simple sum of the
individual responses.  Let’s look at a specific example:
10(s100)
|     |     | H(s) |     |     |     | (1.20)  |
| --- | --- | ----- | --- | --- | --- | ------- |
(s1)
This  is  plotted  in  Figure  1-4.    In  the  composite  response  the  transfer  function  breaks
downward at the pole location (1), and then flattens out again when the zero location is
reached  (100).  Can you see why?  When the zero is reached, the downward break of the
first pole is canceled out by the upward break of the zero.  At low frequencies (0) the
magnitude of the transfer function is a constant representing a sum of the values (in dB) of
the low-frequency asymptotes of each individual term: 20dB + 0dB + 40dB = 60dB.  At the
high frequencies (s) the transfer function in (1.20) approaches the limiting value of 10
(20 dB).
|     | Constant A=10 | Simple pole at s=-1 |     | Simple zero at s=-100 |     |     |
| --- | ------------- | ------------------- | --- | --------------------- | --- | --- |
1
0 dB
|     | H(s)10 |     | H(s) |     |     |     |
| --- | ------- | --- | ----- | --- | --- | --- |
(s1)
|     | 20 dB |     |     | 40 dB |     |     |
| --- | ----- | --- | --- | ----- | --- | --- |
|     |       | +   |     | +     |     |     |
H(s)(s100)
|     |      |          | 1     |           | 100 |     |
| --- | ---- | -------- | ----- | --------- | --- | --- |
|     |      | lim H(s) | 60dB | 10(s100) |     |     |
|     |      | s0      |       | H(s)     |     |     |
|     | Add  | 60 dB    |       |           |     |     |
(s1)
together
40 dB
|     |     |     |     | lim H(s) | 20dB |     |
| --- | --- | --- | --- | -------- | ----- | --- |
s
20 dB
|     |     | 10-2 10-1 | 1 10 | 102 103 | 104   |     |
| --- | --- | --------- | ---- | ------- | ----- | --- |
Figure 1-4 – Illustration of how the composite Bode plot of the transfer
function in (1.20) is a superposition of the individual terms.

From this example some simple rules for generating uncorrected Bode plots begin to
emerge: when poles are encountered the slope always decreases by 20 dB/decade.  When
zeroes are encountered the slope always increases by +20 dB/decade.  All we need to do is
choose a suitable starting point and then start drawing straight lines, changing the slope up or
down depending on whether we encounter a pole or a zero.
Often the most difficult part is figuring out where to start the plot, or how to position the
asymptotes on the vertical scale.  In the previous example the transfer function begins with a
constant value at low frequencies which makes things easy; we just let 0 in the transfer
function and take the magnitude of what is left over,
© Bob York 2009

| Bode Amplitude Plots  |     |     |     |     |     |     | 7   |
| --------------------- | --- | --- | --- | --- | --- | --- | --- |

10(100)
|     | lim H(s) |    |     | 100060dB  |     |     | (1.21)  |
| --- | -------- | --- | --- | ----------- | --- | --- | ------- |
|     | s0      |     | 1   |             |     |     |         |
Here is a slightly more challenging example:
10s
|     |     | H(s) |     |     |     |     | (1.22)  |
| --- | --- | ----- | --- | --- | --- | --- | ------- |
(s1)
The first thing to notice is that the frequency response will begin on an upward trajectory
because of the zero at s0; can you see why?  We’ve already found that the slope increases
after each zero, and since we are always plotting frequency on a log scale we can never
include the point 0 on the plots.  No matter how we choose the limits the plot must
always start at a frequency above the first zero, and thus the plot will begin with an upward
slope  of  +20  dB/decade.
30
| When  we  reach  the  next  |     |     |     |     |     |     |     |
| --------------------------- | --- | --- | --- | --- | --- | --- | --- |
break-point  (associated
20
with  the  pole  at  s1)
the slope will decrease by
|                              |     |     | Slope:    |     | 17dB |     |     |
| ---------------------------- | --- | --- | --------- | --- | ---- | --- | --- |
| 20 dB/dec, flattenening the  |     |     | 20 dB/dec |     |      |     | 10  |
| response.   The result is a  |     |     |           |     |      | 10s |     |
H(s)
high-pass  filter  response.
0
(s1)
| The  only  question  that  |     |     |     |     |     |     |     |
| -------------------------- | --- | --- | --- | --- | --- | --- | --- |
| remains  is  where         | to  |     |     |     |     |     |     |
-10
position the asymptotes on
the vertical scale; that is,
-20
where  to  start  drawing
| lines?    For  this  we  need  |     |     |     |     |     |     |     |
| ------------------------------ | --- | --- | --- | --- | --- | --- | --- |
some convenient reference
Figure 1-5 – Bode plot for the example of (1.22).  The plot begins
point to begin the plot.  In  with an upward slope of 20 dB/decade because of the zero at s=0.
this case it seems best to
start at high-frequencies and work backwards, since for 10 the magnitude approaches a
limiting value of
|     | lim | Hs | 10, | or 20 dB  |     |     | (1.23)  |
| --- | --- | ---- | ---- | --------- | --- | --- | ------- |
s
So now we can draw the Bode plot as shown in Figure 1-5: the curve starts up at a slope of
+20 dB/decade due to the zero at s=0, and flattens out at a level of 20 dB at the break point.
These two asymptotes are shown as the dashed lines.  We then sketch in the “corrected” plot
which passes through a point 3dB below the uncorrected plot at the break point, or 17dB.
Let’s do one more example of multiple poles and zeroes:
10s
|     | H(s) |     |     |     |     |     | (1.24)  |
| --- | ----- | --- | --- | --- | --- | --- | ------- |
(s10)(s100)2
First think abut this qualitatively: there is a simple zero at  s0, a simple pole at s10,
and a double pole at  s100. Can you start to visualize the shape of the Bode plot?  The
first part of the plot (for 100) the shape should be similar to the previous example,
starting on a positive slope of +20 dB/decade and flattening out above 10, but the double
pole at 100 will cause the slope to break downward again by -40 dB/decade.  So the
function has a band-pass response shape.  The only difficult part here is how to position the
asymptotes on the vertical scale.  In this example the techniques we used previously don’t
|     |     |     | 7   |     |     | © Bob York 2009  |     |
| --- | --- | --- | --- | --- | --- | ---------------- | --- |

| 8   |     |     |     |     |     |     |     | Frequency Response and Bode Plots  |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- | ---------------------------------- | --- | --- |

work; if we test the low- and
See text
high-frequency limits by letting
1st-order break
2nd-order break
| s0 or  | s, the transfer  |     |     |     |     | atω= 10 |     |     |     |     |
| ------- | ------------------ | --- | --- | --- | --- | ------- | --- | --- | --- | --- |
atω= 100
function goes to zero, which is
negative infinity on a dB scale!
-63dB
| In this situation there are two  |          |     |               |     |     |     |     |     | -66dB |     |
| -------------------------------- | -------- | --- | ------------- | --- | --- | --- | --- | --- | ----- | --- |
| common                           | methods  |     | of  attack.   |     |     |     |     |     |       |     |
+20dB/dec
| The  | first  | (and  | most  |     |     |     | or +6dB/octave |     |     |     |
| ---- | ------ | ----- | ----- | --- | --- | --- | -------------- | --- | --- | --- |
straightforward) method is just
to choose a specific frequency,
preferably far from all the other
|             |          |      |           |     |     | H(j1) | 80dB |     | -40dB/dec       |     |
| ----------- | -------- | ---- | --------- | --- | --- | ----- | ------ | --- | --------------- | --- |
| poles  and  | zeroes,  | and  | simply    |     |     |       |        |     | or -12dB/octave |     |
| evaluate    |          | the  | function  |     |     |       |        |     |                 |     |
numerically.  The function will
have to pass through that point,
Figure 1-6 – Bode plot for the function given in (1.24)
correct?   Usually it is best to
choose the lowest or highest frequency on the plot for this purpose, assuming it is a factor of
ten below the nearest pole or zero.  For example, at 1 we have
10(j1)
|     |     |     |     | H(j1) |    |     |     |     |     | (1.25)  |
| --- | --- | --- | --- | ----- | --- | --- | --- | --- | --- | ------- |
(j110)(j1100)2
This looks nasty, but remember that we can find the magnitude of a complex expression like
this by evaluating the magnitude of each complex term individually:
|     |       |     | 10    | j1     |     |       | 10     |       |         |         |
| --- | ----- | --- | ----- | ------ | --- | ----- | ------ | ----- | ------- | ------- |
|     | H(j1) |    |       |        |    |       |        | 104 | 80dB  | (1.26)  |
|     |       |     | j110 | j1100 | 2   |       |       | 2    |         |         |
|     |       |     |       |        |     | 1102 | 11002 |       |         |         |
(the exact value computes to -80.04 dB).  As shown in Figure 1-6, we position the first
dashed-line asymptote at -80dB for 1, sloping up at +20dB/decade, and from there we
just follow the basic rules of changing slope for each pole and zero that is encountered.
The second method for positioning the curve vertically is similar in that we try to evaluate
the function at some point numerically, but focusing on the asymptotic behavior of each term
in the transfer function.  At any particular frequency we can split up the transfer function into
two parts, grouping all the poles and zeros that lie at or below this frequency, and grouping
all the terms with poles and zeroes that lie above this frequency.  For example, at a frequency
just above the first pole location 10 we could write
|     |     |     | terms with poles  |     |     | terms with poles  |     |     |     |     |
| --- | --- | --- | ----------------- | --- | --- | ----------------- | --- | --- | --- | --- |
or zeros at or
or zeros at or
|     |     |        |     |                  |        | ab ov | e  =1 0 |              |     |         |
| --- | --- | ------ | --- | ---------------- | ------ | ----- | -------- | ------------ | --- | ------- |
|     |     |        |     | b  e  low    |  =10 |    |      |              |     |         |
|     |     |        |     |                  |        |      |          |             |     |         |
|     |     |        |     |  10s            |       |       | 1        |              |     |         |
|     |     | H(j10) |    |                  |        |      |          | 10360dB  |     | (1.27)  |
|     |     |        |     |                 |       |      | 2        |             |     |         |
|     |     |        |     |  s 1           | 0     |  ( s |  10 0)  |             |     |         |
|     |     |        |   |                |     |    |      |              |     |         |
101 for 10
104 for 100
This is the level the uncorrected Bode plot should pass through at the first pole location
10.  The terms in the first bracket have poles and zeroes at or below 10 so they each
contribute their high-frequency asymptotic behavior to the uncorrected Bode plot. The terms
in the second brackets contribute their low-frequency asymptotic behavior to the plot.   We
can see in Figure 1-6 that the uncorrected bode plot does indeed pass through -60dB at
© Bob York 2009

Bode Amplitude Plots 9
10. This latter method is how certain software packages generate uncorrected Bode
plots from complicated transfer functions.
We can now summarize our findings as a set of rules or guidelines for drawing Bode plots
involving simple/repeated poles and zeroes:
Rules for Drawing Bode Magnitude Plots with Simple Poles and Zeroes
■ First determine all the break points (pole and zero locations) and arrange in order of
increasing frequency. Choose a frequency range for the plot that encompasses all
these points, adding an extra decade of frequency above and below this range.
■ Based on the poels and zeroes, make a quick sketch of the expected shape of the
Bode plot on a piece of scrap paper. This will help you find the appropriate vertical
scales. For a simple pole or zero of the form (sa) the slope of the uncorrected
Bode plot changes at the break point a, increasing by 20 dB/decade for a zero,
and decreasing by 20dB/decade for a pole. For a repeated pole or zero (sa)r the
slope changes by 20rdB/decade, or 20 dB for each time the pole or zero is repeated.
■ To find a reference level we first consider the behavior of the function for low-
frequencies (0) or high frequencies (). If the limiting behavior
approaches a constant value at these extremes that is a good starting point.
Otherwise, we must evaluate the function numerically at some particular frequency,
preferably in a region with a constant-value “plateau”.
■ Once the uncorrected Bode plot is finished, a corrected version can be drawn. For
simple/repeated roots the true response passes through a point that is 3r dB below the
uncorrected curve at the break point, or 3dB for each time the pole is repeated
These rules work well for transfer functions that have poles and zeroes that are well
separated in frequency (by a factor of 10 or more). If the poles and zeroes are very close
together the rules break down and we must evaluate the function numerically.
Normalized Functions and Time Constants
Our approach thus far has been to work with transfer function in the pole-zero form (1.2).
Many books recommend re-normalizing the transfer function first by dividing the numerator
by all the zeroes, and dividing the denominator by all the poles. For example, if we had a
transfer function given by
5(s2)
H(s) (1.28)
(s10)(s100)
we could factor out the zeroes from the numerator and the poles in the denominator to give
5(2) (1s/2)
H(s) (1.29)
10(100) (1s/10)(1s/100)

0.01(or 40dB)
In this procedure all the poles and zeroes have the form (1s/a)r, from which you can see
that the low-frequency asymptote for each term is now always 1, or 0 dB. The break point is
still at a, and the same rules apply: the slope goes up by +20dB/decade for each zero,
and down by 20dB/decade for each pole.
Is it an advantage to renormalize the function in this way? Probably not, at least in terms
of the effort that goes into making a Bode plot by hand. Factoring out the terms as in (1.29)
9 © Bob York 2009

10 Frequency Response and Bode Plots
does tell us that the starting value of the plot will be -40dB at low frequencies, but we could
get this information just as easily from (1.28) by letting s0. And when there are zeroes at
s0, any potential advantage of renormalizing disappears, because we still have to invest
the same amount of effort (or more) in figuring out where to position the lines vertically.
However, there are times in circuit analysis when this normalized form does appear
naturally, so it is important to be familiar with generating Bode plots from both forms. When
it appears it us usually written in terms of time constants, like this
s(1s)
H(s) 1 (1.30)
(1s )(1s)
2 3
The break points in the Bode
Break point at ω= ω
plot are now at 1/, 1/ , and n
1 2
1/ . Recall that a simple pole
3
of the form 1/(s p) is
associated with an exponential
in the time-domain, ept, thus
simple poles are always related
to time constants as 1/ p .
Some advanced circuit analysis
techniques focus specifically on
the rapid estimation of time-
constants in complex circuits, in 0.1ω ω 10ω
n n n
which case it is often easier to
Frequency, ω, [rad/s]
work with the time constant
form as in (1.30). It should be
clear by now that generating a
Bode plot for this case is a simple extension of the techniques we have developed earlier.
Second-Order Response with Complex Roots
An important remaining issue is the case of complex-conjugate pole pairs, as in (1.4). For
this purpose it proves helpful to write the second-order polynomial in the form (1.5), e.g.
2
H(s) n (1.31)
s2 2s2
n n
In this form the quadratic formula gives the pole locations as
s  2 1 (1.32)
n n
For 1 the 2nd-order response involves two simple (real) poles, and we already know how
to deal with that situation. Stable complex-conjugate pole pairs occur when 01, and
this is case we are most interested in here. The amplitude-frequency response is given by
H(j)   n 2 2 2 22 4222 1/2 (1.33)
2 2  j2 n   n n  
n n
Figure 1-7 shows the asymptotic behavior of (1.33), well above and well below  , i.e. the
n
uncorrected Bode plot. These asymptotes are given by
© Bob York 2009
Bd
,|H|
,edutingaM
lim H(s) 0dB
s0
Slope: -40dB/dec
-12dB/octave
2 20log 2
H(s) n 10
s2 2s2
n n
Figure 1-7 – Uncorrected Bode amplitude plot for a second-
order response with 01.

| Bode Amplitude Plots  |     |     |     |     |     |     |     |     |     |     |     | 11  |
| --------------------- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |

|     |     |       |     |          | 0dB |  |     |     |       |     |     |         |
| --- | --- | ----- | --- | ---------- | --- | --- | --- | --- | ----- | --- | --- | ------- |
|     |     | H(j) |     |          |     |     |     | n   | [dB]  |     |     | (1.34)  |
|     |     |       | dB  | 20log2 |     |  |     |     |       |     |     |         |
n
Interestingly the asymptotic behavior is the same as it would be for a repeated simple pole at
; the slope decreases by 40dB/decade at this location.  So the uncorrected Bode plot
n
| for  the  | complex  | conjugate  |     |     |     |     |     |     |     |     |     |     |
| --------- | -------- | ---------- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
poles is the same as it would be
ξξ==00..0022
for a simple repeated pole, with
 behaving as the break
n
| point  in  | this  case.            |   For  | this  |     |     |     |     |     |     |     |     |     |
| ---------- | ---------------------- | ------ | ----- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| reason    |  is called the corner  |        |       |     |     |     |     |     |     |     |     |     |
n
| frequency  | for  the  | complex  |     |     |     |     |     |     |     |     |     |     |
| ---------- | --------- | -------- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
ξξ==11
second-order response.
It is when considering the
22
nn
| corrected  | Bode  plot  | for  | the  |     |     | HH((ss)) |     |     |     |     |     |     |
| ---------- | ----------- | ---- | ---- | --- | --- | ---------- | --- | --- | --- | --- | --- | --- |
ss22 22ss22
| complex second-order response  |        |        |      |     |          |     |     | nn  | nn  |     |     |        |
| ------------------------------ | ------ | ------ | ---- | --- | -------- | --- | --- | --- | --- | --- | --- | ------ |
| that  things                   | start  | to     | get  |     |          |     |     |     |     |     |     |        |
|                                |        |        |      |     | 00..11ωω |     |     |     | ωω  |     |     | 1100ωω |
| interesting.                   |   As   | shown  | in   |     |          | nn  |     |     | nn  |     |     | nn     |
Figure 1-8, the behavior near  FFrreeqquueennccyy,,  ωω,,  [[rraadd//ss]]

the  break  point  is  a  strong  Figure 1-8 – Bode amplitude plot for the general 2nd-order low-
pass response for various values of .
| function   | of  the  parameter  |          | ,  |     |     |     |     |     |     |     |     |     |
| ---------- | ------------------- | -------- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| which  we  | call  the           | damping  |     |     |     |     |     |     |     |     |     |     |
factor.  For small  the curves are peaked sharply near the corner frequency.  Exactly at the
corner frequency the curve must pass through the point
1
|     |     |     | H(j) |    |     |  20log2 |     | [dB]  |     |     |     | (1.35)  |
| --- | --- | --- | ----- | --- | --- | ---------- | --- | ----- | --- | --- | --- | ------- |
n
2
Note  that  this  correction  may  be  above  the  asymptote  (positive)  or  below  (negative)
depending on the value of  the damping factor.

+28 dB
|     | ξ=0.02 |     |     |     |     |     |      | H(j)   |    | /  | H(j    | )   |
| --- | ------ | --- | --- | --- | --- | --- | ----- | ------- | --- | --- | ------- | --- |
|     |        |     |     |     |     |     |       |         | n   | p n |         | p   |
|     |        |     |     |     |     |     | 0.02  | +28 dB  |     | ~1  | +28 dB  |     |
ξ=0.1
|     |     |     |     |     |     |     | 0.05  | +20 dB  | 0.997  |     | +20 dB  |     |
| --- | --- | --- | --- | --- | --- | --- | ----- | ------- | ------ | --- | ------- | --- |
+14 dB
ξ=0.2
|       |     |     |     |       |     |     | 0.1  | +14 dB  | 0.990  |     | +14dB    |     |
| ----- | --- | --- | --- | ----- | --- | --- | ---- | ------- | ------ | --- | -------- | --- |
| ξ=0.4 |     |     |     | +8 dB |     |     |      |         |        |     |          |     |
|       |     |     |     |       |     |     | 0.2  | +8 dB   | 0.959  |     | +8.1 dB  |     |
+2.7 dB
|     |     |     |     |     |     |     | 0.4  | +1.9 dB  | 0.825  |     | +2.7dB  |     |
| --- | --- | --- | --- | --- | --- | --- | ---- | -------- | ------ | --- | ------- | --- |
-3 dB
|      |          |     |     |     |       |     | 0.5    |     | 0 dB  0.707  |     | +1.3 dB  |     |
| ---- | -------- | --- | --- | --- | ----- | --- | ------ | --- | ------------ | --- | -------- | --- |
|      |          |     |     |     | -6 dB |     | 0.707  |     | -3 dB        | 0   | 0 dB     |     |
| 1/ | 2 0.707 |     |     |     |       |     |        |     |              |     |          |     |
ξ=1
|     |     |     |     |     |     |     | 1   |     | -6 dB  | —   | —   |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | ------ | --- | --- | --- |
Figure 1-9 – Behavior near the corner frequency for various values of the damping factor .

Also note that the peak value is not necessarily centered exactly at the corner frequency;  to
find the peak location we set the first derivative equal to zero, giving

|     |     | H(j) | 0  |    |  |   | 122  (low-pass)  |     |     |     |     | (1.36)  |
| --- | --- | ----- | --- | --- | --- | --- | ------------------ | --- | --- | --- | --- | ------- |
|     |     |       |     |     |     | p   | n                  |     |     |     |     |         |

|     |     |     |     |     |     | 11  |     |     |     | © Bob York 2009  |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | ---------------- | --- | --- |

| 12  |     |     |     |     |     |     |     |     | Frequency Response and Bode Plots  |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | ---------------------------------- | --- | --- |

This result tells us that there is a peak or maximum in the response only when 122 0, or
equivalently for 01/ 2.  In this range the peak amplitude is given by
|     |     |     |     |     | 1   |     |     |    |     |    |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
12
|     |     |     | H(j | )  |     |    | 20log | 2  |     | [dB]  | (1.37)  |
| --- | --- | --- | ---- | --- | --- | --- | ------ | --- | --- | ----- | ------- |
p
|     |     |     |     | 2  | 12 |     |     |     |     |     |     |
| --- | --- | --- | --- | --- | ---- | --- | --- | --- | --- | --- | --- |
Figure 1-9 gives a close-up of the region near the corner frequency for various values of
damping factor. Physically this behavior near the break point is associated with a resonance
condition in the circuit; we will discuss this later.
If we instead have a complex pair of zeroes in the transfer function, e.g.
s2 2s2
|     |     |     |     |     |       |     | n   | n   |     |     |         |
| --- | --- | --- | --- | --- | ----- | --- | --- | --- | --- | --- | ------- |
|     |     |     |     |     | H(s) |     |     |     |     |     | (1.38)  |
2
n
| Then                             | we  get     | the    | response  |       |     |       |     |          |     |     |     |
| -------------------------------- | ----------- | ------ | --------- | ----- | --- | ----- | --- | -------- | --- | --- | --- |
| shown                            | in  Figure  | 1-10.  |           |   As  |     |       |     |          |     |     |     |
|                                  |             |        |           |       |     |       | s2  | 2s2 |     |     |     |
|                                  |             |        |           |       |     |       |     |          | n   | n   |     |
| you might expect it is just the  |             |        |           |       |     | H(s) |     |          |     |     |     |
2
| mirror image of the complex  |     |     |     |     |     |     |     |     |     | ξ=1 |     |
| ---------------------------- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
n
pole pair, so all of the main
| conclusions  |       | are  the  | same.   |      |     |     |     |     |     |     |     |
| ------------ | ----- | --------- | ------- | ---- | --- | --- | --- | --- | --- | --- | --- |
| Only         | the   | sign      | of      | the  |     |     |     |     |     |     |     |
| correction   | near  | the       | break   |      |     |     |     |     |     |     |     |
point changes.  We can still
use the table in Figure 1-9 if
ξ=0.02
we remember to reverse the
| sign  (so,  | for         | example,  |     | the  |     | 0.1ω |     |                       |     | ω   | 10ω |
| ----------- | ----------- | --------- | --- | ---- | --- | ---- | --- | --------------------- | --- | --- | --- |
|             |             |           |     |      |     | n    |     |                       |     | n   | n   |
| curve       | lies  28dB  | below     |     | the  |     |      |     | Frequency, ω, [rad/s] |     |     |     |

asymptotes at the break point
Figure 1-10 – Amplitude response with a complex zero pair.
for 0.02).
| Similarly         |     | if  we      | add  | a   |     |     |     |     |     |        |     |
| ----------------- | --- | ----------- | ---- | --- | --- | --- | --- | --- | --- | ------ | --- |
| repeated zero at  |     | s0 to the  |      |     |     |     |     |     |     | ξ=0.02 |     |
2nd-order
| general  |     |     | low-pass  |     |     |     |     |     |     |     |     |
| -------- | --- | --- | --------- | --- | --- | --- | --- | --- | --- | --- | --- |
response of Figure 1-8 we get
a high-pass shape as shown
| in  Figure  | 1-11.        |   Again  |     | the  |     |     |     |     |     |     |     |
| ----------- | ------------ | -------- | --- | ---- | --- | --- | --- | --- | --- | --- | --- |
| general     | conclusions  |          |     | are  |     |     |     |     |     | ξ=1 |     |
unchanged.  The only thing
| to note here is that the peak  |     |     |     |     |     |     |     |     |     | s2  |     |
| ------------------------------ | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
H(s)
| location                       | shifts  | above  |     | the  |     |     |     |     |     |             |     |
| ------------------------------ | ------- | ------ | --- | ---- | --- | --- | --- | --- | --- | ----------- | --- |
|                                |         |        |     |      |     |     |     |     |     | s2 2s2 |     |
| break point in this case.  We  |         |        |     |      |     |     |     |     |     | n           | n   |
can still use the results in the
|     |     |     |     |     |     | 0.1ω |     |     |     | ω   | 10ω |
| --- | --- | --- | --- | --- | --- | ---- | --- | --- | --- | --- | --- |
|     |     |     |     |     |     | n    |     |     |     | n   | n   |
table of Figure 1-9, but the
|           |      |         |      |      |     |     |     | Frequency, ω, [rad/s] |     |     |     |
| --------- | ---- | ------- | ---- | ---- | --- | --- | --- | --------------------- | --- | --- | --- |
| data  in  | the  | column  | for  | the  |     |     |     |                       |     |     |     |
Figure 1-11 – Amplitude response for the general 2nd-order high-
| peak  frequency  |        | should  |       | be   |                                         |     |     |     |     |     |     |
| ---------------- | ------ | ------- | ----- | ---- | --------------------------------------- | --- | --- | --- | --- | --- | --- |
| interpreted      |        | as      |      | /   | pass function for various values of .  |     |     |     |     |     |     |
|                  |        |         | n     | p    |                                         |     |     |     |     |     |     |
| instead,         | since  | the     | peak  |      |                                         |     |     |     |     |     |     |
location is now given by
|     |     |     |      |     |     |     |     |    |              |     |         |
| --- | --- | --- | ----- | --- | --- | --- | --- | --- | ------------ | --- | ------- |
|     |     |     | H(j) | 0  |    |  |    | n   | (high-pass)  |     | (1.39)  |
p
|     |     |     |   |     |     |     |     | 122 |     |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- | ----- | --- | --- | --- |
© Bob York 2009

| Bode Amplitude Plots  |     |     |     |     |     |     |     | 13  |
| --------------------- | --- | --- | --- | --- | --- | --- | --- | --- |

For  example,  the  peak  location  for  0.4  in  Figure  1-11  would  shift  to
|   /0.8251.212 |     |     | .    |     |     |     |     |     |
| ------------------ | --- | --- | ---- | --- | --- | --- | --- | --- |
| p n                |     |     | n    |     |     |     |     |     |
What if we had a repeated complex pole pair?  For example, a transfer function that
involves the square of a term like that in (1.31). You should be able to convince yourself by
the stage that the asymptotic slope should now change by -80 dB/decade, and that the
correction factors near the break point are all doubled.
In terms of generating Bode amplitude plots in the presence of complex pole pairs, our
procedure is the same as before but can be amended as follows:

Additional Rules for Amplitude Plots with Complex Pole and Zero Pairs
First write the relevant 2nd-order polynomials in the standard form s2 2s2,
■
|     |     |     |     |     |     |     |     | n n |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
and extract the corner frequency   and the damping factor .  Complex roots are
n
associated with  01.  For 1 the roots are real and hence correspond to
simple poles or zeroes that we already considered.
■  Sketch the uncorrected Bode plot, which is equivalent to the case of a repeated
simple pole with a break point at .  If the complex roots are in the numerator
n
the slope increases by 40dB/decade at the break point.  If the complex roots are in the
denominator the slope decreases by 40 dB/decade.
■  Sketch in the corrected Bode plot.  The peak value, peak location, and value of the
function exactly at the break point can be determined from the table in Figure 1-9 or
the equations in (1.35)-(1.39).

Let’s conclude with an example that combines many of the details we’ve considered:
105s(s100)
|     |     |     | H(s) |     |     |     |     | (1.40)  |
| --- | --- | --- | ----- | --- | --- | --- | --- | ------- |
(s10)2(s2 400s106)
This function has a zero at
| s0  and  | a   | zero  | at  |     |     |     |     |     |
| --------- | --- | ----- | --- | --- | --- | --- | --- | --- |
s100, a repeated simple
|                   |     |      |      |     | -6 dB | -17 dB | -12 dB |     |
| ----------------- | --- | ---- | ---- | --- | ----- | ------ | ------ | --- |
| pole  at  s10,  |     | and  | two  |     |       |        |        |     |
other poles coming from a
| second-order                  |     | polynomial.   |     |           |     |             |     |           |
| ----------------------------- | --- | ------------- | --- | --------- | --- | ----------- | --- | --------- |
| By comparing the quadratic    |     |               |     | +20dB/dec |     |             |     |           |
| to the standard form we find  |     |               |     |           |     |             |     | -40dB/dec |
| 2 106                       |     | 103          |     |           |     | 105s(s100) |     |           |
 
|       n  |     | n     |     | H(s) |            |            |     |     |
| -------- | --- | ----- | --- | ----- | ---------- | ---------- | --- | --- |
|          |     |       |     |       | (s10)2(s2 | 400s106) |     |     |
| 2 400 |    | 0.2 |     |       |            |            |     |     |
n
From the table in Figure 1-9
| we  find  | a  correction  |     | of  |     |     |     |     |     |
| --------- | -------------- | --- | --- | --- | --- | --- | --- | --- |
+8dB at .  Where do
n
|            |      |        | Figure  1-12  | –    Example  | problem  | integrating  | many  | common  |
| ---------- | ---- | ------ | ------------- | ------------- | -------- | ------------ | ----- | ------- |
| we  start  | the  | plot?  | Let’s         |               |          |              |       |         |
features of Bode plots.
| evaluate  | the  function  |     | at  |     |     |     |     |     |
| --------- | -------------- | --- | --- | --- | --- | --- | --- | --- |
1, which is a decade below the lowest break point.  This gives:
105(1)(100)
|     |     |     | Hj1  | 0.1 |  20dB  |     |     |     |
| --- | --- | --- | ------- | ---- | -------- | --- | --- | --- |
(10)2(106)
|     |     |     |     | 13  |     |     | © Bob York 2009  |     |
| --- | --- | --- | --- | --- | --- | --- | ---------------- | --- |

| 14  |     |     |     |     |     | Frequency Response and Bode Plots  |     |     |     |
| --- | --- | --- | --- | --- | --- | ---------------------------------- | --- | --- | --- |

This completed plot is shown in Figure 1-12, with dots marking the starting point and the
values of the functions at the break points using our basic rules: down 6dB for a repeated
pole, up 3 dB for a simple zero, and up 20log2 for a complex pole pair.
ξ= 0
| Root Locus Plot  |     |     |     |     | s22 | 2 |     |     |     |
| ---------------- | --- | --- | --- | --- | ------ | --- | --- | --- | --- |
15
|                    |           |          |            |     | n      | n       |     |     |     |
| ------------------ | --------- | -------- | ---------- | --- | ------ | ------- | --- | --- | --- |
| Please             | remember  | that     | a  second- |     |        | 0 < ξ<1 |     |     | jω  |
|                    |           |          |            |     | ω = 13 |         |     |     | n   |
| order  polynomial  |           | doesn’t  | always     |     | n      |         |     |     |     |
10
have complex-conjugate roots, but
| we  CAN                            | always  | put  | it  in      | the  |     | ξ>1 | ξ>1 | 5   |     |
| ---------------------------------- | ------- | ---- | ----------- | ---- | --- | --- | --- | --- | --- |
| standard                           | form    | s2   | 2s2!   |      |     |     |     |     |     |
|                                    |         |      | n           | n    |     |     |     |     |     |
|                                    |         |      |             | -40  | -30 | -20 | -10 |     | 10  |
| You  should                        | make    |      | sure  that  | the  |     |     |     |     |     |
| damping factor is in the range of  |         |      |             |      |     |     |     | -5  |     |
ξ= 1
01 before you start plugging
-10
it into the formulas in (1.35)-(1.39).
-jω
n
| A  helpful  |     | way  | to  visualize  |     |     |     |     | -15 |     |
| ----------- | --- | ---- | -------------- | --- | --- | --- | --- | --- | --- |

| solutions  | of  | the  | second-order  |     |     |     |     |     |     |
| ---------- | --- | ---- | ------------- | --- | --- | --- | --- | --- | --- |
polynomial for all possible values  Figure 1-13 –  Root-locus in the complex plan for the
second-order polynomial as a function of damping factor.
of the damping factor is shown in
Figure 1-13.  This is called a root-
locus plot.  The arrows show the path of the roots in the complex plane, beginning with
0.  At this starting point the complex conjugate roots have no real part, lying on the
imaginary axis.  As the damping factor is increased the roots travel on a circular arc towards
the negative real axis.  When   1 the roots converge to a common point on the negative
real axis, corresponding to a repeated simple pole.  As the damping factor is increased beyond
that point the roots split along the real axis, one growing and one shrinking.
1.3  Bode Phase Plots
The transfer function H(j) is a phasor.  Thus far we have concentrated on the magnitude of
the transfer function, but the phase response is important as well; it tells us how the phase of a
sinusoidal  signal  changes  as  it  passes  through  the  network.    As  you  will  see  in  later
coursework, phase vs. frequency plots are important for investigating potential instabilities in
feedback systems.  So it is important to be just as familiar with making Bode phase plots as
with Bode magnitude plots.
Before we proceed it may be helpful to summarize some important points for finding the
phase of complex rational functions.  The key is to remember that any complex number  z
can be written as  z z ejz,  and when exponentials are multiplied the exponents add.  So
for a product of two phasor functions the net phase is the sum of individual phases:
|     |     | H(j)F(j)G(j) |     |     |  H(j)F(j)G(j)  |     |     |     | (1.41)  |
| --- | --- | ---------------- | --- | --- | ----------------------- | --- | --- | --- | ------- |
Similarly for a rational function we subtract the phases
N(j)
|     |     | H(j) |     |    | H(j)N(j)D(j)  |     |     |     | (1.42)  |
| --- | --- | ------ | --- | --- | --------------------- | --- | --- | --- | ------- |
D(j)
Here is a specific example that will encompass many of the situations to be encountered,
jzm
|     |     |        |     |               |     |      |  |     |         |
| --- | --- | ------ | --- | ------------- | --- | ------- | --- | --- | ------- |
|     |     |        |     | H(j)mtan1 |     | ntan1 |     |     |         |
|     |     | H(j) |     |              |     |       |    |    | (1.43)  |
pn
|     |     |     | j |     |     |  z  |    | p  |     |
| --- | --- | --- | ---- | --- | --- | ----- | --- | --- | --- |
© Bob York 2009

| Bode Phase Plots  |     |     |     |     |     |     |     |     |     |     | 15  |
| ----------------- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |

Phase Plots for a Simple Poles and Zeroes
Let’s start as before by considering a first-order circuit with a simple pole at s1,
|     |     |     |     |       | 1   |     |        | 1   |     |     |         |
| --- | --- | --- | --- | ----- | --- | --- | ------ | --- | --- | --- | ------- |
|     |     |     |     | H(s) |     |    | H(j) |     |     |     | (1.44)  |
|     |     |     |     |       | s1 |     | j1   |     |     |     |         |
The phase of the transfer function is given by
|     |     |     |     |     | H(j)tan1  |     |     |     |     |     | (1.45)  |
| --- | --- | --- | --- | --- | ----------------- | --- | --- | --- | --- | --- | ------- |
The asymptotic behavior for 1 and 1 can be easily found
|                |           |           |         |          |      | 0  | 1 |     |     |     |         |
| -------------- | --------- | --------- | ------- | -------- | ----- | --- | --- | --- | --- | --- | ------- |
|                |           |           |         | H(j) |       |     |     |     |     |     | (1.46)  |
|                |           |           |         |          | 90 |     | 1 |     |     |     |         |
| The  transfer  |           | function  |         | goes     |       |     |     |     |     |     |         |
| through        | a  phase  |           | change  | of       |       |     |     |     |     |     |         |
90 for a simple pole.  The
-6º
| asymptotes          | are   | shown  | as          | the  |     |     |     |     |      |     |     |
| ------------------- | ----- | ------ | ----------- | ---- | --- | --- | --- | --- | ---- | --- | --- |
| dotted              | blue  | lines  | in  Figure  |      |     |     |     |     |      |     |     |
| 1-14,  and          | will  | serve  | as          | our  |     |     |     |     | -45º |     |     |
| basic  uncorrected  |       |        | sketch      | for  |     |     |     |     |      |     |     |
1
| Bode  phase  |     | plots.  |   The  | true  |     | H(s) |     |     |     |     |     |
| ------------ | --- | ------- | ------ | ----- | --- | ----- | --- | --- | --- | --- | --- |
s1
| phase  (1.45)  |     | is  shown  | as  | the  |     |     |     |     |     |     |     |
| -------------- | --- | ---------- | --- | ---- | --- | --- | --- | --- | --- | --- | --- |
-84º
solid line for frequencies within
two orders of magnitude of the
| break      | point  | 1;  |   unlike  |        |     |     |     |     |     |     |     |
| ---------- | ------ | ----- | --------- | ------ | --- | --- | --- | --- | --- | --- | --- |
| amplitude  | plots  |       | the       | phase  |     |     |     |     |     |     |     |

approaches the low- and high- Figure 1-14 – Bode phase plot for a simple pole at s1
| frequency  | asymptotes  |                |     | more  |     |     |     |     |             |     |     |
| ---------- | ----------- | -------------- | --- | ----- | --- | --- | --- | --- | ----------- | --- | --- |
| slowly,    | taking      | approximately  |     |       |     |     |     |     | Correction: | r6 |     |
two decades of frequency above
r90
| or  below  | the  | break  | point  | to  |     |     |     |     |     |     |     |
| ---------- | ---- | ------ | ------ | --- | --- | --- | --- | --- | --- | --- | --- |
+84º
| closely approach the asymptote.  |          |             |     |      | seerged ,esahP |     |     |     |     |     |     |
| -------------------------------- | -------- | ----------- | --- | ---- | -------------- | --- | --- | --- | --- | --- | --- |
| Exactly                          | at  the  | breakpoint  |     | the  |                |     |     |     |     |     |     |
H(s)(sa)r
| function  | passes  |     | through  |     |     |     |     |     |     |     |     |
| --------- | ------- | --- | -------- | --- | --- | --- | --- | --- | --- | --- | --- |
r45
| tan1(1)45,  |        |              | or  halfway  |        |     |     |     |             |     |     |     |
| ---------------- | ------ | ------------ | ------------ | ------ | --- | --- | --- | ----------- | --- | --- | --- |
| between          | the    | asymptotes.  |              | A      |     |     |     |             |     |     |     |
| decade           | below  | the          | break        | point  |     |     |     |             |     |     |     |
|                  |        |              |              |        |     |     | -6º | Correction: |     | r6 |     |
| the  phase       |        | passes       | through      |        |     |     |     |             |     |     |     |
tan1(0.1)5.7,
|     |     |     | or  6;  | a   | 0º  |     |     |     |     |     |     |
| --- | --- | --- | --------- | --- | --- | --- | --- | --- | --- | --- | --- |
similar correction applies for a
|         |          |        |      |        | 0.01a |     | 0.1a |     | a   | 10a | 100a |
| ------- | -------- | ------ | ---- | ------ | ----- | --- | ---- | --- | --- | --- | ---- |
| factor  | of  ten  | above  | the  | break  |       |     |      |     |     |     |      |
Frequency, ω, [rad/s]

point (90684).
Figure 1-15 – Bode phase plot for a repeated zero at sa
| The  | behavior  | for  | a  zero  | is  |     |     |     |     |     |     |     |
| ---- | --------- | ---- | -------- | --- | --- | --- | --- | --- | --- | --- | --- |
similar; the phase increases by
90and passes though the midpoint of 45 at the break point.  We can extend the results for
simple repeated poles and zeroes as before using the more general function
|     |     |     | H(s)(sa)r |     |     | H(j)(ja)r |     |     |     |     |         |
| --- | --- | --- | ------------ | --- | --- | -------------- | --- | --- | --- | --- | ------- |
|     |     |     |              |     |     |               |     |     |     |     | (1.47)  |
Here the +sign represents a zero and the –sign represents a pole.  The phase is given by
|     |     |     |     |     |     | 15  |     |     |     | © Bob York 2009  |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | ---------------- | --- |

| 16  |     |     |     |     |     |     |     | Frequency Response and Bode Plots  |     |
| --- | --- | --- | --- | --- | --- | --- | --- | ---------------------------------- | --- |


|     |     |     |     |     | H(j)rtan1 |     |     |     | (1.48)  |
| --- | --- | --- | --- | --- | -------------- | --- | --- | --- | ------- |
|     |     |     |     |     |                |     |    |    |         |
|     |     |     |     |     |                |     |    | a  |         |
In this case the asymptotic behavior and value at the break point are
|     |     |     |          |       | 0 a |     |     |               |         |
| --- | --- | --- | -------- | ------ | ------ | --- | --- | ------------- | ------- |
|     |     |     | H(j) |        |        |     |     | H(ja)r45  | (1.49)  |
|     |     |     |          | r90 | a    |     |     |               |         |
The phase plot and asymptotes for (1.47) are shown in Figure 1-15.   In general we find that
the phase of the transfer function changes by 90 for each pole or zero, increasing 90 for a
zero and decreasing 90 for each pole.  The function passes through the midpoint of each
phase jump, at half the net phase change or 45 for each pole or zero, and passes through a
point that is 6 from the asymptote a decade above or below the break.  For repeated roots all
these values are multiplied by the number of times the root is repeated.  The black dots in
Figure 1-14 and Figure 1-15 serve as important references for drawing the corrected plot.
Phase Plots with Multiple Simple Poles and Zeroes
Our method for making the uncorrected Bode phase plots is simple: first determine the phase
in the limit of 0; that defines our starting point, then add dashed lines of constant phase,
jumping up 90 for each zero and down 90 for each pole.  We then add the reference points
at each phase jump and a decade above and below to guide our sketch of the smoothed or
corrected plot.  As a first example let’s revisit (1.20), given here again for convenience:
10(s100)
|     |     |     |     |     | H(s) |     |     |     | (1.50)  |
| --- | --- | --- | --- | --- | ----- | --- | --- | --- | ------- |
(s1)
The Bode phase plot is shown in Figure 1-16. The plot starts at 0 because H(j)10 (a
real number) as 0.  Then the uncorrected plot jumps down 90at 1 for the pole,
| and  then  | back  | up  | to  | 0  at  |     |     |     |     |     |
| ---------- | ----- | --- | --- | ------- | --- | --- | --- | --- | --- |
100 for the zero.  Now we
add the reference points.  You
| can see that we have marked  |           |      |       |        |     | -6º |     |     | -6º |
| ---------------------------- | --------- | ---- | ----- | ------ | --- | --- | --- | --- | --- |
| the  mid-points              |           | of   | each  | phase  |     |     |     |     |     |
| jump                         | at  45,  | and  | the   | 6     |     |     |     |     |     |
-45º
| corrections  |     | at  0.1  |     | and  |     |     | -45º |     |     |
| ------------ | --- | ---------- | --- | ---- | --- | --- | ---- | --- | --- |
103.
|                                    |   The  | only  | “new”  |     |     |     |     |      |     |
| ---------------------------------- | ------ | ----- | ------ | --- | --- | --- | --- | ---- | --- |
| issue here is the reference point  |        |       |        |     |     |     |     | -78º |     |
at  10.  This is a decade
| above  | the  pole   | and  | a  decade  |         |     |     |     |     |     |
| ------ | ----------- | ---- | ---------- | ------- | --- | --- | --- | --- | --- |
| below  | the  zero,  | so   | we         | get  a  |     |     |     |     |     |
double correction of 12; that
| is,  6 for the pole and        |             |     | 6 for  |      |                                             |     |     |     |     |
| ------------------------------- | ----------- | --- | ------- | ---- | ------------------------------------------- | --- | --- | --- | --- |
| the zero. The two extra dashed  |             |     |         |      | Figure 1-16 – Bode phase plot for  (1.50).  |     |     |     |     |
| lines                           | in  Figure  |     | 1-16    | are  |                                             |     |     |     |     |
included to help illustrate what is going on, representing the phase curves for the pole and
zero terms separately.  The key point to remember is that the total phase at any frequency is
the sum of contributions from all the poles and zeroes. In Figure 1-16, the pole and zero are
close enough together that their contributions overlap at 10.  In general, whenever we
mark a reference point for the corrected plot, we must always consider its proximity to other
breaks.
© Bob York 2009

| Bode Phase Plots  |     |     |     |     |     |     |     | 17  |
| ----------------- | --- | --- | --- | --- | --- | --- | --- | --- |

A few more examples will help illustrate the issues involved.  Consider:
102s
|     |     | H(s) |     |     |     |     |     | (1.51)  |
| --- | --- | ----- | --- | --- | --- | --- | --- | ------- |
(s10)(s100)
 The Bode phase plot for this function is shown in Figure 1-17.  The plot in this case starts at
90  because  H(j)0.1j  (a  positive  imaginary  number)  as  0.    Then  the
uncorrected plot jumps down
90at the first pole and down
|                                 |     |     | +84º |     |     | -6°correction due  |     |     |
| ------------------------------- | --- | --- | ---- | --- | --- | ------------------ | --- | --- |
| another  90 at the next pole.  |     |     |      |     |     | to pole at ω=102   |     |     |
The reference points at 1
+39º
and 103 are easy because
| only  one  | pole  contributes  | to  |     |     |     |     |     |     |
| ---------- | ------------------ | --- | --- | --- | --- | --- | --- | --- |
+6°correction due
| each.  But the reference points  |     |     |     |     |     |     | to pole at ω=10 |     |
| -------------------------------- | --- | --- | --- | --- | --- | --- | --------------- | --- |
at the phase jumps are slightly
| more challenging.  For the first  |     |     |     |     |     |     | -39º |     |
| --------------------------------- | --- | --- | --- | --- | --- | --- | ---- | --- |
102s
| jump  at  10   | you  see       | we     | H(s) |               |     |     |     |      |
| ---------------- | -------------- | ------ | ----- | ------------- | --- | --- | --- | ---- |
| have  marked     | the  crossing  |        |       | (s10)(s100) |     |     |     | -84º |
| point  at  39,  | or  6         | below  |       |               |     |     |     |      |
45.  This is because we are a
decade below the pole break at
| 102.  Similarly at 102  |     | Figure 1-17 – Bode phase plot for (1.51).  |     |     |     |     |     |     |
| --------------------------- | --- | ------------------------------------------ | --- | --- | --- | --- | --- | --- |
we show the crossing point at
39, or 6 above 45 because we are a decade above the pole break at 10.
So far the corrections have all been 6 because we have been dealing with simple poles.
What if we have a repeated root?  Consider a slight modification to the previous example:
104s
|     |     | H(s) |     |     |     |     |     | (1.52)  |
| --- | --- | ----- | --- | --- | --- | --- | --- | ------- |
(s10)(s100)2
The Bode phase plot for this
function is shown in Figure
-12°correction due to
+84º
| 1-18.  It  begins  | much  | like  |     |     |     | repeated pole at ω=102 |     |     |
| ------------------ | ----- | ----- | --- | --- | --- | ---------------------- | --- | --- |
Figure 1-17, but because of
+33º
| the  repeated  | root  | the  |     |     |     |     |     |     |
| -------------- | ----- | ---- | --- | --- | --- | --- | --- | --- |
uncorrected plot jumps down
+6°correction from
| by  180  | at  102.  |     |     |     |     |     | simple pole at ω=10 |     |
| --------- | ----------- | --- | --- | --- | --- | --- | ------------------- | --- |
Similarly, all of the reference
| point  corrections  | associated  |     |     |     |     | -84º |     |     |
| ------------------- | ----------- | --- | --- | --- | --- | ---- | --- | --- |
104s
| with  this  | repeated  root  | are  |     |     |     |     | -12°correction |     |
| ----------- | --------------- | ---- | --- | --- | --- | --- | -------------- | --- |
H(s)
| doubled, as indicated for the  |        |      |     | (s10)(s100)2 |     |     |     | -168º |
| ------------------------------ | ------ | ---- | --- | -------------- | --- | --- | --- | ----- |
| points  a  decade              | above  | and  |     |                |     |     |     |       |
below the repeated pole.
| The  key          | takeaway  | from  |     |     |     |     |     |     |
| ----------------- | --------- | ----- | --- | --- | --- | --- | --- | --- |
| this  discussion  | is  that  | we    |     |     |     |     |     |     |
Figure 1-18 – Bode phase plot for (1.52).
| should  always  | consider  | a   |     |     |     |     |     |     |
| --------------- | --------- | --- | --- | --- | --- | --- | --- | --- |
correction to the initial reference points when they involve contributions from multiple poles
or zeroes.  This is necessary when the poles or zeroes lie within two decades of each other in
frequency.  Thus we arrive at a simple set of rules for drawing Bode phase-plots with
multiple simple poles & zeroes:
|     |     |     | 17  |     |     |     | © Bob York 2009  |     |
| --- | --- | --- | --- | --- | --- | --- | ---------------- | --- |

| 18  |     |     | Frequency Response and Bode Plots  |     |
| --- | --- | --- | ---------------------------------- | --- |

Rules for Drawing Bode Phase Plots with Simple Poles and Zeroes
■  First determine the phase of the transfer function in the limit of 0.  That will
define the asymptotic starting point for the uncorrected plot.  Remember that if the
transfer function evaluates to a negative real number, the starting phase is 180.
■  Sketch the uncorrected phase plot by drawing a sequence of lines of constant phase,
beginning with the low-frequency asymptote above, and jumping discontinuously up
or down at each break point, increasing 90 for a zero and decreasing 90 for each
pole.  For repeated roots the jump is 90 for each time the root is repeated.
■  For each pole or zero, make an initial mark at the mid-point of each phase jump.
Then consider whether those points are within a decade or less from a neighboring
pole or zero.  If so, make the appropriate correction to account for the influence of
the neighboring pole or zero.  Make similar corrections at points a decade above and
below each pole location.
■  Draw in the smoothed or corrected Bode phase plot, passing through the corrected
reference points and meeting the asymptotes at points that are two decades away
from the nearest pole or zero.
Second-Order Response with Complex Roots
A complex conjugate pair of roots presents an interesting challenge in connection with phase
plots.  For a complex pole pair as in (1.31) we find
 2
|     | H(j)tan1 |  n      |    | (1.53)  |
| --- | ------------- | -------- | --- | ------- |
|     |               |  2 2 |    |         |
|     |               |  n      |    |         |
This is plotted in Figure 1-19, along with the uncorrected plot that we’d expect for a repeated
pole.    As  the  damping  factor  decreases,  the  slope  increases  steadily  to  more  closely
approximate  the  uncorrected  phase  plot  for  small  damping  factors.    Each  curve  passes
through the mid-point of the phase jump.

ξ=0.02
|     |     |     |   0.1 | 0.2   0.5 |
| --- | --- | --- | ------- | ----------- |
n n n
2
|     |             |     | 0.02  -0.2°  | -0.5°  -1.5°  |
| --- | ----------- | --- | ------------ | ------------- |
|     | H(s)       | n   |              |               |
|     | s2 2s2 |     | 0.05  -0.6°  | -1.2°  -3.8°  |
ξ=1 n n
|     |     |     | 0.1  -1.2°  | -2.4°  -7.6°  |
| --- | --- | --- | ----------- | ------------- |
|     |     |     | 0.2  -2.3°  | -4.8°  -15°   |
|     |     |     | -3.5°       | -7.1°  -22°   |
0.3
|     |     |     | -4.6°  | -9.5°  -28°  |
| --- | --- | --- | ------ | ------------ |
0.4
|     |     |     | -5.8°  | -12°  -34°  |
| --- | --- | --- | ------ | ----------- |
0.5
|     |     |     | 0.707  -8.1°  | -16°  -43°  |
| --- | --- | --- | ------------- | ----------- |
|     |     |     | 1             | -23°  -53°  |
-11.4°
Figure 1-19 – Phase plot for a 2nd-order low-pass response as a function of the damping factor.
Numerical data at three frequencies below the break are tabulated as an aid for sketching the response.
Superficially it seems relatively easy to deal with complex roots in a phase-plot, because the
curves all have a qualitatively similar shape for damping factors in the range of  01.
For small damping factors we simply draw the corrected plot a bit closer to the uncorrected
© Bob York 2009

Bode Phase Plots 19
plot. The challenge is getting the slope right, and how well we do that in a hand sketch is just
a matter of how hard we want to work at it! For simple poles and zeroes our method
consisted of drawing in reference points at the midpoint frequency and a decade above and
below this point. For the second-order complex roots we can use the same method, but we
must choose frequencies that are closer to the break in order to better approximate the slope;
 /2 and 2 are practical choices. The table in Figure 1-19 includes the phase correction
n n
for three frequencies below the break,  /10,  /5, and  /2. Clearly the symmetry of
n n n
the problem allows us to also use these corrections at 10 , 5 , and 2 , respectively.
n n n
Let’s finish with an illustrative example that involves complex-roots as well as simple
poles and zeroes, such as (1.40), repeated here for convenience:
105s(s100)
H(s) (1.54)
(s10)2(s2 400s106)
The Bode plot for this function is shown in Figure 1-20. For the uncorrected plot the phase
starts at 90 because of the zero at s0, then drops 180 at 10 because of the
repeated pole. It jumps 90 at 102 because of the simple zero, and drops again by
180 at 103 for the complex pole pair. The damping factor is 0.2, so from the table
in Figure 1-19 we find a phase correction of 2.3 a decade away, and 15 an octave away.
The annotations in Figure 1-20 explain how some of the reference points were calculated.
+11.4°from repeated pole at ω=10,
and -2.3°from table for ξ=0.2 due to
+79º
2nd-order pole at ω=103
-15°from table for ξ=0.2,
+6º and another -6°due to
simple zero at ω=102
-36º
+6°correction due to -21º
-6°correction due to
simple zero at ω=102
simple zero at ω=102
-96º
105s(s100) +15°correction
H(s) from table
(s10)2(s2 400s106) -165º
Figure 1-20 – Bode phase plot for (1.54)
Accuracy and Bode Plots
Looking back at the examples of phase plots in Figure 1-16 though Figure 1-20, you may
notice that simply drawing the curves through the mid-points of each phase jump would give
a reasonable good estimate of the actual curve. So it seems appropriate to ask, is all this
business about calculating mid-point corrections even necessary?
In fact this is an important issue because it concerns the broader question of what we are
trying to accomplish with our investigation of Bode plots. Nowadays we have the luxury of
making computer-generated amplitude and phase plots in a fraction of the time it takes to
draw a hand sketch. So in many respects, it simply does not make any sense to waste
valuable time in trying to make a highly accurate hand sketch. If analytical accuracy is what
19 © Bob York 2009

20 Frequency Response and Bode Plots
we’re after, then the computer is a better alternative. Furthermore, it turns out that in many
practical applications it is rarely important to know the phase to a tenth of a degree. Often
just knowing the phase to the nearest tens place is perfectly fine!
No, the real reason to persist in learning about Bode plots is the valuable insight it gives in
connecting the shape of the frequency response to the transfer function. Knowing how poles
and zeroes affect the amplitude and phase ultimately allows us to approach circuit analysis
from a design perspective; that is, how do we design a circuit to give a desired frequency
response? In this respect, computer-generated plots are not much help. They can tell you
how a circuit will perform, but they can’t tell you how to improve the circuit.
So if we keep in mind that our main goal in drawing Bode plots is usually to explore
qualitative behavior of a circuit or transfer function, then the answer to the question is yes:
we can usually take shortcuts like drawing the curve through the midpoint of the phase-
jumps. If more accuracy is required, the simple first-order corrections that we have
developed can be used to adjust the plot accordingly. If even greater accuracy is required,
then a computer-generated plot is needed.
© Bob York 2009