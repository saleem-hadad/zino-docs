# Examples - `Intermediate`

Here you can find a lot of examples ready to be used in your applications. Enjoy 😎!

---

- [Multiple DC Motors](#multi-dc-motors)
- [DC Motor and Delay](#dc-motor-and-delay)
- [Ultrasonic](#ultrasonic)
- [Ultrasonic and Delay](#ultrasonic-and-delay)

<a name="multi-dc-motors"></a>
## Multiple DC Motors

```arduino
#include <Arduino.h>
#include <Zino.h>

DCMotor motors[4];

void setup()
{
    motors[0].init(Pin(PortB, 4), 150);
    motors[0].setDutyCycle(0.3);

    motors[1].init(Pin(PortB, 3), 150);
    motors[1].setDutyCycle(0.5);

    motors[2].init(Pin(PortB, 2), 150);
    motors[2].setDutyCycle(0.8);

    motors[3].init(Pin(PortB, 1), 150);
    motors[3].setDutyCycle(1);
}

void loop()
{
    motors[0].refresh();
    motors[1].refresh();
    motors[2].refresh();
    motors[3].refresh();
}
```

---

<a name="dc-motor-and-delay"></a>
## DC Motor and Delay

```arduino
#include <Arduino.h>
#include <Zino.h>

Delay myDelay(1000);
DCMotor motor;
double dutyCycle = 0;

void callback()
{
    motor.setDutyCycle(dutyCycle);
    dutyCycle += 0.1; // Increase the dutyCycle by 0.1 each 1s
    if(dutyCycle > 1) dutyCycle = 0;
}

void setup()
{
    motor.init(Pin(PortB, 4), 150);
    motor.setDutyCycle(0);

    myDelay.callback = callback;
}

void loop()
{
    myDelay.refresh();
    motor.refresh();
}
```

---

<a name="ultrasonic"></a>
## Ultrasonic

```arduino
#include <Arduino.h>
#include <Zino.h>

Pin trig(PortB, 3);
Pin echo(PortB, 4);

Ultrasonic ultrasonic;

void setup()
{
    Serial.begin(9600);

    ultrasonic.init(trig, echo);
    ultrasonic.setMeasurementUnit(MeasurementUnit::MM); // Optional: default is CM
}

void loop()
{
    Serial.println( ultrasonic.sense() );
}
```

---

<a name="ultrasonic-and-delay"></a>
## Ultrasonic and Delay

```arduino
#include <Arduino.h>
#include <Zino.h>

Pin trig(PortB, 3);
Pin echo(PortB, 4);

Ultrasonic ultrasonic;
Delay myDelay;

void callback()
{
    Serial.println( ultrasonic.sense() );
}

void setup()
{
    Serial.begin(9600);

    myDelay.callback = callback;

    ultrasonic.init(trig, echo);
}

void loop()
{
    myDelay.refresh();
}
```