# <img src="https://raw.githubusercontent.com/saleem-hadad/zino/master/assets/DCMotor.png" alt="Zino DCMotor class"/> DC Motor

- [Overview](#overview)
- [Example](#example)

<a name="overview"></a>
## Overview

> {note}This class still in development

Controlling DC Motors needs a lot of hardware and software configurations to be handled. 
However, ```DCMotor``` class provides a convenient way of controlling the DC motors by
generating a software PWM signal on any digital pin and not only the timers ones 
(with [~] label), which means you can control the dc motor by any digital pin 😎

<a name="example"></a>
## Example

    #include <Arduino.h>
    #include <DCMotor.h>
    #include <Pin.h>
    
    DCMotor motor;
    
    void setup()
    {
        // provide the pin and frequency(in hz) needed
        motor.init(Pin(PortB, 4), 200);
        
        // control the speed by adjusting the dutyCycle between 0.0 and 1.0
        motor.setDutyCycle(0.5);
    }
    
    void loop()
    {
        motor.refresh();
    }