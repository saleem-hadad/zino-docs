# <img src="https://raw.githubusercontent.com/saleem-hadad/zino/master/assets/Delay.png" alt="Zino Delay class"/> Delay

- [نظرة عامة](#overview)
- [مثال تطبيقي](#example)

<a name="overview"></a>
## نظرة عامة

من المحتمل أنك مررت ببعض المشاكل المتعلقة باستخدام delay في مشاريعك, والتي تسبب في توقف المعالج عن العمل لفترة زمنية محددة وقد تضطر لعمل شيء آخر بالتوازي معها.. لذلك تقدم المكتبة كلاس `Delay` الذي يختلف في طريقة بناؤه عن الطريقة المتوفرة في مكتبة الأردوينو بحيث يتيح لك العمل على أشياء أخرى في ذات الوقت وذلك عن طريق محاكاة التوقيف الزمني بالسوفتوير

> {example} مثلاً قد تود ارسال رسالة نصية كل ثانية بدون أن توقف بقية العمليات الأخرى 

<a name="example"></a>
## مثال تطبيقي

    #include <Arduino.h>
    #include <Delay.h>
    
    Delay myDelay;
    
    void callback()
    {
        // print "Hello world 🖐" every 0.5 s
        Serial.println("Hello world 🖐"); 
    }
    
    void setup()
    {
        Serial.begin(9600);
        myDelay.init(500); // duration = 500 ms. (0.5 s)
    
        myDelay.callback = callback; // set the callback to be notified
    }
    
    void loop()
    {
        myDelay.refresh();
        //Other stuff goes here
    }