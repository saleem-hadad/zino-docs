# <img src="https://raw.githubusercontent.com/saleem-hadad/zino/master/assets/Blinky.png" alt="Zino Blinky class"/> Blinky

- [نظرة عامة](#overview)
- [مثال تطبيقي](#example)

<a name="overview"></a>
## نظرة عامة

تقدم المكتبة كلاس `Blinky` والذي يمكن استخدامه لأكثر من تطبيق, على سبيل المثال ومض LED أو حتى إصدار إشارات مربعة الشكل square wave

<a name="example"></a>
## مثال تطبيقي

ومض LED موصول بالمخرج 8 على لوحة الأردوينو بحيث يتم تشغيله لمدة ثانية ومن ثم إطفاؤه لمدة 0.1 ثانية وذلك بدون استخدام دالة delay الموجودة ضمن مكتبة الأردوينو

    #include <Arduino.h>
    #include <Blinky.h>
    #include <Pin.h>
    
    Blinky led;
    
    void setup()
    {
        led.init(Pin(8), 1000, 100); // (pin, onTime, offTime)
    }
    
    void loop()
    {
        led.refresh();
    }