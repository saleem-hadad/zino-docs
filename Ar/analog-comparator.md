# <img src="https://raw.githubusercontent.com/saleem-hadad/zino/master/assets/AnalogComparator.png" alt="Zino AnalogComparator class"/> Analog Comparator

- [Overview](#overview)
- [Example](#example)

<a name="overview"></a>
## Overview

The Atmega328 chip has a built-in analog comparator. That is, it can give a high output when an incoming voltage passes a threshold.

The incoming voltage is on the AIN0 (positive terminal) pin which is pin 12 on the actual chip, and D6 on the Arduino board. The reference voltage (negative terminal) pin is pin 13 on the chip, and D7 on the Arduino.

This is faster than doing an ADC (analog to digital) comparison because it is comparing to a single voltage, not attempting to do a full conversion (which can take almost 104 uS).

> {tip}You can select the internal bandgab (1.1 v) as the positive terminal (D6) and use the navigate terminal as your input to compare. However, if you don't want to use the internal bandgab, you have to supply the voltage (0-5 v) reference on pin D6.

<a name="example"></a>
## Example

    #include <AnalogComparator.h>
    
    AnalogComparator comparator;
    
    void comparatorCallback(bool aboveThreshold)
    {
        /*
            1. if the voltage supplied to pin D7 > D6(either internal bandgab or custom reference): the aboveThreshold value is true
            2. if the voltage supplied to pin D7 < D6(either internal bandgab or custom reference): the aboveThreshold value is false
        */
    
        // your logic goes here
    }
    
    void setup()
    {
        comparator.init(true, true); // enabled, bandgabSelected
        comparator.callback = comparatorCallback; // important
    }
    
    void loop()
    {
        comparator.refresh();
    }