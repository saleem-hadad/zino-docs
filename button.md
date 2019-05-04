# <img src="https://raw.githubusercontent.com/saleem-hadad/zino/master/assets/button.png" alt="Zino Button class"/> Button

- [Overview](#overview)
- [Example](#example)

<a name="overview"></a>
## Overview

The library solves some of the common issue when working with push buttons, like edge detection and bouncing problem.

The class ```Button``` provides very easy way to handle physical actions like button pressed event.

<a name="example"></a>
## Example

Print `Button has been pressed 🤠` to the serial when the button pressed.

```arduino
#include <Arduino.h>
#include <Button.h>
#include <Pin.h>

Button button;

void buttonPressed()
{
    Serial.println("Button has been pressed 🤠");
}

void setup()
{
    Serial.begin(9600);

    // The 1st parameter: the pin connected with the button
    // The 2nd parameter: the debouncing period [35-40 ms is recommended]
    // The 3rd parameter: true or false [default logic is high?]
    // The 4th parameter: true or false [with internal Pull Up?]
    button.init(Pin(PortB, 5), 40, false, false);
    button.pressed = buttonPressed; // set the handler
}

void loop()
{
    button.refresh(); // important
}
```
