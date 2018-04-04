# <img src="https://raw.githubusercontent.com/saleem-hadad/zino/master/assets/button.png" alt="Zino Button class"/> Button

- [نظرة عامة](#overview)
- [مثال تطبيقي](#example)

<a name="overview"></a>
## نظرة عامة

حلّت المكتبة العديد من المشاكل المتعلقة باستخدام الأزرار وسهلت استخدامها, على سبيل المثال: تنبيه المطور بتغير حالة الزر من `low` إلى `high` وأيضاً حلت مشكلة الإرتداد الشهيرة

> {success} يقدم كلاس `Button` سهولة في التعامل مع العوامل الفيزيائية للأزرار على شكل تنبيهات برمجية, مثال: تغير حالة الزر من 0  إلى 1


<a name="example"></a>
## مثال تطبيقي

طباعة جملة `😎 تم ضغط الزر` إلى مدخل الـ `Serial`

    #include <Arduino.h>
    #include <Button.h>
    #include <Pin.h>
    
    Button button;
    
    void buttonPressed()
    {
        Serial.println("😎 تم ضغط الزر");
    }
    
    void setup()
    {
        Serial.begin(9600);
    
        // The 1st parameter: the pin connected with the button
        // The 2nd parameter: the debouncing period [35-40 ms is recommended]
        // The 3rd parameter: true or false [default logic is high?]
        // The 4th parameter: true or false [with internal Pull Up?]
        button.init(Pin(PortB, 5), 40, false, false);
        button.pressed = buttonPressed; // set the handler
    }
    
    void loop()
    {
        button.refresh(); // important
    }
