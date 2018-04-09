# <img src="https://raw.githubusercontent.com/saleem-hadad/zino/master/assets/Ultrasonic.png" alt="Zino Ultrasonic class"/> Ultrasonic

- [Overview](#overview)
    - [Theoretical information](#theoretical-information)
    - [Technical information](#technical-information)
- [Example](#example)

<a name="overview"></a>
## Overview

<a name="theoretical-information"></a>
> {example}Theoretical Information

Ultrasonic is an adjective referring to ultrasound.
Ultrasound and ultrasonic may also refer to: Medical ultrasonography, an ultrasound-based diagnostic imaging technique. Ultrasound (band), a rock band.

Working principal:

1. Trig send the Ping signal to the sensor so that the sensor start giving the pulse to measure the distance.
2. Echo get the reflection of the ultrasonic wave.
3. As long as reflection signal is High it means there is an object.

<a name="technical-information"></a>
> {example}Technical Information

The Zino library encapsulates the essential methods needed to measure the distance from an ultrasonic sensor in the ```Ultrasonic``` class, all you have to do is to call the ```sense``` method which will return back the measured distance according to the subjected ```MeasurementUnit```, which is by default in cm.

<a name="example"></a>
## Example

    #include <Ultrasonic.h>
    #include <Pin.h>
    
    Pin trig(PortB, 3);
    Pin echo(PortB, 4);
    
    Ultrasonic ultrasonic;
    
    void setup()
    {
        Serial.begin(9600);
        ultrasonic.init(trig, echo);
        ultrasonic.setMeasurementUnit(MeasurementUnit::MM); // Optional: default is CM
    }
    
    void loop()
    {
        Serial.println( ultrasonic.sense() );
    }