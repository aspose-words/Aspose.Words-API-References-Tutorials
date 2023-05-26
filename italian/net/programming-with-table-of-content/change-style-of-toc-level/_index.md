---
title: تغيير نمط مستوى Toc
linktitle: تغيير نمط مستوى Toc
second_title: Aspose.Words لمراجع .NET API
description: تعرف على كيفية تغيير نمط مستوى جدول المحتويات بسهولة في مستند Word باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /it/net/programming-with-table-of-content/change-style-of-toc-level/
---

Aspose.Words for .NET مكتبة قوية لإنشاء مستندات Word وتحريرها ومعالجتها في تطبيق C #. من بين الميزات التي تقدمها Aspose.Words القدرة على تغيير نمط مستوى معين من جدول محتويات المستند. في هذا الدليل ، سنوضح لك كيفية استخدام الكود المصدري C # الخاص بـ Aspose.Words for .NET لتغيير نمط مستوى جدول محتويات مستند Word.

## فهم مكتبة Aspose.Words

قبل التعمق في الكود ، من المهم فهم مكتبة Aspose.Words لـ .NET. Aspose.Words مكتبة شائعة تجعل العمل مع مستندات Word أمرًا سهلاً وفعالاً. يوفر مجموعة واسعة من الميزات لإنشاء مستندات Word وتحريرها ومعالجتها ، بما في ذلك تغيير نمط جدول المحتويات.

## إنشاء وثيقة جديدة

تتمثل الخطوة الأولى في إنشاء مستند Word جديد حيث تريد تغيير نمط جدول المحتويات. استخدم فئة المستند لإنشاء مستند جديد. هنا مثال :

```csharp
Document doc = new Document();
```

في هذا المثال ، نقوم بإنشاء مستند فارغ جديد.

## تغيير نمط جدول المحتويات

بمجرد إنشاء المستند ، يمكنك الوصول إلى أنماط المستند وتغيير النمط المستخدم لمستوى معين من جدول المحتويات. في هذا المثال ، سنقوم بتعديل النمط المستخدم للمستوى الأول من جدول المحتويات. إليك الطريقة:

```csharp
doc.Styles[StyleIdentifier.Toc1].Font.Bold = true;
```

في هذا المثال ، نستخدم خاصية Styles لفئة Document للوصول إلى أنماط المستند. بعد ذلك ، نستخدم معرف النمط StyleIdentifier.Toc1 للوصول إلى النمط المستخدم للمستوى الأول من جدول المحتويات. أخيرًا ، نقوم بتعديل الخاصية Font.Bold للنمط لجعلها غامقة.

## احفظ المستند المعدل

بمجرد إجراء التعديلات اللازمة على نمط جدول المحتويات ، يمكنك حفظ المستند المعدل باستخدام طريقة Save لفئة Document. هنا مثال :

```csharp
doc.Save(dataDir + "WorkingWithChangeStyleOfTocLevel.ModifiedDocument.docx");
```

في هذا المثال ، نحفظ المستند المعدل باسم "WorkingWithChangeStyleOfTocLevel.ModifiedDocument.docx".

## مثال على شفرة المصدر لميزة "تغيير نمط مستوى جدول المحتويات" باستخدام Aspose.Words for .NET

```csharp
// المسار إلى دليل المستندات الخاص بك
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// قم بإنشاء مستند جديد
Document doc = new Document();

// تعديل نمط المستوى الأول لجدول المحتويات
doc.Styles[StyleIdentifier.Toc1].Font.Bold = true;

// احفظ المستند المعدل
doc.Save(dataDir + "WorkingWithChangeStyleOfTocLevel.ModifiedDocument.docx");
```

## خاتمة

في هذا الدليل ، شرحنا كيفية استخدام Aspose.Words for .NET لتغيير نمط مستوى جدول محتويات مستند Word باستخدام كود المصدر C # المقدم. باتباع الخطوات المقدمة ، يمكنك بسهولة تخصيص نمط جدول المحتويات في مستندات Word الخاصة بك في تطبيق C # الخاص بك. يوفر Aspose.Words مرونة وقوة هائلة للعمل مع أنماط وتنسيقات مستنداتك ، مما يسمح لك بإنشاء مستندات Word جذابة واحترافية.