# <img src="https://raw.githubusercontent.com/saleem-hadad/zino/master/assets/PowerManager.png" alt="Zino PowerManager class"/> Power Manager

The ```PowerManager``` class used to reduce the power consumption by the Arduino chip, *[please refer to this article to understand the Arduino power management before you use this class](https://playground.arduino.cc/Learning/ArduinoSleepCode)*. There are two static methods available:

---

- [Modes](#modes)
- [Example](#example)

<a name="modes"></a>
## Modes

<larecipe-badge type="success" class="pl-3 pr-3 pt-2 pb-2 ml-3 mb-3">Sleep</larecipe-badge>

+ Turning off ADC
+ Turning off Analog Comparator
+ Sleep with power-down mode


<larecipe-badge type="success" class="pl-3 pr-3 pt-2 pb-2 ml-3 mb-3">Deep Sleep</larecipe-badge>

+ BOD disabled
+ BOD sleep enable
+ Turning off ADC
+ Turning off Analog Comparator
+ Sleep with power-down mode

<a name="example"></a>
## Example

```arduino
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
```