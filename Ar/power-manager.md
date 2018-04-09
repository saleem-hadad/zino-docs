# <img src="https://raw.githubusercontent.com/saleem-hadad/zino/master/assets/PowerManager.png" alt="Zino PowerManager class"/> Power Manager

- [نظرة عامة](#overview)
    - [النوم](#sleep)
    - [النوم العميق](#deep-sleep)
- [مثال تطبيقي](#example)

<a name="overview"></a>
## نظرة عامة

> {tip} يمكنك الاطلاع على المقالة التالية إن كنت تود فهم طريقة عمل الكلاس. [من هنا](https://playground.arduino.cc/Learning/ArduinoSleepCode)

يوفر كلاس `PowerManager` طريقة مبسطة للتقليل من استهلاك متحكم الأردوينو للطاقة الكهربائية في حال عدم استخدام المصادر وذلك إما باستخدام النوم العادي أو النوم العميق.


<a name="sleep"></a>
> {example}النوم

+ Turning off ADC
+ Turning off Analog Comparator
+ Sleep with power-down mode


<a name="deep-sleep"></a>
> {example}النوم العميق

+ BOD disabled
+ BOD sleep enable
+ Turning off ADC
+ Turning off Analog Comparator
+ Sleep with power-down mode

<a name="example"></a>
## مثال تطبيقي

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