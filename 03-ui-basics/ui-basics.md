
# UI Basics

## XML
**XML = Extensible Markup Language**  
لغة لوصف البيانات و تستخدم في الاندرويد

في Android بنستخدم XML  :

- manifests
    
- UI Layout
    
-  Resources → strings / colors / dimens
    
-  Drawables → shapes / selectors / vectors
    
-  Menu  
    
-  Themes/Styles

XML Structure Basics

- كل Element في XML يعرف باستخدام Tags
    
- Element يتكوّن من:
    
    - **Tag**
        
    - **Attributes**
        
    - **Content**
        
- Tag له:
    
    - Opening `<TextView>`
        
    - Closing `</TextView>`
        
- **Self-closing Tag**:
    
    `<ImageView />`
    
- **Attributes** داخل Opening Tag
    
- `android:` → **Namespace** (Attribute تابع لـ Android SDK)
    
- **Root Element ** 
- أول عنصر في XML

### XML Comments

```xml
<!-- هذا تعليق في XML -->
```

 اختصار:  
`Ctrl + /`



>XML = UI + Resources
   Element → defined by Tags
   Root Element → First element of XML
   android: → Android namespace

---

## UI Core Components: View & ViewGroup


- **View **  
    عنصر UI واحد (Text / Image / Button)
    
- **ViewGroup ** 
- حاوية لعناصر  Container 
    يحتوي علي أكثر من View و ينظم مكانهم داخل الشاشة.
      

>  كل ملف Layout لازم يكون له **Root Element** غالبا ViewGroup لأنه يجمع كل العناصر تحته

---

##  Common Views  && Important Attributes


### TextView

> لعرض نص 

#### أهم Attributes:

- `android:text` → النص الي هينعرض
    
- `android:textSize` → حجم النص (**sp**)
    
- `android:textColor` → لون النص
    
- `android:gravity` → محاذاة النص داخل العنصر
    
- `android:maxLines` → عدد الأسطر
    
- `android:ellipsize="end"` → إظهار `...` عند طول النص
    
- `android:background` → خلفية
    

---

###  EditText

> إدخال نص من المستخدم

#### أهم Attributes:

- `android:hint` → نص ارشاد/ تلميح -- Placeholder
    
- `android:inputType` → نوع الإدخال  
    (text / number / phone / textPassword)
    
- `android:textSize` → حجم النص
    
- `android:textColor` → لون النص
    
- `android:maxLines` → عدد الأسطر (خصوصًا للنصوص الطويلة)
    

> لا نستخدم `text` كنص افتراضي --> نستخدم `hint`.

---

### Button

> تنفيذ Action عند الضغط

#### أهم Attributes:

- `android:text` → نص الزر
    
- `android:background` → خلفية (Shape / Selector)
    
- `android:textColor` → لون النص
    
- `android:onClick` → ربط حدث الضغط (XML-based)
    
- `android:enabled` → تفعيل / تعطيل
    


---

### ImageView

> عرض صورة أو أيقونة

#### أهم Attributes:

- `android:src` → الصورة
    
- `android:tint` → تغيير لون الأيقونة
    
- `android:scaleType` → طريقة عرض الصورة
    
- `android:contentDescription` → إمكانية الوصول (Accessibility)
    

> يدعم PNG و VectorDrawable


----> ShapeableImageView

- ImageView يدعم **Material Design shapes**
    
- قص الصورة (دائري / بزوايا)
    

**Attribute:**

```xml
shapeAppearanceOverlay
```

يستخدم مع:

- Profile Images

---

### ImageButton

> زر بصيغة صورة

#### أهم Attributes:

- `android:src`
    
- `android:background="@null"` → إزالة الخلفية الافتراضية
    
- `android:tint`
    

---

### CheckBox

> اختيار متعدد

#### أهم Attributes:

- `android:text` → النص
    
- `android:checked` → الحالة الافتراضية
    
- `android:buttonTint` → لون مربع الاختيار
    

---

### RadioButton

> اختيار واحد (يستخدم داخل RadioGroup)

#### أهم Attributes:

- `android:text`
    
