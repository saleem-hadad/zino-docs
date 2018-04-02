# Blinky

- [Overview](#overview)
- [Example](#example)

<a name="overview"></a>
## Overview

The ```Blinky``` class provides an easy way for blinking(flashing) LEDs, generating a square wave or controlling DC motors.. etc.

<a name="example"></a>
## Example

Blinking an LED connected to PortB on pin 0 (same as digital pin 8) for a period of 1000ms on and 100ms off, without using the delay Arduino library's function, and without affecting other codes

    #include <Arduino.h>
    #include <Blinky.h>
    #include <Pin.h>
    
    Blinky led;
    
    void setup()
    {
        led.init(Pin(PortB, 0), 1000, 100); // (pin, onTime, offTime)
    }
    
    void loop()
    {
        led.refresh();
    }