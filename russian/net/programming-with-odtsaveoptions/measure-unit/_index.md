---
title: وحدة قياس
linktitle: وحدة قياس
second_title: Aspose.Words لمراجع .NET API
description: تعرف على كيفية تحديد وحدة القياس عند تحويل مستند Word إلى ODT باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /ru/net/programming-with-odtsaveoptions/measure-unit/
---

عند تحويل مستند Word إلى تنسيق OpenDocument Text (ODT) في تطبيق C # ، قد ترغب في تحديد وحدة القياس المستخدمة للتنسيق القابل للقياس وخصائص المحتوى. باستخدام مكتبة Aspose.Words لـ .NET ، يمكنك بسهولة تحديد هذه الوظيفة باستخدام خيارات حفظ OdtSaveOptions. في هذا الدليل المفصل خطوة بخطوة ، سنرشدك إلى كيفية استخدام Aspose.Words للكود المصدري .NET C # لتحويل مستند Word إلى ODT عن طريق تحديد وحدة القياس باستخدام OdtSaveOptions.

## فهم مكتبة Aspose.Words

قبل التعمق في الكود ، من المهم فهم مكتبة Aspose.Words لـ .NET. Aspose.Words مكتبة قوية لإنشاء مستندات Word وتحريرها وتحويلها وحمايتها في أنظمة أساسية مختلفة بما في ذلك .NET. يوفر العديد من الميزات لمعالجة المستندات ، مثل إدخال نص وتغيير التنسيق وإضافة أقسام وغير ذلك الكثير.

## تحميل مستند Word

الخطوة الأولى هي تحميل مستند Word الذي تريد تحويله إلى ODT. استخدم فئة المستند لتحميل المستند من الملف المصدر. هنا مثال :

```csharp
Document doc = new Document(dataDir + "Document.docx");
```

في هذا المثال ، نقوم بتحميل المستند "Document.docx" الموجود في دليل المستندات.

## تكوين خيارات النسخ الاحتياطي

الخطوة التالية هي تكوين خيارات النسخ الاحتياطي للتحويل إلى ODT. استخدم فئة OdtSaveOptions وقم بتعيين خاصية MeasureUnit إلى القيمة المطلوبة. على سبيل المثال ، إذا كنت تريد استخدام البوصة كوحدة قياس ، فاضبط MeasureUnit على OdtSaveMeasureUnit.Inches. هيريس كيفية القيام بذلك:

```csharp
OdtSaveOptions saveOptions = new OdtSaveOptions { MeasureUnit = OdtSaveMeasureUnit.Inches };
```

نقوم بإنشاء كائن OdtSaveOptions جديد وتعيين خاصية MeasureUnit إلى القيمة المطلوبة ، في حالتنا ، OdtSaveMeasureUnit.Inches لاستخدام البوصة كوحدة قياس.

## تحويل المستند إلى ODT

الآن بعد أن قمنا بتكوين خيارات الحفظ ، يمكننا المتابعة لتحويل المستند إلى ODT. استخدم طريقة Save لفئة Document لحفظ المستند المحول بتنسيق ODT عن طريق تحديد خيارات الحفظ. هنا مثال :

```csharp
doc.Save(dataDir + "WorkingWithOdtSaveOptions.MeasureUnit.odt", saveOptions);
```

في هذا المثال ، نحفظ المستند المحول باسم "WorkingWithOdtSaveOptions.MeasureUnit.odt" باستخدام خيارات الحفظ المحددة.

### مثال على شفرة المصدر لـ OdtSaveOptions مع وظيفة "وحدة القياس" باستخدام Aspose.Words for .NET



```csharp
// المسار إلى دليل المستندات الخاص بك
string dataDir = "YOUR DOCUMENTS DIRECTORY";

//قم بتحميل مستند Word
Document doc = new Document(dataDir + "Document.docx");

// تكوين خيارات النسخ الاحتياطي باستخدام ميزة "وحدة القياس"
OdtSaveOptions saveOptions = new OdtSaveOptions { MeasureUnit = OdtSaveMeasureUnit.Inches };

// تحويل المستند إلى ODT
doc.Save(dataDir + "WorkingWithOdtSaveOptions.MeasureUnit.odt", saveOptions);
```

## خاتمة

في هذا الدليل ، أوضحنا كيفية تحويل مستند Word إلى ODT عن طريق تحديد وحدة القياس باستخدام خيارات حفظ OdtSaveOptions مع مكتبة Aspose.Words لـ .NET. باتباع الخطوات المقدمة واستخدام الكود المصدري C # المقدم ، يمكنك بسهولة تطبيق هذه الوظيفة في تطبيق C # الخاص بك. يتيح لك تحديد وحدة القياس عند التحويل إلى ODT التحكم في تنسيق وأبعاد المستند الناتج وفقًا لاحتياجاتك الخاصة.