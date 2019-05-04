# Examples - `Basic`

Here you can find a lot of examples ready to be used in your applications. Enjoy 😎!

---

- [Analog Reading](#analog-reading)
- [Blinky](#blinky)
- [Button](#button)
- [Button and Blinky](#button-and-blinky)
- [Button and LED](#button-and-led)
- [Delay](#delay)
- [DCMotor](#dc-motor)
- [DCMotor Potentiometer](#dc-motor-and-potentiometer)


<a name="analog-reading"></a>
## Analog Reading

```arduino
#include <Arduino.h>
#include <Zino.h>

Pin analogSensorPin = Pin(PortC, 5);

void setup()
{
    Serial.begin(9600);
}

void loop()
{
    Serial.println(
        GPIO::read(analogSensorPin)
    );
}
```

---

<a name="blinky"></a>
## Blinky

```arduino
#include <Arduino.h>
#include <Zino.h>

Blinky leds[4];

void setup()
{
    leds[0].init(Pin(PortB, 0), 600, 650);
    leds[1].init(Pin(PortB, 1), 700, 100);
    leds[2].init(Pin(PortB, 2), 300, 540);
    leds[3].init(Pin(PortB, 3), 100, 100);
}

void loop()
{
    for (int index = 0; index < 4; index++) {
        leds[index].refresh();
    }
}
```

---

<a name="button"></a>
## Button

```arduino
#include <Arduino.h>
#include <Zino.h>

Button button;

void buttonPressed()
{
    Serial.println("Button has been pressed 🤠");
}

void setup()
{
    Serial.begin(9600);
    button.init(Pin(PortB, 5), 40, false, false);
    button.pressed = buttonPressed;
}

void loop()
{
    button.refresh();
}
```

---

<a name="button-and-blinky"></a>
## Button and Blinky

```arduino
#include <Arduino.h>
#include <Zino.h>

Blinky leds[5];
Button button;

void buttonPressed()
{
    Serial.println("Button has been pressed 🔥");
}

void setup()
{
    Serial.begin(9600);

    button.init(Pin(PortB, 5), 40, false, false);
    button.pressed = buttonPressed;

    leds[0].init(Pin(PortB, 0), 600, 650);
    leds[1].init(Pin(PortB, 1), 700, 100);
    leds[2].init(Pin(PortB, 2), 300, 540);
    leds[3].init(Pin(PortB, 3), 100, 100);
    leds[4].init(Pin(PortB, 4), 450, 357);
}

void loop()
{
    for (int index = 0; index < 5; index++) {
        leds[index].refresh();
    }

    button.refresh();
}
```

---

<a name="button-and-led"></a>
## Button and LED

```arduino
#include <Arduino.h>
#include <Zino.h>

Button button;
LED led;

void buttonPressed()
{
    led.toggle();
    // Other methods 👇
    // led.on();
    // led.off();
}

void setup()
{
    button.init(Pin(PortB, 5), 40, false, false);
    button.pressed = buttonPressed;

    led.init(Pin(PortB, 4));
}

void loop()
{
    button.refresh();
}
```

---

<a name="delay"></a>
## Delay

```arduino
#include <Arduino.h>
#include <Zino.h>

Delay myDelay;          // default duration 1000 ms.
// Delay myDelay(1000); //Other initialization

void callback()
{
    Serial.println("delay fired 🔥");
}

void setup()
{
    Serial.begin(9600);
    myDelay.init(500); //duration = 500 ms.

    myDelay.callback = callback;
}

void loop()
{
    myDelay.refresh();
    //Other stuff goes here
}
```

---

<a name="dc-motor"></a>
## DC Motor

```arduino
#include <Arduino.h>
#include <Zino.h>

DCMotor motor;

void setup()
{
    motor.init(Pin(PortB, 4), 200);
    motor.setDutyCycle(0.5); // controlling speed 
}

void loop()
{
    motor.refresh();
}
```

---

<a name="dc-motor-and-potentiometer"></a>
## DC Motor and Potentiometer

```arduino
#include <Arduino.h>
#include <Zino.h>

Pin potentiometer = Pin(PortC, 5);
DCMotor motor;

void setup()
{
    motor.init(Pin(PortB, 4), 150);
    motor.setDutyCycle(0);
}

void loop()
{
    double dutyCycle = double(GPIO::read(potentiometer)) / 1023; // 0.0 <-> 1.0

    motor.setDutyCycle(dutyCycle);
    motor.refresh();
}
```