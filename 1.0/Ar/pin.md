# Pin

- [Overview](#overview)
- [Example](#example)

<a name="overview"></a>
## Overview

The library introduces this new concept of shaping the pin as an object which has a port address and pin number.

The `Pin` class used in many different other classes to handle the process of assigning the pin either `Output`, `Input` or `InputWithPullUp` resister.

> {tip}The reason for using Pin class instead of the pin number as Arduino library uses is first for educational purpose where the students can get a clue of the register concept and also to make the code very clean and organised. However, the library also supports the pin number method if you still like it 👍


<a name="example"></a>
## Example

    #include <Pin.h>
    
    /* 
    portName: PortB, pinNumber: 0 
    Same as digital pin 8
    */
    Pin redLedPin(PortB, 0);
    
    /* 
    portName: PortD, pinNumber: 1 
    Same as digital pin 1
    */
    Pin greenLedPin(PortD, 1);
    
    /* 
    portName: PortC, pinNumber: 4 
    Same as analog pin A4
    */
    Pin temperatureSensorPin(PortC, 4); 
