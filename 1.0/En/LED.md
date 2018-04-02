# LED

- [Overview](#overview)
- [Example](#example)

<a name="overview"></a>
## Overview

LEDs are the fun things to play with 🤓, for that, the ```LED``` class handles some cool features that you might need to control the LEDs very easily.

<a name="example"></a>
## Example

    #include <Arduino.h>
    #include <Pin.h>
    #include <LED.h>
    
    Pin ledPin(PortB, 4); // same as digital pin 12
    LED led;
    
    void setup()
    {
        led.init(ledPin);
    }
    
    void loop()
    {
        led.on();
        led.off();
        // or
        led.toggle();
    }