- `android:checked`
    

---

### Switch

> ON / OFF Toggle

#### أهم Attributes:

- `android:text`
    
- `android:checked`
    
- `android:thumbTint`
    
- `android:trackTint`
    

---

### ProgressBar

> مؤشر تحميل

#### أهم Attributes:

- `android:indeterminate` → تحميل غير محدد
    
- `android:progress` → نسبة التحميل
    
- `android:max` → الحد الأعلى
    

---

### WebView

> عرض محتوى ويب

#### أهم Attributes:

- `android:layout_width`
    
- `android:layout_height`
    

---

### Ultra Short

`TextView → text / textSize / maxLines 
`EditText → hint / inputType Button → text / background 
`ImageView → src / tint / scaleType 
`CheckBox → text / checked 
`RadioGroup → orientation 
`Switch → checked 
`ProgressBar → indeterminate`

---

## Important Attributes


  `id`
لتعريف العنصر والتعامل معه في Kotlin / Java

`android:id="@+id/titleText"`

---
## Size 

`layout_width`             للعرض

 `layout_height`           للطول

قيم 
- `match_parent`
    
- `wrap_content`

> layout_width & layout_height → required 

---

  ## Spacing 

 `layout_margin`       مسافة **خارجية**

 `padding`                        مسافة **داخلية**

---

## Position & Alignment 

 `gravity`                   محاذاة المحتوى داخل العنصر
 
 `layout_gravity`          محاذاة العنصر داخل الأب

---

## Visibility

`visibility`         الظهور

- `visible`
    
- `invisible`
    
- `gone`                لا يحجز مساحة
    

---

## Background & Styling

 `background`   خلفية العنصر

- Drawable
    
- Shape
    
- Selector
    

`android:background="@drawable/btn_selector"`

---

## Text Attributes (لـ TextView)

 `text`

`textSize` → sp

`textColor`

 `maxLines`

 `ellipsize`

---

## Input Attributes (لـ EditText)

 `hint`

 `inputType`
 - `text`
    
- `number`
    
- `phone`
    
- `textPassword`

---

##  Extra / Advanced

`elevation`                الظل (Material Design)

`tools:text`                Preview فقط

---
### Ultra Short

`id ↓ width / height ↓ margin / padding ↓ gravity / layout_gravity ↓ visibility ↓ background ↓ text ↓ input ↓ layout-specific`

---
##  Common ViewGroups  && Important Attributes


### ConstraintLayout

Default & flexible layout

#### أهم Attributes (للـ ViewGroup):

- `android:layout_width`
    
- `android:layout_height`
    

#### أهم Attributes (للـ Views داخله):

- `app:layout_constraintStart_toStartOf`
    
- `app:layout_constraintEnd_toEndOf`
    
- `app:layout_constraintTop_toTopOf`
    
- `app:layout_constraintBottom_toBottomOf`
- 
> كل View لازم يكون له Constraint أفقي + عمودي.



    
#### Bias:

- `app:layout_constraintHorizontal_bias`
    
- `app:layout_constraintVertical_bias`
    
- القيم من `0` إلى `1`
    
- يعمل فقط إذا كان العنصر مربوط من جهتين
    

#### Dimension Ratio:

- `app:layout_constraintDimensionRatio="1:1"`
    
- أحد الأبعاد لازم يكون `0dp`
    


#### Baseline Constraint:

- `app:layout_constraintBaseline_toBaselineOf`
    
- لمحاذاة النصوص بين `TextView`
    
- يعتبر **Vertical constraint**
    

## Guidelines

- خطوط وهمية للمحاذاة
    

### الأنواع:

- `layout_constraintGuide_percent` → نسبة من الشاشة
    
- `layout_constraintGuide_begin` → بعد ثابت من البداية
    
- `layout_constraintGuide_end` → بعد ثابت من النهاية
    
 ----> تساعد في التصميم 

---

## Chains

مجموعة Views مربوطة ببعضها على **نفس المحور** (أفقي أو عمودي) وتشارك نفس المساحة

### الأنواع:

- `spread` → توزيع متساوي
    
