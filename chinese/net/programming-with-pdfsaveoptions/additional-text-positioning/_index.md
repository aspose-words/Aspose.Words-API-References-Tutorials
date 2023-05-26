---
title: نص إضافي المواقع
linktitle: نص إضافي المواقع
second_title: Aspose.Words لمراجع .NET API
description: تعرف على كيفية التحكم في موضع النص الإضافي عند تحويل مستندات Word إلى PDF باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /zh/net/programming-with-pdfsaveoptions/additional-text-positioning/
---

في هذا البرنامج التعليمي ، سنوجهك عبر خطوات استخدام ميزة تحديد موضع النص الإضافية مع Aspose.Words for .NET. تتيح لك هذه الميزة التحكم في وضع نص إضافي عند تحويل مستند Word إلى PDF. اتبع الخطوات التالية:

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

