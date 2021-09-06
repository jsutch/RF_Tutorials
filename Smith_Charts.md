# Smith Charts

https://www.youtube.com/watch?v=rUDMo7hwihs


Named after Philip Hagar Smith, first described in January 1939
http://smithchart.org/phsmith.shtml

- Has many applications.
- the most common are impedence matching and the design of matching networks
- pre-computers this was an intensive process
- the Smith Chart lets you solve the problem graphically with a compass, ruler and pencil
- still useful to help visualize complex impedences, especially as a function of frequency.
- widely used when tuning or verifying the performance of networks


A Smith Chart:
- used when making 1 Port measurements (reflection coefficients e.g. $S_{xy})
- Shows $Z_{L}$ relative to $Z_{0}$
- can be used as
    - a single point
    - traces (impedance as a function of frequency)
- essentially bends the right hand side of a cartesian coordinate plane 
    -  this side is all that would be used in measurement
    - postitive and negative reactance axes (top and bottom half circles) bend around to meet the resistance axis (horizontal/x axis)
    - top half is the Inductive region
    - bottom half is the Capacitative region
    - horizontal (x-axis) is the resistive axis
- A complex impedence appears as a point on a Smith Chart

### layout

Prime Center
- Point in the middle of chart
- corresponds to the source impedence $Z_{0}$ and a VSWR of 1
- in most RF systems the source is purely resistive 50 $\Omega$ load
- using the Smith Chart this value is normalized to 1.0
- 50 $\Omega$ / 50 == 1
- if the point moves to the right along the resistive axis to 2.0, this corresponds to a resistive value of 2 * 50 or 100 $\Omega$. 
- moving the point to 4.0 would increase the resistive value to 4 * 50 or 200 $\Omega$. 
- All Values on the Smith Chart are normalized by the same Prime Center value.
    - This allows the Chart to be used regardless of impedence (50 $\Omega$  or 75 $\Omega$ etc) 


Significance of the Prime Center:
- ideally $Z_{L}$ = $Z_{0}$ ("matched")
- $Z_{0}$ is always the Prime Center.
- Measured $Z_{L}$ is plotted on the Smith Chart
- The closer the values are to the center the better the impedence match 
- the farther away the values to the center, the higher the degree of mismatch
- when viewing a trace (many points):
    - the load is resonant at the frequency where the trace moves through the center


Reistive Axis:
- left of prime center decreases until 0 on the outer edge - A Short Circuit 
- right of prime center increases until the outer edge where it reaches $\infty$ - an Open Circuit
- therefore VSWR is $\infty$ on either end of the resistive axis. 100% reflected power
- 