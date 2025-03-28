

1. **`grep`**:
    
    - **الوظيفة**: يستخدم للبحث عن نص معين داخل ملف أو في مجموعة من الملفات.
    - **الاستخدام**:
        
        ```bash
        grep "pattern" filename
        ```
        
        حيث أن `pattern` هو النص الذي تريد البحث عنه و `filename` هو الملف أو الملفات التي تريد البحث فيها.
    - **مثال**:
        
        ```bash
        grep "error" log.txt
        ```
        
        سيعرض جميع الأسطر التي تحتوي على الكلمة "error".
2. **`sort`**:
    
    - **الوظيفة**: يقوم بترتيب الأسطر في الملف.
    - **الاستخدام**:
        
        ```bash
        sort filename
        ```
        
        يقوم بترتيب الأسطر في الملف **بترتيب أبجدي** بشكل افتراضي.
    - **مثال**:
        
        ```bash
        sort names.txt
        ```
        
        سيعرض قائمة الأسماء في `names.txt` بترتيب أبجدي.
3.  **`uniq`**:
    
    - **الوظيفة**: يُستخدم لإزالة الأسطر المكررة من الملف أو يُظهر الأسطر التي تظهر فقط مرة واحدة.
        
    - **الاستخدام**:
        
        ```bash
        uniq filename
        ```
        
    - **مثال**:
        
        ```bash
        sort names.txt | uniq
        ```
        
        سيعرض الأسطر الفريدة فقط بعد ترتيبها.
        
    - **`-u`**: لعرض الأسطر التي تظهر مرة واحدة فقط.
        
        ```bash
        sort names.txt | uniq -u
        ```
        
4. **`strings`**:
    
    - **الوظيفة**: يُستخدم لاستخراج السلاسل النصية من ملفات غير نصية (مثل ملفات الـ binary).
    - **الاستخدام**:
        
        ```bash
        strings filename
        ```
        
    - **مثال**:
        
        ```bash
        strings image.jpg
        ```
        
        سيعرض جميع النصوص القابلة للقراءة داخل الصورة (إذا كانت موجودة).
5. **`base64`**:
    
    - **الوظيفة**: يستخدم لتحويل البيانات إلى تنسيق Base64 (وغالبًا ما يُستخدم لتحويل البيانات الثنائية إلى نص يمكن نقله بسهولة).
        
    - **الاستخدام**:
        
        ```bash
        base64 filename
        ```
        
    - **مثال**:
        
        ```bash
        base64 file.txt
        ```
        
        سيحول محتوى الملف `file.txt` إلى تنسيق Base64.
        
    - **لفك التشفير (decode)**:
        
        ```bash
        base64 -d filename
        ```
        
6. **`tr`**:
    
    - **الوظيفة**: يُستخدم لتحويل أو استبدال النصوص داخل البيانات.
    - **الاستخدام**:
        
        ```bash
        tr 'old' 'new' < filename
        ```
        
    - **مثال**:
        
        ```bash
        tr 'a-z' 'A-Z' < file.txt
        ```
        
        سيحول جميع الحروف الصغيرة إلى حروف كبيرة في الملف `file.txt`.
7. **`tar`**:
    
    - **الوظيفة**: يُستخدم لإنشاء أو استخراج أرشيفات ملفات (مثل `.tar`, `.tar.gz`).
    - **الاستخدام**:
        - **إنشاء أرشيف**:
            
            ```bash
            tar -cvf archive.tar file1 file2
            ```
            
            `-c` لإنشاء أرشيف جديد، `-v` لعرض الملفات أثناء الإضافة، `-f` لتحديد اسم الأرشيف.
        - **استخراج أرشيف**:
            
            ```bash
            tar -xvf archive.tar
            ```
            
8. **`gzip`**:
    
    - **الوظيفة**: يُستخدم لضغط الملفات باستخدام خوارزمية GZIP.
        
    - **الاستخدام**:
        
        ```bash
        gzip filename
        ```
        
    - **مثال**:
        
        ```bash
        gzip file.txt
        ```
        
        سيقوم بضغط `file.txt` وتحويله إلى `file.txt.gz`.
        
    - **لفك الضغط**:
        
        ```bash
        gunzip file.txt.gz
        ```
        
9. **`bzip2`**:
    
    - **الوظيفة**: يُستخدم لضغط الملفات باستخدام خوارزمية BZIP2.
        
    - **الاستخدام**:
        
        ```bash
        bzip2 filename
        ```
        
    - **مثال**:
        
        ```bash
        bzip2 file.txt
        ```
        
        سيقوم بضغط `file.txt` وتحويله إلى `file.txt.bz2`.
        
    - **لفك الضغط**:
        
        ```bash
        bunzip2 file.txt.bz2
        ```
        
10. **`xxd`**:
    
    - **الوظيفة**: يُستخدم لتحويل البيانات الثنائية (مثل محتويات الملفات) إلى تمثيل نصي بتنسيق hexadecimal.
    - **الاستخدام**:

### **2. شرح كل جزء في الأمر**

#### **(1) `xxd -r data.txt`**

- **`xxd -r`**:
    - `-r` تعني **reverse** (عكس العملية)، أي **تحويل الهيكس إلى الملف الأصلي**.
- **`data.txt`**:
    - هذا الملف يحتوي على البيانات بصيغة **hexdump**، والتي تم تحويلها من ملف أصلي.

#### **(2) `> data`**

- هذا الجزء **يحفظ الإخراج في ملف اسمه `data`** بدل ما يظهر في الشاشة.
- بدون `>`، كانت البيانات ستُعرض في التيرمينال فقط.
- `>` هو **رمز إعادة التوجيه** في Linux، ويعني "احفظ الناتج في الملف".

---

### **3. كيف يعمل الأمر؟**

نفترض أن `data.txt` يحتوي على بيانات `hexdump` مثل:

```
00000000: 4865 6c6c 6f20 576f 726c 6421 0a       Hello World!.
```

عند تشغيل:

```bash
xxd -r data.txt > data
```

سينتج ملف جديد `data` يحتوي على:

```
Hello World!
```

لأنه أعاد تحويل الهيكس إلى نص عادي.

---

### **4. متى نستخدم هذا الأمر؟**

- عندما يكون لدينا ملف **تم تحويله إلى هيكس** (مثل `hexdump` أو `xxd`).
- لاستعادة الملفات الأصلية **بعد تحويلها إلى هيكس** لأي سبب.
- في مستويات OverTheWire مثل **Bandit**، حيث يتم تخزين البيانات بشكل مضغوط أو مشفر.

---

### **5. كيف نعرف إن الملف رجع لحالته الأصلية؟**

بعد تشغيل الأمر، استخدم:

```bash
file data
```

سيعطيك نوع الملف، فإذا كان **ملف نصي أو مضغوط أو أي شيء آخر**، تعرف أنك استرجعت الأصل.

---

### **ملخص سريع** 🚀

✅ `xxd` = يحول الملفات إلى هيكس.  
✅ `xxd -r` = يعيد الهيكس إلى أصله.  
✅ `xxd -r data.txt > data` = يحول `data.txt` من هيكس إلى ملف أصلي ويحفظه في `data`.

لو عندك أي استفسار، اسألني وأنا أوضح أكتر! 💪🔥

---

### **الخلاصة:**

- هذه الأوامر كلها أدوات قوية للعمل مع الملفات النصية والبيانات الثنائية، وتحويلها، وضغطها، واستخراج المعلومات منها بشكل مرن.