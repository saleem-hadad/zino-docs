# <img src="https://raw.githubusercontent.com/saleem-hadad/zino/master/assets/LED.png" alt="Zino LED class"/> LED

- [نظرة عامة](#overview)
- [مثال تطبيقي](#example)

<a name="overview"></a>
## نظرة عامة

التعامل مع الديود الضوئي `LED` أمر مسل, كما في نفس الوقت مفيد لاكتشاف الأخطاء البرمجية وتتبعها, لذلك تقدم المكتبة طريقة لتشغيل وإطفاء أو حتى تغيير حالة الـ LED بشكل بسيط

<a name="example"></a>
## مثال تطبيقي

    #include <Arduino.h>
    #include <Pin.h>
    #include <LED.h>
    
    Pin ledPin(PortB, 4); // same as digital pin 12
    LED led;
    
    void setup()
    {
        led.init(ledPin);
    }
    
    void loop()
    {
        led.on();
        led.off();
        // or
        led.toggle();
    }
