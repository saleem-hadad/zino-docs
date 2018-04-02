# Ultrasonic

- [Overview](#overview)
    - [Sleep](#sleep)
    - [Deep Sleep](#deep-sleep)
- [Example](#example)

<a name="overview"></a>
## Overview

The ```PowerManager``` class used to reduce the power consumption by the Arduino chip, *[please refer to this article to understand the Arduino power management before you use this class](https://playground.arduino.cc/Learning/ArduinoSleepCode)*. There are two static methods available:

<a name="sleep"></a>
> {example}Sleep

+ Turning off ADC
+ Turning off Analog Comparator
+ Sleep with power-down mode


<a name="deep-sleep"></a>
> {example}Deep Sleep

+ BOD disabled
+ BOD sleep enable
+ Turning off ADC
+ Turning off Analog Comparator
+ Sleep with power-down mode

<a name="example"></a>
## Example

    #include <Arduino.h>
    #include <PowerManager.h>
    
    void setup()
    {
        PowerManager::sleep();
        // or
        PowerManager::deepSleep();
    }
    
    void loop()
    {
        //
    }