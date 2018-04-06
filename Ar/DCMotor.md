# <img src="https://raw.githubusercontent.com/saleem-hadad/zino/master/assets/DCMotor.png" alt="Zino DCMotor class"/> DC Motor

- [نظرة عامة](#overview)
- [مثال تطبيقي](#example)

<a name="overview"></a>
## نظرة عامة

> {note}لايزال هذا الكلاس في طور التطوير

التحكم في المحركات عادة مايتطلب الكثير من التجهيزات في كل من الهادوير والسوفتوير, لذلك تقدم المكتبة كلاس `DCMotor` لتسهيل التعامل مع المحركات والتحكم بها.

الكلاس يقدم طريقة مختلفة عن طريقة مكتبة الأدروينو بحيث يمكنك تشغيل المحركات على أي مخرج من مخارج المتحكم على عكس الموجودة ضمن مكتبة الأردوينو والتي تسمح لك التحكم بالمحركات فقط عن طريق المخارج التي عُلمت بالعلامة ~

<a name="example"></a>
## مثال تطبيقي

    #include <Arduino.h>
    #include <DCMotor.h>
    #include <Pin.h>
    
    DCMotor motor;
    
    void setup()
    {
        // provide the pin and frequency(in hz) needed
        motor.init(Pin(PortB, 4), 200);
        
        // control the speed by adjusting the dutyCycle between 0.0 and 1.0
        motor.setDutyCycle(0.5);
    }
    
    void loop()
    {
        motor.refresh();
    }