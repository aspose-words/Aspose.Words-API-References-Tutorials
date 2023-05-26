---
title: أضف علامات ثنائية الاتجاه
linktitle: أضف علامات ثنائية الاتجاه
second_title: Aspose.Words لمراجع .NET API
description: تعلم كيفية إضافة علامات ثنائية الاتجاه إلى مستند Word باستخدام Aspose.Words for .NET وإنشاء مستندات احترافية متعددة اللغات.
type: docs
weight: 10
url: /ru/net/programming-with-txtsaveoptions/add-bidi-marks/
---

Aspose.Words for .NET مكتبة قوية لإنشاء مستندات Word وتحريرها ومعالجتها في تطبيق C #. من بين الميزات التي تقدمها Aspose.Words القدرة على إضافة علامات ثنائية الاتجاه (ثنائية الاتجاه) إلى المستند. في هذا الدليل ، سنرشدك إلى كيفية استخدام الكود المصدري C # الخاص بـ Aspose.Words for .NET لإضافة علامات ثنائية الاتجاه إلى مستند.

## فهم مكتبة Aspose.Words

قبل التعمق في الكود ، من المهم فهم مكتبة Aspose.Words لـ .NET. Aspose.Words مكتبة شائعة تجعل العمل مع مستندات Word أمرًا سهلاً وفعالاً. يوفر مجموعة واسعة من الميزات لإنشاء مستندات Word وتحريرها ومعالجتها ، بما في ذلك إضافة علامات ثنائية الاتجاه.

## إنشاء الوثيقة وإضافة المحتوى

تتمثل الخطوة الأولى في إنشاء مستند جديد وإضافة محتوى إليه. استخدم فئة المستند لإنشاء مثيل مستند جديد. ثم استخدم فئة DocumentBuilder لإضافة نص إلى المستند. هنا مثال :

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder. Writen("Hello world!");
builder.ParagraphFormat.Bidi = true;
builder. Writen("שלום עולם!");
builder. Writen("مرحبا بالعالم!");
```

في هذا المثال ، نقوم بإنشاء مستند جديد واستخدام DocumentBuilder لإضافة نص. لقد أضفنا ثلاثة أسطر نصية: واحد بالإنجليزية والآخر بالعبرية والآخر بالعربية لإثبات إضافة محتوى بلغات مختلفة.

## العلامات ثنائية الاتجاه المضافة

بمجرد إضافة المحتوى ، يمكننا الآن إضافة علامات ثنائية الاتجاه إلى المستند. لهذا ، نستخدم فئة TxtSaveOptions وقمنا بتعيين الخاصية AddBidiMarks على true. إليك الطريقة:

```csharp
TxtSaveOptions saveOptions = new TxtSaveOptions { AddBidiMarks = true };
doc.Save(dataDir + "WorkingWithTxtSaveOptions.AddBidiMarks.txt", saveOptions);
```

في هذا المثال ، قمنا بإنشاء مثيل لـ TxtSaveOptions وقمنا بتعيين الخاصية AddBidiMarks على true. بعد ذلك ، نستخدم طريقة Save لفئة Document لحفظ المستند بعلامات ثنائية الاتجاه.

### مثال على شفرة المصدر لوظيفة "Add Bidi Marks" مع Aspose.Words for .NET

```csharp
// المسار إلى دليل المستندات الخاص بك
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// قم بإنشاء المستند وإضافة محتوى
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder. Writen("Hello world!");
builder.ParagraphFormat.Bidi = true;
builder. Writen("שלום עולם!");
builder. Writen("مرحبا بالعالم!");

// أضف علامات ثنائية الاتجاه
TxtSaveOptions saveOptions = new TxtSaveOptions { AddBidiMarks = true

  };
doc.Save(dataDir + "WorkingWithTxtSaveOptions.AddBidiMarks.txt", saveOptions);
```

## خاتمة

في هذا الدليل ، أوضحنا كيفية استخدام Aspose.Words for .NET لإضافة علامات ثنائية الاتجاه إلى مستند Word باستخدام كود المصدر C # المقدم. باتباع الخطوات المقدمة ، يمكنك بسهولة إضافة علامات ثنائية الاتجاه إلى مستندات Word في تطبيق C # الخاص بك. يوفر Aspose.Words مرونة وقوة هائلة للعمل مع تنسيق النص وإدارة اللغة ، مما يسمح لك بإنشاء مستندات متعددة اللغات بشكل احترافي.