---
title: تعطيل تضمين خطوط Windows
linktitle: تعطيل تضمين خطوط Windows
second_title: Aspose.Words لمراجع .NET API
description: تعرف على كيفية تعطيل تضمين خطوط Windows عند تحويل المستندات إلى PDF باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /ar/net/programming-with-pdfsaveoptions/disable-embed-windows-fonts/
---

في هذا البرنامج التعليمي ، سنرشدك عبر خطوات تعطيل تضمين خطوط Windows في مستند PDF باستخدام Aspose.Words for .NET. من خلال تعطيل دمج الخط ، يمكنك تقليل حجم ملف PDF الذي تم إنشاؤه. اتبع الخطوات التالية:

## الخطوة 1: تحميل المستند

ابدأ بتحميل المستند الذي تريد تحويله إلى PDF:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Rendering.docx");
```

تأكد من تحديد المسار الصحيح للمستند الخاص بك.

## الخطوة 2: تعيين خيارات حفظ PDF

قم بإنشاء مثيل لفئة PdfSaveOptions وحدد كيفية تضمين الخطوط:

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions { FontEmbeddingMode = PdfFontEmbeddingMode.EmbedNone };
```

يتيح لك هذا الخيار إلغاء تنشيط تكامل خطوط Windows في ملف PDF الذي تم إنشاؤه.

## الخطوة 3: تحويل المستند إلى PDF

 استخدم ال`Save` طريقة تحويل المستند إلى PDF مع تحديد خيارات التحويل:

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.DisableEmbedWindowsFonts.pdf", saveOptions);
```

تأكد من تحديد المسار الصحيح لحفظ ملف PDF المحول.

### مثال على شفرة المصدر لـ Disable Embed Windows Fonts باستخدام Aspose.Words for .NET

إليك كود المصدر الكامل لتعطيل تضمين خطوط Windows في مستند PDF باستخدام Aspose.Words for .NET:

```csharp

	// المسار إلى دليل المستندات.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	// سيتم حفظ ملف PDF الناتج بدون تضمين خطوط Windows القياسية.
	PdfSaveOptions saveOptions = new PdfSaveOptions { FontEmbeddingMode = PdfFontEmbeddingMode.EmbedNone };
	
	doc.Save(dataDir + "WorkingWithPdfSaveOptions.DisableEmbedWindowsFonts.pdf", saveOptions);

```
باتباع هذه الخطوات ، يمكنك بسهولة تعطيل دمج خطوط Windows في مستند PDF باستخدام Aspose.Words for .NET.

