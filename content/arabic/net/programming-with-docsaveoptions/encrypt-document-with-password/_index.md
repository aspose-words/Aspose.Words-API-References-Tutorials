---
title: تشفير المستند بكلمة مرور
linktitle: تشفير المستند بكلمة مرور
second_title: Aspose.Words واجهة برمجة تطبيقات معالجة المستندات
description: تعرف على كيفية تشفير المستندات بكلمة مرور باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /ar/net/programming-with-docsaveoptions/encrypt-document-with-password/
---
يعد أمان المستند أمرًا ضروريًا عند معالجة الكلمات مع الملفات الموجودة في تطبيق C#. باستخدام مكتبة Aspose.Words لـ .NET، يمكنك بسهولة حماية مستنداتك عن طريق تشفيرها بكلمة مرور. في هذا الدليل التفصيلي، سنرشدك إلى كيفية استخدام Aspose.Words للتعليمات البرمجية المصدر لـ .NET C# لتشفير مستند باستخدام خيارات الحفظ DocSaveOptions.

## فهم مكتبة Aspose.Words

قبل الغوص في التعليمات البرمجية، من المهم فهم مكتبة Aspose.Words الخاصة بـ .NET. Aspose.Words هي مكتبة قوية لإنشاء مستندات Word وتحريرها وتحويلها وحمايتها في منصات مختلفة بما في ذلك .NET. فهو يوفر العديد من الميزات لمعالجة المستندات، مثل إدراج النص وتغيير التنسيق وإضافة الأقسام وغير ذلك الكثير.

## الخطوة 1: تحديد دليل المستندات

الخطوة الأولى هي تعيين الدليل الذي تريد حفظ المستند المشفر فيه. يجب عليك تحديد مسار الدليل الكامل. على سبيل المثال :

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

تأكد من استبدال "دليل مستنداتك" بالمسار الفعلي لدليل مستنداتك.

## الخطوة 2: إنشاء وتحرير مستند

وبعد ذلك يمكنك إنشاء مستند وإضافة محتوى إليه. استخدم فئة DocumentBuilder المقدمة من Aspose.Words لإنشاء محتوى مستندك. على سبيل المثال :

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
            
builder.Write("Hello world!");
```

في هذا المثال، نقوم بإنشاء مستند فارغ جديد ثم نستخدم DocumentBuilder لكتابة النص "Hello World!".

## الخطوة 3: تكوين خيارات التسجيل

الآن دعونا نقوم بتكوين خيارات الحفظ لمستندنا. استخدم فئة DocSaveOptions لتحديد إعدادات الحفظ. على سبيل المثال :

```csharp
DocSaveOptions saveOptions = new DocSaveOptions { Password = "password" };
```

في هذا المثال، قمنا بإنشاء كائن DocSaveOptions جديد وقمنا بتعيين خاصية كلمة المرور على "كلمة المرور" لتشفير المستند باستخدام كلمة المرور هذه.

## الخطوة 4: تمكين ميزة "تشفير المستند بكلمة مرور".

لقد قمنا بالفعل بتكوين الخيارات لـ

التسجيل بكلمة المرور المحددة، مما يؤدي تلقائيًا إلى تفعيل ميزة "تشفير المستند بكلمة مرور". وهذا يضمن تشفير المستند بكلمة المرور المحددة عند حفظه.

## الخطوة 5: حفظ الوثيقة

وأخيرًا، يمكنك حفظ المستند باستخدام طريقة الحفظ الخاصة بفئة المستند. حدد المسار الكامل للملف واسم الملف المطلوب. على سبيل المثال :

```csharp
doc.Save(dataDir + "WorkingWithDocSaveOptions.EncryptDocumentWithPassword.docx", saveOptions);
```

تأكد من استبدال "dataDir" بمسار الدليل إلى مستنداتك.

### مثال على التعليمات البرمجية المصدر لخيارات حفظ DocSaveOptions مع وظيفة "تشفير المستند بكلمة مرور" باستخدام Aspose.Words for .NET

```csharp
// المسار إلى دليل المستندات الخاص بك
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// إنشاء وتحرير مستند
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
            
builder.Write("Hello world!");

// قم بتكوين خيارات الحفظ باستخدام ميزة "تشفير المستند بكلمة مرور".
DocSaveOptions saveOptions = new DocSaveOptions { Password = "password" };

// احفظ المستند بالخيارات المحددة
doc.Save(dataDir + "WorkingWithDocSaveOptions.EncryptDocumentWithPassword.docx", saveOptions);
```

## خاتمة

شرحنا في هذا الدليل كيفية استخدام مكتبة Aspose.Words لـ .NET لتشفير مستند بكلمة مرور باستخدام خيارات الحفظ DocSaveOptions. باتباع الخطوات المقدمة واستخدام كود مصدر C# المقدم، يمكنك بسهولة تطبيق هذه الوظيفة في تطبيق C# الخاص بك. تشفير الوثيقة بكلمة مرور يضمن سريتها وأمانها عند التعامل معها.