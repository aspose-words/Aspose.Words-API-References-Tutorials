---
title: إرفاق نصوص PDF مع مواضع نصية إضافية
linktitle: إرفاق نصوص PDF مع مواضع نصية إضافية
second_title: واجهة برمجة تطبيقات معالجة المستندات Aspose.Words
description: تعرف على كيفية تعديل وضع نصوص PDF باستخدام مواضع نصية إضافية عند تحويل مستندات Word إلى PDF باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /ar/net/programming-with-pdfsaveoptions/additional-text-positioning/
---

في هذا البرنامج التعليمي ، سنرشدك عبر خطوات عدم تحسين منشورات نص PDF مع ميزة تحديد موضع النص الإضافية باستخدام Aspose.Words for .NET. تتيح لك هذه الميزة التحكم في وضع نص إضافي عند تحويل مستند Word إلى PDF. اتبع الخطوات التالية:

## الخطوة 1: تحميل المستند

ابدأ بتحميل مستند Word الذي تريد تحويله إلى PDF:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Rendering.docx");
```

تأكد من تحديد المسار الصحيح لمستند Word الخاص بك.

## الخطوة 2: تعيين خيارات تحويل PDF

قم بإنشاء مثيل لفئة PdfSaveOptions وقم بتمكين وضع نص إضافي:

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions { AdditionalTextPositioning = true };
```

يتحكم هذا الخيار في الموضع الدقيق للنص الإضافي في ملف PDF.

## الخطوة 3: تحويل المستند إلى PDF

 استخدم ال`Save` طريقة لتحويل مستند Word إلى PDF عن طريق تحديد خيارات التحويل:

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.AdditionalTextPositioning.pdf", saveOptions);
```

تأكد من تحديد المسار الصحيح لحفظ ملف PDF المحول.

### مثال على شفرة المصدر لتحديد موضع النص الإضافي باستخدام Aspose.Words for .NET

إليك شفرة المصدر الكاملة لاستخدام وظيفة تحديد موضع النص الإضافية مع Aspose.Words for .NET:


```csharp

	// المسار إلى دليل المستندات.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	PdfSaveOptions saveOptions = new PdfSaveOptions { AdditionalTextPositioning = true };

	doc.Save(dataDir + "WorkingWithPdfSaveOptions.AdditionalTextPositioning.pdf", saveOptions);

```
باتباع هذه الخطوات ، يمكنك التحكم بسهولة في وضع نص إضافي عند تحويل مستند Word إلى PDF باستخدام Aspose.Words for .NET.


## خاتمة

في هذا البرنامج التعليمي ، شرحنا كيفية تحسين وضع النص في ملف PDF عن طريق إضافة نص إضافي باستخدام Aspose.Words for .NET. باتباع الخطوات الموضحة ، يمكنك التحكم بدقة في موضع النص الإضافي عند تحويل مستند Word إلى PDF. تأكد من تحديد المسار الصحيح لمستند Word الخاص بك وتكوين الخيارات للتحويل إلى PDF حسب الحاجة.

### أسئلة مكررة

#### س: ما هي ميزة وضع النص الإضافية في ملف PDF؟
ج: تساعد ميزة "وضع نص إضافي في PDF" في التحكم في الموضع الدقيق للنص الإضافي عند تحويل مستند Word إلى PDF. عند تمكين هذه الميزة ، يمكنك تحديد الموقع الدقيق للنص الإضافي في ملف PDF.

#### س: كيف يمكنني استخدام Aspose.Words for .NET لتحسين وضع النص في ملف PDF عن طريق إضافة نص إضافي؟
ج: لتحسين وضع النص في ملف PDF عن طريق إضافة نص إضافي باستخدام Aspose.Words for .NET ، اتبع الخطوات التالية:

 قم بتعيين مسار الدليل حيث توجد المستندات الخاصة بك عن طريق الاستبدال`"YOUR DOCUMENTS DIRECTORY"` مع المسار الفعلي لدليل المستندات الخاص بك.

 قم بتحميل مستند Word الذي تريد تحويله إلى PDF باستخدام ملف`Document` class وحدد المسار إلى مستند Word في دليل المستندات المحدد.

 قم بتكوين الخيارات للتحويل كملف PDF عن طريق إنشاء مثيل لملف`PdfSaveOptions` الطبقة وتمكين`AdditionalTextPositioning` الخيار لتمكين الدقة 
وضع نص إضافي في ملف PDF.

 احفظ المستند بتنسيق PDF باستخدام ملف`Save` طريقة`Document`فئة تحدد المسار وخيارات الحفظ.

#### س: ما هي فوائد تحسين وضع النص في ملف PDF بإضافة نص إضافي؟
ج: فوائد تحسين وضع النص في ملف PDF عن طريق إضافة نص إضافي هي:

التحكم الدقيق في موقع النص الإضافي: يمكنك تحديد الموقع الدقيق للنص الإضافي في ملف PDF ، مما يتيح لك تحديد موضع النص بدقة.

تخطيط مستند محسّن: من خلال التحكم في موضع نص إضافي ، يمكنك تحسين تخطيط مستند PDF وتحقيق نتيجة نهائية أكثر دقة وجمالية.