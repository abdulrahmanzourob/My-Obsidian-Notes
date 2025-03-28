
### 1️⃣ **نسخ الملف إلى `/usr/local/bin`**

الأمر ده بينقل الملف إلى المسار `/usr/local/bin`، وهو مسار بيحتوي على أوامر النظام اللي يقدر أي مستخدم يشغلها:

```bash
cp zz.sh /usr/local/bin
```

### 2️⃣ **إعطاء الملف صلاحية التنفيذ**

بعد النسخ، لازم تضيف له صلاحية التنفيذ باستخدام:

```bash
chmod +x /usr/local/bin/zz.sh
```

أو لو كنت شغال في نفس المسار:

```bash
chmod +x zz.sh
```

### 3️⃣ **تشغيل الأمر من أي مكان**

دلوقتي تقدر تنفّذ الأمر بمجرد كتابة اسمه بدون الحاجة لاستخدام `./` أو تحديد المسار:

```bash
zz.sh
```

أو لو فيه شِبِل (shebang) صحيح في بداية الملف، تقدر تنفذه كأمر عادي:

```bash
zz
```

> ✅ **ملاحظة:** تأكد إن `zz.sh` يحتوي على سطر الـ **Shebang** في بدايته زي:
> 
> ```bash
> #!/bin/bash
> ```
> 
> أو
> 
> ```bash
> #!/usr/bin/env bash
> ```
> 
> عشان يشتغل بالسّكربت المناسب.
![[Screenshot 2025-02-01 214225.png]]

![[Screenshot 2025-02-01 214254.png]]

----
### حل مشكلة "command not found" بعد التثبيت عبر Snap
![[Screenshot 2025-02-01 224629.png]]
#### **السبب:**

عند تثبيت أداة باستخدام `snap`، يتم وضعها في `/snap/bin/`، لكن هذا المسار غير مضاف إلى `PATH`، مما يمنع تشغيل الأداة مباشرة.

---

### **الحلول:**

✅ **إضافة `/snap/bin` إلى `PATH` مؤقتًا:**

```bash
export PATH=$PATH:/snap/bin
```

✅ **إضافته بشكل دائم:**

- لمستخدمي Bash:
    
    ```bash
    echo 'export PATH=$PATH:/snap/bin' >> ~/.bashrc
    source ~/.bashrc
    ```
    
- لمستخدمي Zsh:
    
    ```bash
    echo 'export PATH=$PATH:/snap/bin' >> ~/.zshrc
    source ~/.zshrc
    ```
    

✅ **تشغيل الأداة مباشرة باستخدام المسار الكامل:**

```bash
/snap/bin/<command>
```

🚀 **جرب الحلول دي لتشغيل الأدوات المثبتة عبر Snap بسهولة!**