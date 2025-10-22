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
[Dimension Drawing (pdf)](../assets/encoderdrawing.pdf){:download="drawing"}
 

## Analog Usage
To use the encoder, configure it as an Analog Input device in the hardware map. Each analog port has two channels, and the encoder outputs on both of them (for example, plugging into the first port would give a reading on both port 0 and port 1). The analog output of the encoder scales the voltage nominally from 0.043V to 3.1V as specced by the chip. To measure angle accurately in code, please reference the code below. 
``` java
//Initialization Code
AnalogInput encoder = hardwareMap.get(AnalogInput.class, "encoder");
double offset = 0;

//Run in Loop
double angle = AngleUnit.normalizeDegrees((encoder.getVoltage()-0.043)/3.1*360 + offset);
```

## Repair
There have been reports of the original design of the encoder having issues with the core falling out (On orders placed before 10/21). If this happens or you want to ensure it doesn't happen, you can follow the guide here. 
### Required Materials: 
3D Printer (0.2mm nozzle is preferred, but 0.4mm nozzle will work)
Super Glue
Small Phillips Screwdriver

First, print out the replacement parts. Note that these have no built in tolerances, which vary from material to material. For Polymaker's PolySonic PLA Pro, I use 0.125mm XY hole compensation and -0.025mm XY contour compensation in OrcaSlicer/Bambu Studio.


[CaseMiddle.step](../assets/CaseMiddle.step){:download="Case Middle.step"}

[MagnetHolder.step](../assets/MagnetHolder.step){:download="Magnet Holder.step"}

Next, remove the 4 screws holding the encoder together.

After all the screws are removed, you should be able to separate the encoder into the 3 case parts, and the core. If the magnet is still on the core, you will need to use some force to break it off. If it has already broken, then you can scrape off residue from the old core.

Get the new core and apply super glue to the inner corner of the core, then press the magnet on.

Find the middle part of the case, and replace it with your new one.

After this, you can reassemble the encoder, and it should be a lot stronger.


## Quadrature Usage
NO
