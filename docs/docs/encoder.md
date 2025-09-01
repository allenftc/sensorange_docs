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

## CAD and Drawings
[CAD Link (Onshape)↗](https://cad.onshape.com/documents/17b4dcf69571843c27329307/w/e1b88a356c959f37899eb8e6/e/c158a022034ba6101b0b01ff){target=blank}
<br>
[Dimension Drawing (pdf)](../assets/encoderdrawing.pdf){:download}


 

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