- `spread_inside` → فراغ داخلي
    
- `packed` → عناصر متقاربة
    

```xml
app:layout_constraintVertical_chainStyle="packed"
```


- `chainStyle` يوضع على **أول View فقط**
    
- أفقي → `Horizontal_chainStyle`
    
- عمودي → `Vertical_chainStyle`
    

### Ultra Short

```
ConstraintLayout → flexible layout
Bias → position (0–1)
Ratio → aspect
Guideline → alignment
Chain → grouped views
```


---

### LinearLayout
ترتيب العناصر بشكل خطي (horizontal / vertical) 
#### أهم Attributes:

- `android:orientation` → vertical / horizontal
    
- `android:gravity` → محاذاة المحتوى
    
- `android:weightSum`    مجموع الوزن/ نسب - بنحسب تلقائي اذا ما تم ادخلو
    

#### أهم Attributes (للـ Views داخله):

- `android:layout_weight`       تقسيم المساحة نسبيًا داخل LinearLayout

> `layout_weight` →      `layout_width="0dp

---

## RelativeLayout
 ترتيب العناصر بالنسبة لبعضها

#### أهم Attributes:

- `android:gravity`
    

#### أهم Attributes (للـ Views داخله):

- `android:layout_below`
    
- `android:layout_above`
    
- `android:layout_toStartOf`
    
- `android:layout_alignParentStart`
    

> يفضّل استخدام ConstraintLayout بدلا منه.

---

##  FrameLayout
طبقات فوق بعض

### أهم Attributes:

- `android:foreground`
    
- `android:foregroundGravity`
    

---

##  ScrollView

 تمرير عمودي

### أهم Attributes:

- `android:fillViewport`
    
- `android:scrollbars`
    

> يسمح بـ **Child واحد فقط (ViewGroup)**

---

## HorizontalScrollView

تمرير أفقي

#### أهم Attributes:

- `android:scrollbars`
    

> يسمح بـ **Child واحد فقط (ViewGroup)**

---

##  RadioGroup

 - تجميع RadioButtons (اختيار واحد)
- هو الذي يمنع التحديد المتعدد

#### أهم Attributes:

- `android:orientation`
    
---


---

## Ultra Short 

`ConstraintLayout → default 
`LinearLayout → (horizontal / vertical)
`FrameLayout → overlay 
`ScrollView →  vertical scroll 
`HorizontalScrollView → horizontal scroll 
`RadioGroup → single choice 


---

## Units - وحدات القياس

### dp 
- وحدة قياس للاحجام الواجهة والمسافات
- لا تتأثر بدقة الشاشة
### sp

- وحدة مخصصة **للنص**
- تتأثر بإعدادات حجم الخط عند المستخدم

dp → UI sizes & spacing
sp → text size (user scalable)

---
## Orientation (اتجاه الجهاز)

- **Portrait** → عمودي
    
- **Landscape** → أفقي
    

📌 يمكن تخصيص Layout لكل وضع:

```
layout/        → Portrait
layout-land/   → Landscape

Portrait / Landscape → device orientation
```

---
### Resources Folder — `values/`

> مجلد **values/** يستخدم لتخزين القيم المشتركة بدل كتابتها مباشرة داخل الـ Layout.


#### dimens.xml

تخزين **قياسات ثابتة** بوحدة `dp`

**الاستخدام:**

- padding
    
- margin
    
- heights / widths

**مثال:**

`<dimen name="padding_large">16dp</dimen>`
الهدف منها

- توحيد القياسات
    
- سهولة التعديل من مكان واحد
    
---

#### colors.xml
 تعريف ألوان التطبيق

**مثال:**

`<color name="primary">#6200EE</color>`

تستخدم مع:

- `background`
    
- `textColor`
    
- `tint`
    

---

####  strings.xml

تخزين نصوص التطبيق

**مثال:**

`<string name="app_name">My App</string>`
 يدعم:

- الترجمة
    
- إعادة الاستخدام
    
- تنظيم النصوص
    


>Best Practice  
> لا نكتب نصوص مباشرة داخل Layout   استخدم دائمًا `strings.xml`
---

