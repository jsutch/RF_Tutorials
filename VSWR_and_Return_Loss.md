## VSWR and Return Loss

https://www.youtube.com/watch?v=BijMGKbT0Wk

#### VWSR and Return Loss are both related to the transfer of RF power.

VSWR - Voltage Standing Wave Ratio (vizwarr)

Maximum power is transferred when the Source of the power and the Load of the power have impedences that are Matched. (e.g. 50$\Omega$ on both sides)


when matched all the power provided by the Source is absorbed by the Load.

- RF systems are typically 50$\Omega$
- Cable TV systems are typically 75$\Omega$

in Impedence Mismatch (50$\Omega$ to 75$\Omega$) causes some of the Forward Power to be reflected back to the Source. (Reflected or Reversed power)
- Reflected Power is almost always undesireable

Imedences are typically thought of as Resistive Powers, but in practice these are Complex values. They consist of a:
- Resistive (Real) part
- Reactive (Imaginary) part

R - (resistive)
jZ - (reactive)

So the formula is:  
R + jZ$\Omega$

A complex impedence is Matched by a Complex Conjugate in which the sign of the imaginary part is reversed.
e.g.

(source)  ---------------------- (load)  
35 + j6$\Omega$ is matched to 35 - j6$\Omega$



### Impedence

Impedence is a complex value that consists of
- Resistance (R) which does not change with frequency 
- Reactance (X) which does change with frequency
    - Two types of Reactance, created by Capacitors and Inductors
        - Capacitative (C) (+X)
        - Inductive (L) (-X)

So Impedence Z is point on a coordinate graph determined by R and X.

So Complex Impedence is both a Magnitude and a Directional.

Because of Reactance, total Impedence varies by Frequency.



- Dummy loads are very resistive loads designed to have a constant impedence over a wide frequency range.
- Antennas have a resistance that changes substantially by frequency. They are only used for specific frequencies.
    - Antenna impedence in real world applications is dependant on placement relative to a Ground Plane or other nearby objects


So with a Dummy Load the relative reflected power stays low and consistent over a variety of frequencies.
So:  
| Freq | Reflected Power | 
| ----------- | ----------- | 
| 100mhz |  1w |  
| 200mhz |  1w |  
| 500mhz |  1w |  
| 1ghz |  1w |  


But with an Antenna the level of reflected power is a function of the Frequency, relative to the capabilities of the antenna. So the amount of bad power returning will be higher at non-optimal antenna frequencies and lower for optimal antenna frequencies.

in this case:  
| Freq | Reflected Power |  
| ----------- | ----------- |
| 100mhz |  4w |  
| 200mhz |  <1w |  
| 500mhz |  25w |  
| 1ghz |  50w |  

Real world devices fall in between the two cases of:
- Little impedence variation by frequency
- Large or Irregular impedence variation by frequency

#### Quantifying Reflected Power relative to Forward Power

Two Methods:
- return loss
- VSWR 

*Return Loss* is the difference in dB between the Forward and Reflected power

forward power - return power == return loss

If forward power is 50dBm and reflected power is 10dBm, return loss == 40dB

Larger values for return loss mean the less power is reflected, so we want the value of Return Loss to be as large as possible.

The value must always be a positive number since the level of reflected power is always less than the level of forward power.

Even in the cast where 100% of the forward power is lost, some power will be lost on the path from the source to the load, so reflected power can never be 100%

**standing waves**

Forward signal
Reverse signal
forward + reverse signal - standing wave

VSwR is measure of the highest and lowest ratios in the standing wave.

VSWR = $\frac{Vmax} {Vmin}$

so if Vmax == 3 and Vmin == 1, VSWR == 3


Reflection can be quantified by means of a Reflection Coefficient $\Gamma$

So $\Gamma$ is a function of the Load Impedence $Z_{L}$ and the Source Impedence $Z_{0}$

$\Gamma$ = $\frac{Z_{L} -  Z_{0}} {Z_{L} +  Z_{0}}$

$\Gamma$ is then used to calculate VSWR:

VSWR = $\frac{1 + |\Gamma|} {1 - |\Gamma|}$

VSWR can also be calculated from Return Loss and Vice Versa:

Return Loss = $20log_{10}$$\left \frac{VSWR + 1}{VSWR - 1}\right$

As VSWR increases:
- if $\Gamma$ == 0.0, then the impedences match and there is no reflected power.


| VSWR      | ( $\Gamma$ ) | % of reflected power |
| ----------- | ----------- | ----------- |
| 1.0      | 0.0      | 0.0 |
| 1.5   | 0.200        | 4.0 |
| 2.0 | .333 | 11.1 | 
| 3.0 | .500 | 25.0 | 
| 4.0 | .600 | 36.0| 
| 5.0 | .667 | 44.0| 
| 6.0 | .714 | 51.0| 
| 7.0 | .750 | 56.3 | 
| 8.0 | .778| 60.5 | 
| 9.0 | .800 | 64.0| 
| 10.0 |.818  | 66.9| 
| 15.0 | .875| 76.6| 
| 20.0 |.905 | 81.9| 
 

- VSWR 3 (25% reflected power) - still ok for many applications

Two Special Cases of VSWR:
- short circuit $Z_{L}$ = 0 and $\Gamma$ = -1
- open circuit $Z_{L}$ = $\infty$ and $\Gamma$ = 1 

In both cases VSWR = $\infty$ which means that 100% of the forward power is being reflected back to the source.

### Dealing with Reflected Power

**Matching Network**

In the case:

Source -> Load  
50 + j0 $\Omega$ -> 39 + j6 $\Omega$ 

A Matching Network can be added. Adds Impedences (capacitance and inductance) to "match" source and load impedence.

Source -> Matching Network -> Load
- 23.415nH Inductor + 19.905pF Capacitor


**Foldback**
- reducing forward power also reduces reflected power
    - primarily used in higher power sources like broadband amplifiers
- protects the source from dangerous levels of reflected power
    - can cause performance degredation and sometimes permanent damage

In this case:

Source (max safe reflected power == 40w) 

- At VSWR 1.5 with 100w of Forward Power only 4w will be reflected back to source.
- At VSWR 6, the reflected power of 50w would exceed the safe limit.
    - if this is limited to 80w @ VSWR 6, reflected power is down to 40w - the max safe limit








