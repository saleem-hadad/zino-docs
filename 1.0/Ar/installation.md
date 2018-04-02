# تحميل المكتبة

- [تحميل المكتبة](#installation)
    - [باستخدام Atom](#using-atom-vscode)
    - [باستخدام Arduino IDE](#using-arduino-ide)
- [اللوحات المدعومة](#supported-boards)
- [رخصة الاستخدام](#license)

<a name="installation"></a>
## تحميل المكتبة

> {tip}أنصح باستخدام محرر النصوص [`Atom`](https://atom.io/) أو [`VSCode`](https://code.visualstudio.com/) مع [`Platform IO`](http://platformio.org/platformio-ide) للحصول على بيئة تطوير أفضل من استخدام محرر الاردوينو العادي

<a name="using-atom-vscode"></a>
### باستخدام Atom/VSCode

اذا كنت تفضل استخدام احدى هذين المحررين فلديك طريقتين لتحميل المكتبة

**الطريقة الأولى** (موصى بها✌️)

    pio lib install zino
    
**الطريقة الثانية**

أنشأ مشروعاً جديداً في Platform IO ثم [حمل المكتبة](https://github.com/saleem-hadad/zino/archive/master.zip) وقم باستخراج الملفات إلى مجلد `lib`


<a name="using-arduino-ide"></a>
### باستخدام Arduino IDE

> {note}لم أقم بتجربة المكتبة على محرر الأردوينو لذلك إن واجهت مشاكل في استخدامها فضلاً قم بتنبيهي!

1. [حمل المكتبة](https://github.com/saleem-hadad/zino/archive/master.zip) 
2. Arduino IDE > ```sketch``` > ```include Library``` > add .Zip library

<a name="supported-boards"></a>
## اللوحات المدعومة

+ ### UNO

<a name="license"></a>
## رخصة الاستخدام

هذه المكتبة مرخصة تحت رخصة MIT. يمكنك الاطلاع على التفاصيل أكثر [LICENSE.md](https://github.com/saleem-hadad/zino/blob/master/LICENSE)