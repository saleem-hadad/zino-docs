# <img src="https://raw.githubusercontent.com/saleem-hadad/zino/master/assets/Delay.png" alt="Zino Delay class"/> Delay

- [Overview](#overview)
- [Example](#example)

<a name="overview"></a>
## Overview

Most probably you came across this issue when you deal with the delay 
function that Arduino library provides, which halts the CPU for 
specific period in ms. However, you might need to perform an 
action with delay without delaying the whole process. 
For example, you might need to send a message to the serial port 
every 1s without affecting other functionalities! for that, the 
Zino library provides an alternative way for using the delay function.

<a name="example"></a>
## Example

```arduino
#include <Arduino.h>
#include <Delay.h>

Delay myDelay;

void callback()
{
    // print "Hello world 🖐" every 0.5 s
    Serial.println("Hello world 🖐"); 
}

void setup()
{
    Serial.begin(9600);
    myDelay.init(500); // duration = 500 ms. (0.5 s)

    myDelay.callback = callback; // set the callback to be notified
}

void loop()
{
    myDelay.refresh();
    //Other stuff goes here
}
```