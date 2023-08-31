---
title: لا تقم بحفظ صورة نقطية
linktitle: لا تقم بحفظ صورة نقطية
second_title: واجهة برمجة تطبيقات معالجة المستندات Aspose.Words
description: تعرف على كيفية تعطيل حفظ الرموز النقطية للصور في مستندات Word باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /ar/net/programming-with-docsaveoptions/do-not-save-picture-bullet/
---

تعد الرموز النقطية للصور ميزة شائعة الاستخدام في مستندات Word لإضافة رموز نقطية مخصصة. ومع ذلك ، في بعض الحالات قد يكون من الضروري تعطيل تسجيل الصور النقطية عند معالجة المستندات باستخدام Aspose.Words Library for .NET. في هذا الدليل المفصل خطوة بخطوة ، سنشرح كيفية استخدام كود مصدر Aspose.Words C # لـ .NET لتعطيل حفظ الصور النقطية باستخدام خيارات حفظ DocSaveOptions.

## فهم مكتبة Aspose.Words

قبل التعمق في الكود ، من المهم فهم مكتبة Aspose.Words لـ .NET. Aspose.Words مكتبة قوية لإنشاء مستندات Word وتحريرها وتحويلها وحمايتها في أنظمة أساسية مختلفة بما في ذلك .NET. يوفر العديد من الميزات لمعالجة المستندات ، مثل إدخال نص وتغيير التنسيق وإضافة أقسام وغير ذلك الكثير.

## الخطوة 1: إعداد دليل المستندات

الخطوة الأولى هي تحديد الدليل حيث توجد المستندات الخاصة بك. يجب عليك تحديد مسار الدليل الكامل. على سبيل المثال :

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

تأكد من استبدال "دليل المستندات" بالمسار الفعلي إلى دليل المستندات.

## الخطوة 2: تحميل المستند مع صورة نقطية

بعد ذلك ، تحتاج إلى تحميل المستند باستخدام الرموز النقطية للصور. استخدم فئة المستند لتحميل المستند من ملف. على سبيل المثال :

```csharp
Document doc = new Document(dataDir + "Image bullet points.docx");
```

في هذا المثال نقوم بتحميل المستند من ملف "Image bullet points.docx"

  الموجود في دليل المستندات.

## الخطوة 3: تكوين خيارات التسجيل

لنقم الآن بتهيئة خيارات الحفظ لمستندنا. استخدم فئة DocSaveOptions لتحديد إعدادات الحفظ. على سبيل المثال :

```csharp
DocSaveOptions saveOptions = new DocSaveOptions { SavePictureBullet = false };
```

في هذا المثال ، قمنا بإنشاء كائن DocSaveOptions جديد وقمنا بتعيين الخاصية SavePictureBullet إلى false لتعطيل حفظ الرموز النقطية للصور.

## الخطوة 4: تمكين ميزة "عدم حفظ الصورة التعدادية"

لتمكين ميزة "Do Not Save Picture Bullet" ، قمنا بالفعل بتكوين خيارات الحفظ مع تعيين SavePictureBullet على false. هذا يضمن عدم حفظ الصور النقطية في المستند النهائي.

## الخطوة 5: احفظ المستند

أخيرًا ، يمكنك حفظ المستند باستخدام طريقة Save لفئة Document. حدد المسار الكامل للملف واسم الملف المطلوب. على سبيل المثال :

```csharp
doc.Save(dataDir + "WorkingWithDocSaveOptions.DoNotSavePictureBullet.docx", saveOptions);
```

تأكد من استبدال "dataDir" بمسار الدليل إلى مستنداتك.

## مثال على كود المصدر لـ DocSaveOptions حفظ الخيارات مع وظيفة "عدم حفظ الصورة" باستخدام Aspose.Words for .NET

```csharp
// المسار إلى دليل المستندات الخاص بك
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// قم بتحميل المستند باستخدام الصور النقطية
Document doc = new Document(dataDir + "Image bullet points.docx");

// تكوين خيارات الحفظ مع ميزة "عدم حفظ الصورة"
DocSaveOptions saveOptions = new DocSaveOptions { SavePictureBullet = false };

// احفظ المستند بالخيارات المحددة
doc.Save(dataDir + "WorkingWithDocSaveOptions.DoNotSavePictureBullet.docx", saveOptions);
```

## خاتمة

في هذا الدليل ، تناولنا كيفية تعطيل حفظ الصور النقطية في مستند باستخدام مكتبة Aspose.Words لـ .NET. باتباع الخطوات المقدمة واستخدام الكود المصدري C # المقدم ، يمكنك بسهولة تطبيق هذه الوظيفة في تطبيق C # الخاص بك. يمكن أن يكون تعطيل حفظ الصورة النقطية مفيدًا في بعض المواقف للحفاظ على بنية المستند وتنسيقه بدون حفظ الرموز النقطية للصورة.