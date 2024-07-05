---
title: وحدة قياس
linktitle: وحدة قياس
second_title: Aspose.Words واجهة برمجة تطبيقات معالجة المستندات
description: تعرف على كيفية تحديد وحدة القياس عند تحويل مستند Word إلى ODT باستخدام Aspose.Words لـ .NET.
type: docs
weight: 10
url: /ar/net/programming-with-odtsaveoptions/measure-unit/
---

عندما تقوم بتحويل مستند Word إلى تنسيق OpenDocument Text (ODT) في تطبيق C#، فقد ترغب في تحديد وحدة القياس المستخدمة للتنسيق القابل للقياس وخصائص المحتوى. باستخدام مكتبة Aspose.Words لـ .NET، يمكنك بسهولة تحديد هذه الوظيفة باستخدام خيارات الحفظ OdtSaveOptions. في هذا الدليل خطوة بخطوة، سنرشدك إلى كيفية استخدام Aspose.Words للتعليمات البرمجية المصدر لـ .NET C# لتحويل مستند Word إلى ODT عن طريق تحديد وحدة القياس باستخدام OdtSaveOptions.

## فهم مكتبة Aspose.Words

قبل الغوص في التعليمات البرمجية، من المهم فهم مكتبة Aspose.Words الخاصة بـ .NET. Aspose.Words هي مكتبة قوية لإنشاء مستندات Word وتحريرها وتحويلها وحمايتها في منصات مختلفة بما في ذلك .NET. فهو يوفر العديد من الميزات لمعالجة المستندات، مثل إدراج النص وتغيير التنسيق وإضافة الأقسام وغير ذلك الكثير.

## تحميل مستند الوورد

الخطوة الأولى هي تحميل مستند Word الذي تريد تحويله إلى ODT. استخدم فئة المستند لتحميل المستند من الملف المصدر. هنا مثال :

```csharp
Document doc = new Document(dataDir + "Document.docx");
```

في هذا المثال، نقوم بتحميل المستند "Document.docx" الموجود في دليل المستندات.

## تكوين خيارات النسخ الاحتياطي

الخطوة التالية هي تكوين خيارات النسخ الاحتياطي للتحويل إلى ODT. استخدم فئة OdtSaveOptions وقم بتعيين الخاصية MeasureUnit إلى القيمة المطلوبة. على سبيل المثال، إذا كنت تريد استخدام البوصة كوحدة قياس، قم بتعيين MeasureUnit إلى OdtSaveMeasureUnit.Inches. هيريس كيفية القيام بذلك:

```csharp
OdtSaveOptions saveOptions = new OdtSaveOptions { MeasureUnit = OdtSaveMeasureUnit.Inches };
```

نقوم بإنشاء كائن OdtSaveOptions جديد وقمنا بتعيين خاصية MeasureUnit على القيمة المطلوبة، في حالتنا، OdtSaveMeasureUnit.Inches لاستخدام البوصة كوحدة قياس.

## تحويل الوثيقة إلى ODT

الآن بعد أن قمنا بتكوين خيارات الحفظ، يمكننا المتابعة لتحويل المستند إلى ODT. استخدم طريقة Save الخاصة بفئة Document لحفظ المستند المحول بتنسيق ODT عن طريق تحديد خيارات الحفظ. هنا مثال :

```csharp
doc.Save(dataDir + "WorkingWithOdtSaveOptions.MeasureUnit.odt", saveOptions);
```

في هذا المثال، نقوم بحفظ المستند المحول باسم "WorkingWithOdtSaveOptions.MeasureUnit.odt" باستخدام خيارات الحفظ المحددة.

### مثال على التعليمات البرمجية المصدر لـ OdtSaveOptions مع وظيفة "وحدة القياس" باستخدام Aspose.Words for .NET



```csharp
// المسار إلى دليل المستندات الخاص بك
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// قم بتحميل مستند الوورد
Document doc = new Document(dataDir + "Document.docx");

// تكوين خيارات النسخ الاحتياطي مع ميزة "وحدة القياس".
OdtSaveOptions saveOptions = new OdtSaveOptions { MeasureUnit = OdtSaveMeasureUnit.Inches };

// تحويل المستند إلى ODT
doc.Save(dataDir + "WorkingWithOdtSaveOptions.MeasureUnit.odt", saveOptions);
```

## خاتمة

في هذا الدليل، شرحنا كيفية تحويل مستند Word إلى ODT عن طريق تحديد وحدة القياس باستخدام خيارات الحفظ OdtSaveOptions مع مكتبة Aspose.Words لـ .NET. باتباع الخطوات المقدمة واستخدام كود مصدر C# المقدم، يمكنك بسهولة تطبيق هذه الوظيفة في تطبيق C# الخاص بك. يتيح لك تحديد وحدة القياس عند التحويل إلى ODT التحكم في تنسيق وأبعاد المستند الناتج وفقًا لاحتياجاتك الخاصة.