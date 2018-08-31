# <img src="https://raw.githubusercontent.com/saleem-hadad/zino/master/assets/GPIO.png" alt="Zino GPIO class"/> GPIO

- [Overview](#overview)
- [Example 1](#example1)
- [Example 2](#example2)

<a name="overview"></a>
## Overview

The library has its own ```GPIO``` wrapper(class) to use, which is much more faster than the Arduino library. [See the comparison](https://github.com/saleem-hadad/zino/blob/master/examples/CompareFrequencies/CompareFrequencies.cpp).

<a name="example1"></a>
## Example 1

Blinking LED on and off without delay.

```arduino
#include <GPIO.h>
#include <Pin.h>

Pin redLedPin(PortB, 0);

void setup()
{
    // You can choose Output, Input or InputWithPullUp
    GPIO::setup(redLedPin, Output);
}

void loop()
{
    GPIO::high(redLedPin);      // Turn on the LED
    GPIO::low(redLedPin);       // Turn off the LED
    //or
    GPIO::write(redLedPin, 1);  // Turn on the LED
    GPIO::write(redLedPin, 0);  // Turn off the LED
} 
```

<a name="example2"></a>
## Example 2

Reading analog input from PortC, pin number 4 and print the result to the serial.

```arduino
#include <Arduino.h>
#include <GPIO.h>
#include <Pin.h>

Pin temperatureSensorPin(PortC, 4);

void setup()
{
    Serial.begin(9600);
}

void loop()
{
    // For analog reading you don't have to call GPIO::setup method :)
    int temperature = GPIO::read(temperatureSensorPin);
    Serial.println(temperature);
}
```