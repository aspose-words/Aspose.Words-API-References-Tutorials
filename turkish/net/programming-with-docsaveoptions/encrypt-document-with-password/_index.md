---
title: تشفير الوثيقة بكلمة مرور
linktitle: تشفير الوثيقة بكلمة مرور
second_title: Aspose.Words لمراجع .NET API
description: تعرف على كيفية تشفير المستندات بكلمة مرور باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /tr/net/programming-with-docsaveoptions/encrypt-document-with-password/
---
يعد أمان المستند ضروريًا عند العمل مع الملفات في تطبيق C #. باستخدام مكتبة Aspose.Words لـ .NET ، يمكنك حماية مستنداتك بسهولة عن طريق تشفيرها بكلمة مرور. في هذا الدليل المفصل خطوة بخطوة ، سنرشدك إلى كيفية استخدام Aspose.Words للكود المصدري .NET C # لتشفير مستند باستخدام خيارات حفظ DocSaveOptions.

## فهم مكتبة Aspose.Words

قبل التعمق في الكود ، من المهم فهم مكتبة Aspose.Words لـ .NET. Aspose.Words مكتبة قوية لإنشاء مستندات Word وتحريرها وتحويلها وحمايتها في أنظمة أساسية مختلفة بما في ذلك .NET. يوفر العديد من الميزات لمعالجة المستندات ، مثل إدخال نص وتغيير التنسيق وإضافة أقسام وغير ذلك الكثير.

## الخطوة 1: تحديد دليل المستند

الخطوة الأولى هي تعيين الدليل حيث تريد حفظ المستند المشفر. يجب عليك تحديد مسار الدليل الكامل. على سبيل المثال :

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

تأكد من استبدال "دليل المستندات" بالمسار الفعلي إلى دليل المستندات.

## الخطوة 2: إنشاء وتحرير وثيقة

ثم يمكنك إنشاء مستند وإضافة محتوى إليه. استخدم فئة DocumentBuilder المقدمة من Aspose.Words لبناء محتوى وثيقتك. على سبيل المثال :

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
            
builder.Write("Hello world!");
```

في هذا المثال ، نقوم بإنشاء مستند فارغ جديد ثم استخدام DocumentBuilder لكتابة النص "Hello World!".

## الخطوة 3: تكوين خيارات التسجيل

لنقم الآن بتهيئة خيارات الحفظ لمستندنا. استخدم فئة DocSaveOptions لتحديد إعدادات الحفظ. على سبيل المثال :

```csharp
DocSaveOptions saveOptions = new DocSaveOptions { Password = "password" };
```

في هذا المثال ، قمنا بإنشاء كائن DocSaveOptions جديد وقمنا بتعيين خاصية Password على "password" لتشفير المستند باستخدام كلمة المرور هذه.

## الخطوة 4: تمكين ميزة "تشفير المستند بكلمة مرور"

لقد قمنا بالفعل بتكوين الخيارات لـ

التسجيل بكلمة المرور المحددة ، والتي تقوم تلقائيًا بتنشيط ميزة "تشفير المستند بكلمة مرور". هذا يضمن أن الوثيقة مشفرة بكلمة المرور المحددة عندما تم حفظها.

## الخطوة 5: حفظ المستند

أخيرًا ، يمكنك حفظ المستند باستخدام طريقة Save لفئة Document. حدد المسار الكامل للملف واسم الملف المطلوب. على سبيل المثال :

```csharp
doc.Save(dataDir + "WorkingWithDocSaveOptions.EncryptDocumentWithPassword.docx", saveOptions);
```

تأكد من استبدال "dataDir" بمسار الدليل إلى مستنداتك.

### مثال على التعليمات البرمجية المصدر لـ DocSaveOptions حفظ الخيارات باستخدام وظيفة "تشفير المستند بكلمة مرور" باستخدام Aspose.Words for .NET

```csharp
// المسار إلى دليل المستندات الخاص بك
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// إنشاء وتحرير وثيقة
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
            
builder.Write("Hello world!");

// قم بتكوين خيارات الحفظ باستخدام ميزة "تشفير المستند بكلمة مرور"
DocSaveOptions saveOptions = new DocSaveOptions { Password = "password" };

// احفظ المستند بالخيارات المحددة
doc.Save(dataDir + "WorkingWithDocSaveOptions.EncryptDocumentWithPassword.docx", saveOptions);
```

## خاتمة

في هذا الدليل ، شرحنا كيفية استخدام مكتبة Aspose.Words لـ .NET لتشفير مستند بكلمة مرور باستخدام خيارات حفظ DocSaveOptions. باتباع الخطوات المقدمة واستخدام الكود المصدري C # المقدم ، يمكنك بسهولة تطبيق هذه الوظيفة في تطبيق C # الخاص بك. يضمن تشفير المستند بكلمة مرور سريته وأمانه عند التعامل معه.