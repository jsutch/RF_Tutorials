Understanding S parameters  
https://www.youtube.com/watch?v=-Pi0UbErHTY

- A Network is a device with 1 or more ports. 
- Each port can Reflect, Pass, and/or Absorb RF Energy
- Measured by injecting power at one port and simultaneously measuring power appearing at other ports
- The standard way of measuring and denoting these are "S-Parameters".


1, 2, and 3 port networks. Some examples:  
1 port - antenna  
2 port - filter, amplifier  
3 port - directional coupler, mixer  

"S" stands for "Scattering"

Named using capital S and a pair of subscripts (Sxy (or stylized S_{xy}, since I can't use subscript in these notes until they're rendered in Markdown.)  
- first subscript - port where energy emerges (output port)
- second subscript - port where energy enters (input port)

If measuring the amount of energy passing through a 2 port network (input and output) it's referred to as $S_{21}$.  

If measuring the amount of energy reflecting back from the input port, it's referred to as $S_{11}$.  

Forward Port (input) --> Reverse Port (output)

In a two port network there are 4 S parameters:
- $S_{11}$ - amount of incident power that's reflected by the forward port
- $S_{21}$ - amount of power that's transferred from the forward to the reverse port
- $S_{12}$ - opposite of $S_{21}$ - amount of power that's transferred from the reverse back to the forward port
- $S_{22}$ - opposite of $S_{11}$ - amount of incident power that's reflected by the reverse port

can be defined as ratios of the power seen at each port.

S params can be represented by square and NxN matrices where "N" is the Number Of Ports.

e.g.

(These would be a little cleaner with encapsulating parens, but for some reason \left and \right notation isn't working in the VSCode renderer)

one port =  
$S_{11}$ 

two ports =  
$S_{11}, S_{11}$  
$S_{21}, S_{22}$  

three ports = 

$S_{11}, S_{12}, S_{13}$  
$S_{21}, S_{22}, S_{23}$  
$S_{31}, S_{32}, S_{33}$  


S Params are Complex values, consisting of both a Magnitude and a Phase. They can change over frequency.

Reflection Coefficients like $S_{11}, S_{11}$ are often plotted on a Smith Chart

S Params can be cascaded together to predict the overall performance of a system.

Some other common names:

Reflection Coefficients:
Quantified as return loss or VWSR (Voltage Standing Wave Ratio) (vizwarr)
- $S_{11}$ : impedence input match (as return loss or VSWR)
- $S_{22}$ : impedence output match (as return loss or VSWR)

Transmission Coefficients:
- $S_{21}$ - a measure of gain or loss between the input and output ports
- $S_{12}$ - is a measure of Reverse Isolation (how much power is flowing the wrong way)


