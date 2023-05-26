---
title: Dml 3DEffects التقديم
linktitle: Dml 3DEffects التقديم
second_title: Aspose.Words لمراجع .NET API
description: تعرف على كيفية تمكين عرض تأثيرات DML ثلاثية الأبعاد عند التحويل إلى PDF باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /zh/net/programming-with-pdfsaveoptions/dml-3deffects-rendering/
---

في هذا البرنامج التعليمي ، سنرشدك خلال الخطوات لتمكين عرض تأثير 3D DML عند التحويل إلى PDF باستخدام Aspose.Words for .NET. هذا يحافظ على التأثيرات ثلاثية الأبعاد في مستند PDF الذي تم إنشاؤه. اتبع الخطوات التالية:

## الخطوة 1: تحميل المستند

ابدأ بتحميل المستند الذي تريد تحويله إلى PDF:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Rendering.docx");
```

تأكد من تحديد المسار الصحيح للمستند الخاص بك.

## الخطوة 2: تكوين خيارات حفظ PDF

قم بإنشاء مثيل لفئة PdfSaveOptions وقم بتمكين العرض المتقدم لتأثيرات 3D DML:

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions { Dml3DEffectsRenderingMode = Dml3DEffectsRenderingMode.Advanced };
```

يحافظ هذا الخيار على التأثيرات ثلاثية الأبعاد في مستند PDF الذي تم إنشاؤه.

## الخطوة 3: تحويل المستند إلى PDF

 استخدم ال`Save` طريقة لتحويل المستند إلى PDF مع تحديد خيارات الحفظ:

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.Dml3DEffectsRendering.pdf", saveOptions);
```

تأكد من تحديد المسار الصحيح لحفظ ملف PDF المحول.

### مثال على شفرة المصدر لـ Dml 3DEffects Rendering باستخدام Aspose.Words for .NET

```csharp

	// المسار إلى دليل المستندات.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	PdfSaveOptions saveOptions = new PdfSaveOptions { Dml3DEffectsRenderingMode = Dml3DEffectsRenderingMode.Advanced };

	doc.Save(dataDir + "WorkingWithPdfSaveOptions.Dml3DEffectsRendering.pdf", saveOptions);
	 
```

باتباع هذه الخطوات ، يمكنك بسهولة تمكين عرض تأثيرات DML ثلاثية الأبعاد عند التحويل إلى PDF باستخدام Aspose.Words for .NET.



