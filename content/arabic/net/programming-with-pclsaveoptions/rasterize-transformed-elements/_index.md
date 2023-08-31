---
title: تنقيط العناصر المحولة
linktitle: تنقيط العناصر المحولة
second_title: Aspose.Words واجهة برمجة تطبيقات معالجة المستندات
description: تعرف على كيفية تعطيل التنقيط للعناصر المحولة عند التحويل إلى تنسيق PCL باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /ar/net/programming-with-pclsaveoptions/rasterize-transformed-elements/
---

Aspose.Words for .NET هي مكتبة قوية لإنشاء مستندات Word ومعالجتها وتحويلها في تطبيق C#. من بين الميزات التي يقدمها Aspose.Words هي القدرة على تنقيط العناصر المحولة عند تحويل المستندات إلى تنسيقات مختلفة. في هذا الدليل، سنوضح لك كيفية استخدام كود مصدر C# الخاص بـ Aspose.Words لـ .NET لتعطيل تنقيط العناصر المحولة عند تحويل مستند إلى تنسيق PCL.

## فهم مكتبة Aspose.Words

قبل الغوص في التعليمات البرمجية، من المهم فهم مكتبة Aspose.Words الخاصة بـ .NET. Aspose.Words هي مكتبة شائعة تجعل معالجة الكلمات باستخدام مستندات Word سهلة وفعالة. وهو يقدم مجموعة واسعة من الميزات لإنشاء مستندات Word وتحريرها وتحويلها، بما في ذلك دعم تنقيط العناصر المحولة أثناء التحويل.

## تحميل مستند الوورد

الخطوة الأولى هي تحميل مستند Word الذي تريد تحويله إلى تنسيق PCL. استخدم فئة المستند لتحميل المستند من الملف المصدر. هنا مثال :

```csharp
Document doc = new Document(dataDir + "Rendering.docx");
```

في هذا المثال، نقوم بتحميل مستند "Rendering.docx" الموجود في دليل المستندات.

## تكوين خيارات النسخ الاحتياطي

الخطوة التالية هي تكوين خيارات الحفظ للتحويل إلى تنسيق PCL. استخدم فئة PclSaveOptions وقم بتعيين الخاصية RasterizeTransformedElements إلى false. هيريس كيفية القيام بذلك:

```csharp
PclSaveOptions saveOptions = new PclSaveOptions
{
     SaveFormat = SaveFormat.Pcl,
     RasterizeTransformedElements = false
};
```

نقوم بإنشاء كائن PclSaveOptions جديد وقمنا بتعيين خاصية SaveFormat على SaveFormat.Pcl لتحديد أننا نريد حفظ المستند بتنسيق PCL. بعد ذلك، قمنا بتعيين خاصية RasterizeTransformedElements على false لتعطيل تنقيط العناصر المحولة.

## تحويل المستند إلى تنسيق PCL

الآن بعد أن قمنا بتكوين خيارات الحفظ، يمكننا المتابعة لتحويل المستند إلى تنسيق PCL. استخدم طريقة Save الخاصة بفئة Document لحفظ المستند المحول بتنسيق PCL عن طريق تحديد خيارات الحفظ. هنا مثال :

```csharp
doc.Save(dataDir + "WorkingWithPclSaveOptions.RasterizeTransformedElements.pcl", saveOptions);
```

في هذا المثال، نقوم بحفظ المستند المحول باسم "WorkingWithPclSaveOptions.RasterizeTransformedElements.pcl" باستخدام خيارات الحفظ المحددة.

### مثال على التعليمات البرمجية المصدر لميزة "تنقيط العناصر المحولة" باستخدام Aspose.Words لـ .NET

```csharp
// المسار إلى دليل المستندات الخاص بك
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// قم بتحميل مستند الوورد


Document doc = new Document(dataDir + "Rendering.docx");

// قم بتكوين خيارات النسخ الاحتياطي للتحويل إلى تنسيق PCL
PclSaveOptions saveOptions = new PclSaveOptions
{
     SaveFormat = SaveFormat.Pcl,
     RasterizeTransformedElements = false
};

// تحويل المستند إلى تنسيق PCL
doc.Save(dataDir + "WorkingWithPclSaveOptions.RasterizeTransformedElements.pcl", saveOptions);
```

## خاتمة

في هذا الدليل، تناولنا كيفية استخدام Aspose.Words for .NET لتعطيل تنقيط العناصر المحولة عند تحويل مستند إلى تنسيق PCL باستخدام كود مصدر C# المتوفر. باتباع الخطوات المتوفرة، يمكنك التحكم بسهولة في سلوك التنقيط للعناصر المحولة عند تحويل مستندات Word إلى تنسيقات مختلفة. يوفر Aspose.Words مرونة وقوة هائلة للعمل مع العناصر المحولة، مما يسمح لك بإنشاء مستندات محولة بدقة وفقًا لاحتياجاتك المحددة.