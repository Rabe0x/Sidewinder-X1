# Sidewinder-X1
I am trying to work out the full potential of the Sidewinder X1. 

## Update buildin Driver to TMC2209
### Driver Type
#### File: Marlin/Configuration.h (Line ~677) 
Change the replaced driver from TMC2100 to TMC2209 (I've used the driver from MKS)

for example:

#define X_DRIVER_TYPE  TMC2209

#define Y_DRIVER_TYPE  TMC2209

#define Z_DRIVER_TYPE  TMC2209

#define Z2_DRIVER_TYPE TMC2209

#define E0_DRIVER_TYPE TMC2209

### Moving Direction
For each replaced driver you need to invert the stepper direction.
#### File: Marlin/Configuration.h (Line ~1085)

X:  from false to true

Y:  from false to true

Z:  from true to false

 
#### File: Marlin/Configuration.h (Line ~1092)
*E0: from false to true


### Sensorless Homing and UART communication
After configurating on your board of choice the Jumper to UART communication 


#### remove Endstops for X and Y
uncomment ENDSTOP_NOISE_THRESHOLD with "//" 
