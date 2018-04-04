# <img src="https://raw.githubusercontent.com/saleem-hadad/zino/master/assets/GPIO.png" alt="Zino GPIO class"/> GPIO

- [نظرة عامة](#overview)
- [مثال تطبيقي 1](#example1)
- [مثال تطبيقي 2](#example2)

<a name="overview"></a>
## نظرة عامة

 تمتلك المكتبة كلاس `GPIO` للتعامل مع مدخلات ومخرجات متحكم `Atmega32` والذي يتفوق في سرعته على التوابع  الموجودة ضمن مكتبة الأردوينو مثل `digitalWrite`


> {tip} يمكنك الإطلاع على نتائج المقارنة بين كلاس `GPIO ` والتوابع الموجودة ضمن مكتبة الأردوينو [من هنا](https://github.com/saleem-hadad/zino/blob/master/examples/CompareFrequencies/CompareFrequencies.cpp).

<a name="example1"></a>
## مثال تطبيقي 1

تشغيل وإطفاء `LED` بدون توقف زمني.

    #include <GPIO.h>
    #include <Pin.h>
    
    Pin redLedPin(PortB, 0);
    
    void setup()
    {
        // You can choose Output, Input or InputWithPullUp
        GPIO::setup(redLedPin, Output);
    }
    
    void loop()
    {
        GPIO::high(redLedPin);      // Turn on the LED
        GPIO::low(redLedPin);       // Turn off the LED
        //or
        GPIO::write(redLedPin, 1);  // Turn on the LED
        GPIO::write(redLedPin, 0);  // Turn off the LED
    } 

<a name="example2"></a>
## مثال تطبيقي 2

قراءة القيم المتغيرة من مدخل 4 على البورت C ومن ثم طباعة النتيجة إلى الـ Serial


    #include <Arduino.h>
    #include <GPIO.h>
    #include <Pin.h>
    
    Pin temperatureSensorPin(PortC, 4);
    
    void setup()
    {
        Serial.begin(9600);
    }
    
    void loop()
    {
        // For analog reading you don't have to call GPIO::setup method :)
        int temperature = GPIO::read(temperatureSensorPin);
        Serial.println(temperature);
    }