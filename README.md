# Rigol924s-ARB-file
example files of arbitrairy function for the generator

Some example files that works with the Rigol DHHO924s

basic example is a simple sine wave.
all files must have 8192 points. 
all value are in volt 
voltage beyond +-0.312 Volt seems clipped. 
format is header than a list of voltaqge point in vertical list without the time coordinate!
volts can be fix or sci notation and always after comma without time    
,YYY

Header must be in form: 


RIGOL:DG1:CSV DATA FILE
TYPE:Arb
AMP:0.647 Vpp
PERIOD:2.00E-7 S
DOTS:8192
MODE:Freq
AFG Frequency:5.0E6
AWG N:0
x,y[V]
,0.0024
,0.0048
,0.0072
,0.0096
...

at least one empty line at the end of file


table can be generated with any shape. 
the maximum rate of output of the table is 10mhz.  so if you encode a 1 sine wave cycle, it output a 10mhz signal.
while intrinsec generator is sine, square , triangle up to 25mhz. 

one usefull shape is a five sine cycle with header base frequency of 10mHz which gives an output of 50Mhz with at least 30db of shape noise
more cycle than that is not giving usefull signal without strong deformation or instability

file can be .txt or .csv

param in the header are read to initialise the generator.
period and frequency must be consistent. 
period is the duration of the generated voltage table.
if only one cycle sine is present, then this gives directly the frequency

amp is the expected pk-pk amplitude. 
behavioir is strange   
putting table with more than 0.647 V give a clipped waveform. 
this is why I max out at +-0.312 V in the table.
