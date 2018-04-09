# <img src="https://raw.githubusercontent.com/saleem-hadad/zino/master/assets/Ultrasonic.png" alt="Zino Ultrasonic class"/> Ultrasonic

- [نظرة عامة](#overview)
    - [معلومات نظرية](#theoretical-information)
    - [معلومات تقنية](#technical-information)
- [مثال تطبيقي](#example)

<a name="overview"></a>
## مثال تطبيقي

<a name="theoretical-information"></a>
> {example}معلومات نظرية

طريقة عمل الحساس

+ يرسل مخرج الـ trig ومضات لتصطدم بالأجسام المقابلة وتعود عبر مدخل الـ echo
+ يتم قياس المسافة من خلال المعادلة التالية: المسافة = السرعة ÷ الزمن
+ طالما أن حالة المدخل high فذلك يعطي إشارة بوجود جسم مقابل قريب للحساس

<a name="technical-information"></a>
> {example}معلومات تقنية

يحيط كلاس `Ultrasonic` بأغلب العمليات اللازمة لتحديد المسافة بين الحساس وبين الجسم المقابل وذلك من خلال تضمينها في فنكشن `sense` والتي تعود بالمسافة المقاسة تبعاً لوحدة القياس المحددة مسبقاً.

> {tip} يوفر الكلاس أيضا إمكانية تغيير وحدة القياس إلى أي من cm, mm, m وذلك من خلال فنكشن `setMeasurementUnit`

<a name="example"></a>
## مثال تطبيقي

طباعة المسافة المقروءة من الحساس بوحدة ال cm إلى الـ Serial

    #include <Ultrasonic.h>
    #include <Pin.h>
    
    Pin trig(PortB, 3);
    Pin echo(PortB, 4);
    
    Ultrasonic ultrasonic;
    
    void setup()
    {
        Serial.begin(9600);
        ultrasonic.init(trig, echo);
    }
    
    void loop()
    {
        Serial.println( ultrasonic.sense() );
    }