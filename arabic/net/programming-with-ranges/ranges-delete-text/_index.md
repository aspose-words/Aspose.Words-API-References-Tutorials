---
title: نطاقات حذف النص
linktitle: نطاقات حذف النص
second_title: Aspose.Words لمراجع .NET API
description: تعرف على كيفية حذف نص في نطاقات محددة في مستند Word باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /ar/net/programming-with-ranges/ranges-delete-text/
---

Aspose.Words for .NET مكتبة قوية لإنشاء مستندات Word وتحريرها ومعالجتها في تطبيق C #. من بين الميزات التي تقدمها Aspose.Words القدرة على حذف نص معين ضمن نطاقات محددة من المستند. في هذا الدليل ، سنرشدك إلى كيفية استخدام الكود المصدري C # الخاص بـ Aspose.Words for .NET لحذف نص في نطاقات محددة في مستند Word.

## فهم مكتبة Aspose.Words

قبل التعمق في الكود ، من المهم فهم مكتبة Aspose.Words لـ .NET. Aspose.Words مكتبة شائعة تجعل العمل مع مستندات Word أمرًا سهلاً وفعالاً. يوفر مجموعة واسعة من الميزات لإنشاء مستندات Word وتحريرها ومعالجتها ، بما في ذلك حذف النص في نطاقات محددة.

## تحميل مستند Word

تتمثل الخطوة الأولى في تحميل مستند Word حيث تريد حذف النص. استخدم فئة المستند لتحميل المستند من الملف المصدر. هنا مثال :

```csharp
Document doc = new Document(dataDir + "Document.docx");
```

في هذا المثال ، نقوم بتحميل المستند "Document.docx" الموجود في دليل المستندات.

## حذف النص في نطاقات محددة

بمجرد تحميل المستند ، يمكنك التنقل إلى أقسام المستند وتحديد النطاقات حيث تريد حذف النص. في هذا المثال ، سنزيل كل النص من القسم الأول من المستند. إليك الطريقة:

```csharp
doc.Sections[0].Range.Delete();
```

في هذا المثال ، نقوم بالوصول إلى القسم الأول من المستند باستخدام الفهرس 0 (الأقسام مفهرسة من 0). بعد ذلك ، نسمي طريقة الحذف في نطاق القسم لحذف كل النص من هذا النطاق.

## احفظ المستند المعدل

بمجرد حذف النص في النطاقات المحددة ، يمكنك حفظ المستند المعدل باستخدام طريقة Save لفئة Document. هنا مثال :

```csharp
doc.Save(dataDir + "WorkingWithRangesDeleteText.ModifiedDocument.docx");
```

في هذا المثال ، نحفظ المستند المعدل باسم "WorkingWithRangesDeleteText.ModifiedDocument.docx".

### مثال على شفرة المصدر لوظيفة "حذف النص في النطاقات" باستخدام Aspose.Words for .NET

```csharp
// المسار إلى دليل المستندات الخاص بك
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// قم بتحميل مستند Word
Document doc = new Document(dataDir + "Document.docx");

// احذف النص في القسم الأول من المستند
doc.Sections[0].Range.Delete();

// احفظ المستند المعدل
doc.Save(dataDir + "WorkingWithRangesDeleteText.ModifiedDocument.docx");
```

## خاتمة

في هذا الدليل ، قمنا بتغطية كيفية استخدام Aspose.Words for .NET لحذف نص في نطاقات محددة من مستند Word باستخدام كود المصدر C # المقدم. باتباع الخطوات المقدمة ، يمكنك بسهولة حذف النص في نطاقات محددة في مستندات Word الخاصة بك في تطبيق C # الخاص بك. يوفر Aspose. Words مرونة هائلة وقوة للعمل مع نطاقات من النصوص ، مما يسمح لك بإنشاء وتحرير مستندات Word بدقة وبشكل هادف.