####  strings-ar.xml
 - نسخة عربية من `strings.xml`
 -  نفس keys - قيم مترجمة للعربية

- Android يختار الملف تلقائيًا حسب لغة الجهاز

---

### Ultra Short

`dimens.xml → dp values 
`colors.xml → colors 
`strings.xml → text 
`strings-ar.xml → Arabic 
`values/ → shared resources

---

## VectorDrawable & Icons

### VectorDrawable

- أيقونات SVG قابلة للتكبير بدون فقدان الجودة
- تستخدم بدل PNG

 للاضافة :

```
drawable → New → Vector Asset
```


 >  مكتبة أيقونات SVG جاهزة   ---->     lineicons.com
 
 ---
### App Icon

**appicon.co**

- إنشاء أيقونة التطبيق (Launcher Icon)
    
- يولّد كل الأحجام تلقائيًا
 
---
### Important Attributes

`android:tint`  
تغيير لون الأيقونة

`android:drawableStart`  
وضع أيقونة داخل `TextView` (بداية النص)

`android:drawableTint`  
تغيير لون الأيقونة داخل `TextView`

---

### Drawable — Shape

#### Shape Drawable

- خلفية XML مخصصة

### Important Attributes

`solid`                 لون الخلفية

`stroke`           حدود (Border)

`corners`             تدوير الزوايا

`padding`            مسافة داخلية

`size`                      حجم ثابت

`gradient`             تدرج لوني

Example — Shape (Button Background)


 ملف: `res/drawable/btn_shape.xml`

```xml
<?xml version="1.0" encoding="utf-8"?>
<shape xmlns:android="http://schemas.android.com/apk/res/android"
    android:shape="rectangle">

    <solid android:color="@color/primary" />

    <stroke
        android:width="2dp"
        android:color="@color/black" />

    <corners android:radius="12dp" />

    <padding
        android:left="12dp"
        android:top="8dp"
        android:right="12dp"
        android:bottom="8dp" />

</shape>
```

📌 استخدامه:

```xml
android:background="@drawable/btn_shape"
```

---

### Selector Drawable

#### Selector

- Drawable يتغير حسب حالة العنصر
    

##### اشهر الحالات:

- `state_pressed`
    
- `state_enabled`
    
- `state_checked`
    
يستخدم غالبا مع:

- Button
    
- CheckBox
    
- Switch


Example — Selector (Button States)

ملف: `res/drawable/btn_selector.xml`

```xml
<?xml version="1.0" encoding="utf-8"?>
<selector xmlns:android="http://schemas.android.com/apk/res/android">

    <!-- عند الضغط -->
    <item android:state_pressed="true">
        <shape>
            <solid android:color="@color/dark_primary" />
        </shape>
    </item>

    <!-- عند التعطيل -->
    <item android:state_enabled="false">
        <shape>
            <solid android:color="@color/gray" />
        </shape>
    </item>

    <!-- الحالة العادية -->
    <item>
        <shape>
            <solid android:color="@color/primary" />
        </shape>
    </item>

</selector>
```

الاستخدام:

```xml
android:background="@drawable/btn_selector"
```

---


## Styles & Themes

#### styles.xml / themes.xml

- تخصيص UI بشكل مركزي
- تقليل التكرار
- دعم Dark / Light Mode

`
<style name="AppButtonStyle" parent="Widget.Material3.Button">

    <!-- خلفية مخصصة (Shape / Selector) -->
    <item name="android:background">@drawable/btn_selector</item>

    <!-- لون النص -->
    <item name="android:textColor">@color/white</item>

    <!-- حجم النص -->
    <item name="android:textSize">16sp</item>

    <!-- مسافة داخلية -->
    <item name="android:paddingHorizontal">16dp</item>
    <item name="android:paddingVertical">10dp</item>

    <!-- تعطيل الحروف الكبيرة الافتراضية -->
    <item name="android:textAllCaps">false</item>

