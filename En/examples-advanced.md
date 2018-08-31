# Examples - `Advanced`

Here you can find a lot of examples ready to be used in your applications. Enjoy 😎!

---


- [Analog Comparator](#analog-comparator)
- [Power Manager](#power-manager)
- [Compare Frequencies](#compare-frequencies)


<a name="analog-comparator"></a>
## Analog Comparator

```arduino
#include <Arduino.h>
#include <Zino.h>

Blinky led;
AnalogComparator comparator;

void comparatorCallback(bool aboveThreshold)
{
    if (! aboveThreshold) { return; }

    //blink LED only if the comparatorOutput aboveThreshold
    led.refresh();
}

void setup()
{
    comparator.init(true, true);              //enabled, bandgabSelected
    comparator.callback = comparatorCallback; // very important
    led.init(Pin(PortB, 0), 600, 650);
}

void loop()
{
    comparator.refresh();
}
```

---

<a name="power-manager"></a>
## Power Manager

```arduino
#include <Arduino.h>
#include <Zino.h>

void setup()
{
    PowerManager::sleep();
    // or
    PowerManager::deepSleep();
}

void loop()
{
    // not used in this example
}
```

---

<a name="compare-frequencies"></a>
## Compare Frequencies

```arduino
#include <Arduino.h>
#include <Zino.h>

Pin ledPin = Pin(PortB, 0);
LED led;

void setup()
{
    led.init(ledPin);

    while(1)
    {
        // freq. ~= 147 Khz
        digitalWrite(8, 1);
        digitalWrite(8, 0);

        // freq. ~= 200 Khz
        led.toggle();

        // freq. ~= 440 Khz
        GPIO::write(ledPin, 1);
        GPIO::write(ledPin, 0);
    }
}

void loop()
{
    // not used in this example
}
```