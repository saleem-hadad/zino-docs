# <img src="https://raw.githubusercontent.com/saleem-hadad/zino/master/assets/AnalogComparator.png" alt="Zino AnalogComparator class"/> Analog Comparator

- [نظرة عامة](#overview)
- [مثال تطبيقي](#example)

<a name="overview"></a>
## نظرة عامة

متحكم الـ Atmega328 أو مايعرف باسم الاردوينو يحتوي على مقارن للإشارات التماثلية.
والذي يمكن استخدامه في مقارنة الإشارة التماثلية القادمة كمدخل للأردوينو مع مستوى رقمي معين يمكن تحديده.

الفولت القادم عبر المدخل AIN0 "المدخل الموجب" للمقارن هو المدخل رقم 6 على لوحة الأردوينو والمدخل رقم 7 يمثل المستوى المطلوب للمقارنة معه.

> {example} لكن ماهي فائدة هذه الطريقة عوضاً عن المداخل التماثلية؟

يعتبر المقارن التماثلي المضمن بلوحة الأردوينو أسرع بكثير من استخدام المداخل التماثلية للمقارنة ADC والتي تستنزف الكثير من الطاقة مقارنة بالمقارن التماثلي, لكن تذكر أنه لايمكنك استخدام هذا المقارن لاكثر من شيء في آن واحد!

<a name="example"></a>
## مثال تطبيقي

    #include <AnalogComparator.h>
    
    AnalogComparator comparator;
    
    void comparatorCallback(bool aboveThreshold)
    {
        /*
            1. if the voltage supplied to pin D7 > D6(either internal bandgab or custom reference): the aboveThreshold value is true
            2. if the voltage supplied to pin D7 < D6(either internal bandgab or custom reference): the aboveThreshold value is false
        */
    
        // your logic goes here
    }
    
    void setup()
    {
        comparator.init(true, true);              // enabled, bandgabSelected
        comparator.callback = comparatorCallback; // important
    }
    
    void loop()
    {
        comparator.refresh();
    }