</style>
`

----

### Ultra Short

```
Vector → SVG icons
Shape → custom background
Selector → state UI
ShapeableImageView → shaped images
Constraint → flexible layout
Guideline → alignment helper
Chain → group layout
MotionLayout → animations
tools: → preview only
```


---
# MotionLayout

تطوير لـ **ConstraintLayout**  
يُستخدم لعمل **Animations + Transitions** داخل نفس الـ layout بدون كود.

> MotionLayout = ConstraintLayout + MotionScene

#### الفكرة العامة

- Parent = **MotionLayout**
    
- الحركة تعرف في ملف **MotionScene**
    
- الانتقال يتم بين حالتين:
    
    - **Start ConstraintSet**
        
    - **End ConstraintSet**
        

### MotionScene يتكون من:

### 1️ ConstraintSet

- يحدد وضع الـ View في حالة معيّنة (start / end)
    
- نفس constraints لكن بقيم مختلفة
    

```xml
<ConstraintSet android:id="@+id/start">...</ConstraintSet>
<ConstraintSet android:id="@+id/end">...</ConstraintSet>
```

### 2️ Transition

- يربط `start` مع `end`
    
- يحدد طريقة الانتقال
    

```xml
<Transition
    app:constraintSetStart="@id/start"
    app:constraintSetEnd="@id/end">
```

### 3️ OnSwipe / OnClick

- التحكم بالحركة عن طريق Gesture أو Click
    

```xml
<OnSwipe
    app:touchAnchorId="@id/videoView"
    app:dragDirection="dragUp"/>
```

### Custom Attributes

- تغيير خصائص غير الـ layout (color, alpha, rotation…)
    
- تكتب داخل `Constraint`
    

```xml
<CustomAttribute
    app:attributeName="backgroundColor"
    app:customColorValue="@color/primary"/>
```

📌 مفيدة لـ:

- color
    
- alpha
    
- elevation
    


### KeyFrames

- التحكم بالحركة في نقطة معيّنة من الانتقال
    
- النسبة من 0 → 100
    

```xml
<KeyFrameSet>

    <KeyPosition
        app:framePosition="90"
        app:motionTarget="@id/videoView"
        app:percentX="0.3"/>

    <KeyAttribute
        app:framePosition="90"
        app:motionTarget="@id/videoView"
        android:scaleX="3"
        android:rotation="90"/>

</KeyFrameSet>
```


## Important Notes (Dev)

- داخل MotionScene نستخدم:
    
    - `@id/viewId` ❌ مش `@+id`
        
- MotionLayout = ConstraintLayout (كل قوانينه شغّالة)
    
- الحركة بدون Java/Kotlin
    



---

# Lottie (External Library)

مكتبة Animations بصيغة **JSON**

### الاستخدام:

- UI Animations
    
- Loading
    
- Empty States
    


### Setup

```gradle
implementation "com.airbnb.android:lottie:$lottieVersion"
```


## مكان الملف

```
res/raw/animation.json
```

## LottieAnimationView

```xml
<com.airbnb.lottie.LottieAnimationView
    app:lottie_rawRes="@raw/animation"
    app:lottie_autoPlay="true"
    app:lottie_loop="true"/>
```

## Ultra Short 

```
MotionLayout → animated ConstraintLayout
MotionScene → start + end + transition
ConstraintSet → view state
Transition → move between states
OnSwipe → gesture control
KeyFrame → mid animation control
CustomAttribute → animate properties
Lottie → JSON animations
```


---

## Common Properties (Motion / UI)

- **`alpha`**  
    التحكم في الشفافية  
    `0 = invisible` ، `1 = fully visible`
    
- **`scaleX / scaleY`**  
    تكبير / تصغير العنصر أفقيًا وعموديًا
    
- **`rotation`**  
    تدوير العنصر بالدرجات (°)
    
- **`visibilityMode="ignore"`** _(MotionLayout)_  
    يتجاهل تغيّر `visibility` أثناء الحركة  
    → الحركة تستمر حتى لو العنصر `GONE / INVISIBLE`
    

---

### Ultra Short

```
alpha → transparency
scaleX / scaleY → size
rotation → angle
visibilityMode=ignore → keep animating
```


---

