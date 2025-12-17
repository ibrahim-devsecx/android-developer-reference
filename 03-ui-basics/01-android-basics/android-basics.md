

## 1.  Android Architecture layers  || Android Software Stack

### Linux Kernel

     - base layer of Android

    - Android
> يعتمد على Linux لتوفير الأمان والاستقرار ودعم الأجهزة المختلفة
    
 
**Responsibilities:**

- Hardware Management
    
    - Drivers: Audio, Camera, Display, Bluetooth, WiFi, USB
        
- Memory Management
    
- Process Scheduling
    
- Security
    
    - Permissions



### HAL (Hardware Abstraction Layer): 


- طبقة تربط الـ Framework مع Hardware  بشكل موحد لكل الأجهزة.
- يعطي Interface موحد للتعامل مع Hardware

    
### Native Libraries: 

- مكتبات C/C++ مثل OpenGL, SQLite, SSL.
- هذه المكتبات يستخدمها Framework لتوفير وظائف عالية المستوى.


- **Android Runtime (ART)**: 

- **ART = Android Runtime**  
    بيئة تشغيل تطبيقات **Java / Kotlin** في أندرويد.
    
- يقوم بتحويل وتشغيل:  
    **DEX → Native Code** باستخدام:
    
    - **AOT (Ahead-Of-Time)** أثناء التثبيت
        
    - **JIT (Just-In-Time)** أثناء التشغيل
        
- **AOT** قد يأخذ وقتًا  
    → لذلك تظهر رسالة: _“Optimizing apps…”_
    
- **النتيجة:**
    
    - أداء أسرع
    - استهلاك بطارية أقل
    - أفضل من Dalvik
        

- **Dalvik (قديم)** → JIT فقط
    
- **ART (حديث)** → **AOT + JIT (Hybrid)**
    

```
Java / Kotlin
   ↓
Bytecode (.class)
   ↓
DEX (classes.dex)
   ↓
ART → Native Code
```


> ART يشغّل ملفات `DEX` وليس ملفات `.class`




### Java API Framework: 


-  هي **الـ API** التي يتعامل مع Developer
- APIs مثل ActivityManager، ViewSystem، ContentProvider.


### **System Apps**:
- تطبيقات النظام الرسمية
-  Camera
- Calendar

![[Pasted image 20251207230039.png]]


#### Ultra Short

```
Linux Kernel → hardware + security
HAL → hardware interface
Native Libraries → C/C++ libs
ART → run Java/Kotlin (AOT + JIT)
Java API Framework → APIs for dev
System Apps → built-in apps
```


---


## 2. API Levels & Versions


 - **API Level** → رقم للمطور يحدد الميزات المتوفرة في الـ SDK  
  مثال: API 34، API 33…
- **Version Number** → رقم الإصدار (14 / 13 / 12)
- **Version Name** → الاسم التسويقي (Android 14)
---

## 3. IDE / SDK / Emulator


#### IDE

IDE  =  Integrated Development Environment
مكان كتابة الكود + تصميم UI + تشغيل التطبيق.

**Android Studio** 
هو الـ **IDE الرسمي** لتطوير تطبيقات أندرويد.



#### SDK

SDK = Software Development Kit

أدوات ومكتبات أندرويد (APIs + Build Tools).  

> كل إصدار أندرويد يحتاج SDK خاص فيه


#### SDK Manager

أداة داخل Android Studio لإدارة:

- API Levels
    
- Build Tools
    
- Emulator
    

#### Emulator

محاكي جهاز أندرويد للتجربة بدون جهاز حقيقي.


### Ultra Short

