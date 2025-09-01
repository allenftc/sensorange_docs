# Encoder
The [sensOrange Encoder](https://sensorangerobotics.com/product/encoder) is a very compact and versatile angle sensor.

## Specs
- 24x24x6mm
- 7mm hex bore to interface with GoBilda 8mm REX
- 16x16 M4 mounting pattern

## Features

- Absolute Analog and Relative Quadrature output
- Differential Hall sensing for stray magnetic field immunity
- 100HZ update rate to reduce noise and match REV Control Hub polling rate
 

## Analog Usage
The analog output of the encoder scales the voltage from 0.05V to 3.19V to mitigate the effects of variation in the digital-to-analog converter. To measure angle accurately in code, please reference the code below. 
``` java
//Initialization Code
AnalogInput encoder = hardwareMap.get(AnalogInput.class, "encoder");

//Run in Loop
double angle = (encoder.getVoltage()-0.05)/3.142*360;
```

## Quadrature Usage
Coming soon...
