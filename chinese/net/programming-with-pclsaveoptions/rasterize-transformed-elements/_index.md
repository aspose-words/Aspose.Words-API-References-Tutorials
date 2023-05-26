---
title: تنقيط العناصر المحولة
linktitle: تنقيط العناصر المحولة
second_title: Aspose.Words لمراجع .NET API
description: تعرف على كيفية تعطيل التحويل النقطي للعناصر المحولة عند التحويل إلى تنسيق PCL باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /zh/net/programming-with-pclsaveoptions/rasterize-transformed-elements/
---

Aspose.Words for .NET مكتبة قوية لإنشاء مستندات Word ومعالجتها وتحويلها في تطبيق C #. من بين الميزات التي تقدمها Aspose.Words القدرة على تحويل العناصر المحوّلة إلى نقطية عند تحويل المستندات إلى تنسيقات مختلفة. في هذا الدليل ، سنوضح لك كيفية استخدام الكود المصدري C # لـ Aspose.Words for .NET لتعطيل تنقيط العناصر المحولة عند تحويل مستند إلى تنسيق PCL.

## فهم مكتبة Aspose.Words

قبل التعمق في الكود ، من المهم فهم مكتبة Aspose.Words لـ .NET. Aspose.Words مكتبة شائعة تجعل العمل مع مستندات Word أمرًا سهلاً وفعالاً. يوفر مجموعة واسعة من الميزات لإنشاء مستندات Word وتحريرها وتحويلها ، بما في ذلك دعم تنقيط العناصر المحولة أثناء التحويل.

## تحميل مستند Word

الخطوة الأولى هي تحميل مستند Word الذي تريد تحويله إلى تنسيق PCL. استخدم فئة المستند لتحميل المستند من الملف المصدر. هنا مثال :

```csharp
Document doc = new Document(dataDir + "Rendering.docx");
```

في هذا المثال ، نقوم بتحميل مستند "Rendering.docx" الموجود في دليل المستندات.

## تكوين خيارات النسخ الاحتياطي

الخطوة التالية هي تكوين خيارات الحفظ للتحويل إلى تنسيق PCL. استخدم فئة PclSaveOptions وقم بتعيين الخاصية RasterizeTransformedElements على false. هيريس كيفية القيام بذلك:

```csharp
PclSaveOptions saveOptions = new PclSaveOptions
{
     SaveFormat = SaveFormat.Pcl,
     RasterizeTransformedElements = false
};
```

قمنا بإنشاء كائن PclSaveOptions جديد وقمنا بتعيين خاصية SaveFormat على SaveFormat.Pcl لتحديد أننا نريد حفظ المستند بتنسيق PCL. بعد ذلك ، قمنا بتعيين الخاصية RasterizeTransformedElements على false لتعطيل تنقيط العناصر المحولة.

## تحويل المستند إلى تنسيق PCL

الآن بعد أن قمنا بتكوين خيارات الحفظ ، يمكننا المتابعة لتحويل المستند إلى تنسيق PCL. استخدم طريقة Save لفئة Document لحفظ المستند المحول بتنسيق PCL عن طريق تحديد خيارات الحفظ. هنا مثال :

```csharp
doc.Save(dataDir + "WorkingWithPclSaveOptions.RasterizeTransformedElements.pcl", saveOptions);
```

في هذا المثال ، نحفظ المستند المحول باسم "WorkingWithPclSaveOptions.RasterizeTransformedElements.pcl" باستخدام خيارات الحفظ المحددة.

### مثال على شفرة المصدر لميزة "Rasterize Transformed Elements" مع Aspose.Words for .NET

```csharp
// المسار إلى دليل المستندات الخاص بك
string dataDir = "YOUR DOCUMENTS DIRECTORY";

//قم بتحميل مستند Word


Document doc = new Document(dataDir + "Rendering.docx");

// تكوين خيارات النسخ الاحتياطي للتحويل إلى تنسيق PCL
PclSaveOptions saveOptions = new PclSaveOptions
{
     SaveFormat = SaveFormat.Pcl,
     RasterizeTransformedElements = false
};

// قم بتحويل المستند إلى تنسيق PCL
doc.Save(dataDir + "WorkingWithPclSaveOptions.RasterizeTransformedElements.pcl", saveOptions);
```

## خاتمة

في هذا الدليل ، تناولنا كيفية استخدام Aspose.Words for .NET لتعطيل تنقيط العناصر المحولة عند تحويل مستند إلى تنسيق PCL باستخدام كود المصدر C # المقدم. باتباع الخطوات المقدمة ، يمكنك بسهولة التحكم في سلوك التنقيط للعناصر المحولة عند تحويل مستندات Word إلى تنسيقات مختلفة. يوفر Aspose.Words مرونة وقوة هائلة للعمل مع العناصر المحولة ، مما يسمح لك بإنشاء مستندات محولة بدقة لاحتياجاتك الخاصة.