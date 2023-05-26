---
title: تجنب تضمين الخطوط الأساسية
linktitle: تجنب تضمين الخطوط الأساسية
second_title: Aspose.Words لمراجع .NET API
description: تعرف على كيفية تجنب تضمين الخط الأساسي عند تحويل مستندات Word إلى PDF باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /ar/net/programming-with-pdfsaveoptions/avoid-embedding-core-fonts/
---

في هذا البرنامج التعليمي ، سنوجهك عبر خطوات استخدام ميزة Avoid Basic Font Embedding مع Aspose.Words for .NET. تتيح لك هذه الميزة التحكم في ما إذا كان يجب تضمين الخطوط الأساسية مثل Arial و Times New Roman وما إلى ذلك في ملف PDF عند تحويل مستند Word. اتبع الخطوات التالية:

## الخطوة 1: تحميل المستند

ابدأ بتحميل مستند Word الذي تريد تحويله إلى PDF:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Rendering.docx");
```

تأكد من تحديد المسار الصحيح لمستند Word الخاص بك.

## الخطوة 2: تعيين خيارات تحويل PDF

قم بإنشاء مثيل لفئة PdfSaveOptions وقم بتمكين تجنب تضمين الخط الأساسي:

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions { UseCoreFonts = true };
```

يتحكم هذا الخيار فيما إذا كان يجب تضمين الخطوط الأساسية في ملف PDF أم لا.

## الخطوة 3: تحويل المستند إلى PDF

 استخدم ال`Save` طريقة لتحويل مستند Word إلى PDF عن طريق تحديد خيارات التحويل:

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.AvoidEmbeddingCoreFonts.pdf", saveOptions);
```

تأكد من تحديد المسار الصحيح لحفظ ملف PDF المحول.

### مثال على شفرة المصدر لتجنب تضمين الخطوط الأساسية باستخدام Aspose.Words for .NET

إليك الكود المصدري الكامل لاستخدام الميزة لتجنب تضمين الخط الأساسي مع Aspose.Words for .NET:

```csharp

	// المسار إلى دليل المستندات.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	// لن يتم تضمين ملف PDF الناتج مع الخطوط الأساسية مثل Arial و Times New Roman وما إلى ذلك.
	PdfSaveOptions saveOptions = new PdfSaveOptions { UseCoreFonts = true };
	
	doc.Save(dataDir + "WorkingWithPdfSaveOptions.AvoidEmbeddingCoreFonts.pdf", saveOptions);

```

باتباع هذه الخطوات ، يمكنك التحكم بسهولة فيما إذا كان يجب تضمين الخطوط الأساسية في ملف PDF عند تحويل مستند Word باستخدام Aspose.Words for .NET.

