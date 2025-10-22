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
- TVS diode for ESD protection

### Note
- This encoder is designed for use on an already supported shaft. Please do not put excessive loads on it, especially axial loads.

## CAD and Drawings
[CAD Link (Onshape)↗](https://cad.onshape.com/documents/17b4dcf69571843c27329307/w/e1b88a356c959f37899eb8e6/e/c158a022034ba6101b0b01ff){target=blank}
<br>
[Dimension Drawing (pdf)](../assets/encoderdrawing.pdf){:download}


 

## Analog Usage
The analog output of the encoder scales the voltage nominally from 0.043V to 3.1V as specced by the chip. To measure angle accurately in code, please reference the code below. 
``` java
//Initialization Code
AnalogInput encoder = hardwareMap.get(AnalogInput.class, "encoder");
double offset = 0;

//Run in Loop
double angle = AngleUnit.normalizeDegrees((encoder.getVoltage()-0.043)/3.1*360 + offset);
```

## Quadrature Usage
NO
