---
title: إضافة علامات بيدي في مستند Word
linktitle: إضافة علامات بيدي في مستند Word
second_title: Aspose.Words واجهة برمجة تطبيقات معالجة المستندات
description: تعلم كيفية إضافة علامات Bidi إلى مستند Word باستخدام Aspose.Words لـ .NET وإنشاء مستندات احترافية متعددة اللغات.
type: docs
weight: 10
url: /ar/net/programming-with-txtsaveoptions/add-bidi-marks/
---

تعد Aspose.Words for .NET مكتبة قوية لإنشاء مستندات Word وتحريرها ومعالجتها في تطبيق C#. من بين الميزات التي يقدمها Aspose.Words هي القدرة على إضافة علامات Bidi (ثنائية الاتجاه) إلى المستند. في هذا الدليل، سنرشدك إلى كيفية استخدام الكود المصدري لـ C# الخاص بـ Aspose.Words لـ .NET لإضافة علامات Bidi إلى المستند.

## فهم مكتبة Aspose.Words

قبل الغوص في التعليمات البرمجية، من المهم فهم مكتبة Aspose.Words الخاصة بـ .NET. Aspose.Words هي مكتبة شائعة تجعل معالجة الكلمات باستخدام مستندات Word سهلة وفعالة. وهو يقدم مجموعة واسعة من الميزات لإنشاء مستندات Word وتحريرها ومعالجتها، بما في ذلك إضافة علامات Bidi.

## إنشاء المستند وإضافة المحتوى

الخطوة الأولى هي إنشاء مستند جديد وإضافة محتوى إليه. استخدم فئة المستند لإنشاء مثيل مستند جديد. ثم استخدم فئة DocumentBuilder لإضافة نص إلى المستند. هنا مثال :

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder. Writen("Hello world!");
builder.ParagraphFormat.Bidi = true;
builder. Writen("שלום עולם!");
builder. Writen("مرحبا بالعالم!");
```

في هذا المثال، نقوم بإنشاء مستند جديد واستخدام DocumentBuilder لإضافة نص. لقد أضفنا ثلاثة أسطر من النص: واحد باللغة الإنجليزية، وواحد باللغة العبرية، وواحد باللغة العربية لتوضيح إضافة محتوى بلغات مختلفة.

## تمت إضافة علامات بيدي

بمجرد إضافة المحتوى، يمكننا الآن إضافة علامات Bidi إلى المستند. لهذا، نستخدم فئة TxtSaveOptions وقمنا بتعيين خاصية AddBidiMarks على true. إليك الطريقة:

```csharp
TxtSaveOptions saveOptions = new TxtSaveOptions { AddBidiMarks = true };
doc.Save(dataDir + "WorkingWithTxtSaveOptions.AddBidiMarks.txt", saveOptions);
```

في هذا المثال، قمنا بإنشاء مثيل لـ TxtSaveOptions وقمنا بتعيين الخاصية AddBidiMarks على true. بعد ذلك، نستخدم طريقة Save لفئة المستند لحفظ المستند بعلامات Bidi.

### مثال على التعليمات البرمجية المصدر لوظيفة "إضافة علامات Bidi" مع Aspose.Words لـ .NET

```csharp
// المسار إلى دليل المستندات الخاص بك
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// قم بإنشاء المستند وإضافة المحتوى
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder. Writen("Hello world!");
builder.ParagraphFormat.Bidi = true;
builder. Writen("שלום עולם!");
builder. Writen("مرحبا بالعالم!");

// أضف علامات بيدي
TxtSaveOptions saveOptions = new TxtSaveOptions { AddBidiMarks = true

  };
doc.Save(dataDir + "WorkingWithTxtSaveOptions.AddBidiMarks.txt", saveOptions);
```

## خاتمة

في هذا الدليل، شرحنا كيفية استخدام Aspose.Words لـ .NET لإضافة علامات Bidi إلى مستند Word باستخدام كود مصدر C# المتوفر. باتباع الخطوات المتوفرة، يمكنك بسهولة إضافة علامات Bidi إلى مستندات Word الخاصة بك في تطبيق C# الخاص بك. يوفر Aspose.Words مرونة وقوة هائلة لمعالجة الكلمات من خلال تنسيق النص وإدارة اللغة، مما يسمح لك بإنشاء مستندات متعددة اللغات بشكل احترافي.

### أسئلة مكررة

#### س: ما هو Aspose.Words لـ .NET؟
تعد Aspose.Words for .NET مكتبة قوية لإنشاء مستندات Word وتحريرها ومعالجتها في تطبيق C#. وهو يقدم العديد من الميزات لمعالجة الكلمات مع مستندات Word، بما في ذلك إضافة علامات Bidi (ثنائية الاتجاه).

#### س: ما هي الميزات التي يقدمها Aspose.Words لـ .NET؟
يقدم Aspose.Words for .NET نطاقًا واسعًا من الميزات لإنشاء مستندات Word وتحريرها ومعالجتها. تتضمن بعض هذه الميزات إنشاء المستندات وإضافة محتوى وتنسيق النص وإدارة الجداول ودمج المستندات وتقسيمها وتحويل المستندات والمزيد.

#### س: كيف يمكنني إضافة علامات ثنائية الاتجاه إلى مستند Word باستخدام Aspose.Words لـ .NET؟
يمكنك إضافة علامات Bidi إلى مستند Word باتباع الخطوات التالية:

 قم بإنشاء مستند جديد باستخدام`Document` فصل.

 استخدم ال`DocumentBuilder` فئة لإضافة محتوى إلى المستند.

 بمجرد إضافة المحتوى، استخدم`TxtSaveOptions` فئة وتعيين`AddBidiMarks`الملكية ل`true`.

 احفظ المستند بعلامات Bidi باستخدام`Save` طريقة`Document` فصل.

#### س: هل يدعم Aspose.Words لغات متعددة لإضافة علامات ثنائية الاتجاه؟
نعم، يدعم Aspose.Words لغات متعددة لإضافة علامات ثنائية الاتجاه. يمكنك إضافة علامات Bidi إلى نص بلغات مختلفة، مثل الإنجليزية والعبرية والعربية، باستخدام Aspose.Words for .NET.

#### س: هل هناك أي خيارات إضافية لحفظ المستند بعلامات Bidi؟
 نعم، يمكنك تحديد خيارات أخرى عند حفظ المستند بعلامات Bidi باستخدام`TxtSaveOptions` فصل. على سبيل المثال، يمكنك ضبط تنسيق حفظ المستند وخيارات الترميز وما إلى ذلك.