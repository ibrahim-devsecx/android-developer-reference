
## Android Application Components

هي العناصر الأساسية التي يبني عليها أي تطبيق Android.

هناك
**4 core components:**

---

### **1. Activity**
[[Activity]]
- شاشة **UI Screen**
    
- تتعامل مع **User Interaction**
    
- لها **Activity Lifecycle**
    

> **Activity = UI + Interaction**

---

### **2. Service**

-  كود يعمل في الخلفية **Background**
    
- بدون واجهة **No UI**
    
- لمهام طويلة:  music, download
    
- قد تستمر بعد غلق Activity
    

> **Service = Background execution**


---

### **3. BroadcastReceiver**

- يستقبل **System Events**
    
- مثال: Battery Low, Boot Completed
    
- يستخدم لتنفيذ actions بناءً على event معين
    

> **BroadcastReceiver = System Events Listener**

---

### **4. ContentProvider**

- مشاركة البيانات **Data Sharing** بين التطبيقات بدون الوصول المباشر للـ Database
    
- الوصول للبيانات: DB, Files
    
- يقدم CRUD عبر **URI**
- **CRUD** = insert/query/update/delete
- **URI** هو عنوان البيانات داخل التطبيق
- **Concept:** ContentProvider = CRUD عبر URI بدل DB.
    

> **ContentProvider = Data Access & Sharing**

---


>كل Component لازم يكون  مسجل داخل **`AndroidManifest.xml`**  عشان النظام يعرفه.

>التواصل بين Components يتم باستخدام **Intent**
> Intent → Android messaging system
