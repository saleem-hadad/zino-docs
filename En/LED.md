# <img src="https://raw.githubusercontent.com/saleem-hadad/zino/master/assets/LED.png" alt="Zino LED class"/> LED

- [Overview](#overview)
- [Example](#example)

<a name="overview"></a>
## Overview

LEDs are the fun things to play with 🤓, for that, the ```LED``` class handles some cool features that you might need to control the LEDs very easily.

<a name="example"></a>
## Example

```arduino
#include <Arduino.h>
#include <Pin.h>
#include <LED.h>

Pin ledPin(PortB, 4); // same as: Pin ledPin(12);
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
```