`IDE → Android Studio 
`SDK → tools + APIs 
`SDK Manager → manage versions 
`Emulator → virtual device`

---
## 4. NDK & JNI

**NDK = Native Development Kit**  
يسمح لك بكتابة أجزاء من التطبيق بـ C/C++

لاسباب منها
- أداء عالي (High Performance)
- استخدام مكتبات قديمة
-  Games + Multimedia + ML + Crypto

- JNI = Java Native Interface  
    اللي يسمح للكود يتواصل بين Java ↔ C++
    
---

## 5. Android Sandbox

Android 
يستخدم **Sandbox Model** لحماية البيانات

- هي آلية أمان يعمل فيها كل تطبيق داخل بيئة **معزولة**
- ما يسمح لأي تطبيق الوصول لتطبيق آخر بدون إذن
- 
--كل تطبيق له:

- **Linux User ID** خاص
    
-  **Process** خاص
    
-  **Private Storage**
    

---

## 6. Framework vs Library

##  Library:
- مجموعة Functions أو Classes جاهزة
- المطور **يستدعيها** عند الحاجة
- يعطي **تحكم كامل بالـ Flow**
Example:
- Retrofit
- Glide
- Gson

## Framework:
- يحدد **Application Structure**
- **Framework** يستدعي كود المطور
- يعتمد مبدأ **Inversion of Control (IoC)**
-  هو الذي يتحكم في الـ Flow وليس كود المطور
- 
> **The framework calls your code.**


Examples:
- Android Framework (Activity lifecycle)
- Jetpack Architecture Components (ViewModel, LiveData)





---

>  Deprecated  -->  موجود ولكن غير موصي باستخدامة لانة فية افضل منة وقد يحدف مستقبلا

---

## 7. Gradle Build System


**Gradle**  
هو الـ **Build System** الأساسي في Android Studio، ومسؤول عن:

 - بناء المشروع
    
- إدارة المكتبات (Dependencies)
    
- إنشاء APK / AAB

> Gradle = build automation + dependency management


### Groovy DSL → Kotlin DSL


- قديم: `build.gradle` (Groovy)
    
- جديد: `build.gradle.kts` (Kotlin)
    

**Kotlin DSL أفضل لأنه:**
- لأنها **Type-Safe**
    
- وتدعم **Auto-complete** أفضل داخل Android Studio
    
- وتتكامل مع لغة التطبيق **Kotlin

### Ultra Short:

`Gradle → build automation + dependency management 
`Groovy → old 
`Kotlin DSL → Auto-complete best + type-safe`


---

## 8. Android Project Structure

MyApp/
│
├─ app/                           ← موديول التطبيق (Module)
│   │
│   ├─ manifests/
│   │    └─ AndroidManifest.xml   ← أهم ملف في المشروع
│   │
│   ├─ java/                      ← ملفات الكود
│   │    └─ com.example.myapp/
│   │         ├─ MainActivity.kt  ← نقطة تشغيل التطبيق
│   │         └─ ... ملفات أخرى (ViewModel, Classes…)
│   │
│   ├─ res/                       ← ملفات الواجهة UI / الموارد Resources
│   │    │
│   │    ├─ layout/               ← تصميم الشاشات XML
│   │    │     ├─ activity_main.xml
│   │    │     └─ screen_home.xml
│   │    │
│   │    ├─ values/               ← نصوص، ألوان، Styles
│   │    │     ├─ strings.xml     ← نصوص التطبيق
│   │    │     ├─ colors.xml      ← ألوان UI
│   │    │     ├─ styles.xml      ← الثيمات/الأنماط
│   │    │     ├─ dimens.xml      ← قياسات (Margins, Text sizes…)
│   │    │     └─ themes.xml      ← Light/Dark Theme (AndroidX)
│   │    │
│   │    ├─ drawable/             ← صور ورسومات
│   │    │     ├─ bg_button.xml   ← خلفية زر (Shape XML)
│   │    │     ├─ icon_star.xml   ← أيقونة متجهة Vector
│   │    │     └─ image_logo.png  ← صورة عادية
│   │    │
│   │    ├─ mipmap/               ← أيقونات التطبيق
│   │    │     ├─ ic_launcher.png
│   │    │     └─ ic_launcher_round.png
│   │    │
│   │    ├─ font/                 ← خطوط (اختياري)
│   │    │     └─ cairo.ttf
│   │    │
│   │    ├─ raw/                  ← ملفات خام (اختياري)
│   │    │     └─ data.json
│   │    │
│   │    └─ menu/                 ← قوائم (اختياري)
│   │          └─ main_menu.xml
│   │
│   └─ build.gradle.kts           ← إعدادات موديول التطبيق (Dependencies, SDK)
│
├─ build.gradle.kts               ← إعدادات المشروع العام (Repositories)
└─ settings.gradle.kts            ← تعريف الموديولات (include ":app")


---

## 9. AndroidManifest.xml

- تعريف التطبيق لنظام أندرويد.
    
- تحديد اسم الحزمة (Package Name).
    
- تسجيل Activities.
    
- تحديد شاشة البداية (Launcher Activity).
    
- إضافة الصلاحيات (Permissions).
    
- تعريف مكونات التطبيق
    



###  يتكون من:

- `<manifest>` → اسم الحزمة
    
- `<application>` → اسم التطبيق، الأيقونة، الثيم
    
- `<activity>` → تعريف شاشة
    
- `<intent-filter>` → Launcher Activity
    
- `<uses-permission>` → الصلاحيات
    

### Ultra Short:

`Manifest → app definition 
`Application → app config 
`Activity → screen 
`Intent-filter → launcher 
`Permission → access`
