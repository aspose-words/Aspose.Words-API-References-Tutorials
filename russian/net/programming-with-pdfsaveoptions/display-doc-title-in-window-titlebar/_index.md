---
title: عرض عنوان المستند في شريط عنوان النافذة
linktitle: عرض عنوان المستند في شريط عنوان النافذة
second_title: Aspose.Words لمراجع .NET API
description: تعرف على كيفية عرض عنوان المستند في شريط عنوان النافذة عند التحويل إلى PDF باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /ru/net/programming-with-pdfsaveoptions/display-doc-title-in-window-titlebar/
---

في هذا البرنامج التعليمي ، سنوجهك خلال الخطوات لعرض عنوان المستند في شريط عنوان النافذة باستخدام Aspose.Words for .NET. تتيح لك هذه الميزة عرض عنوان المستند في شريط عنوان النافذة عند فتح مستند PDF الذي تم إنشاؤه. اتبع الخطوات التالية:

## الخطوة 1: تحميل المستند

ابدأ بتحميل المستند الذي تريد تحويله إلى PDF:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Rendering.docx");
```

تأكد من تحديد المسار الصحيح للمستند الخاص بك.

## الخطوة 2: تكوين خيارات حفظ PDF

قم بإنشاء مثيل لفئة PdfSaveOptions وقم بتمكين عرض عنوان المستند في شريط عنوان النافذة:

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions { DisplayDocTitle = true };
```

يتيح هذا الخيار عرض عنوان المستند في شريط عنوان النافذة عند التحويل إلى PDF.

## الخطوة 3: تحويل المستند إلى PDF

 استخدم ال`Save` طريقة تحويل المستند إلى PDF مع تحديد خيارات التحويل:

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.DisplayDocTitleInWindowTitlebar.pdf", saveOptions);
```

تأكد من تحديد المسار الصحيح لحفظ ملف PDF المحول.

### مثال على شفرة المصدر لعرض عنوان المستند في شريط عناوين النافذة باستخدام Aspose.Words for .NET

إليك كود المصدر الكامل لعرض عنوان المستند في شريط عنوان النافذة في مستند PDF باستخدام Aspose.Words for .NET:

```csharp

	// المسار إلى دليل المستندات.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	PdfSaveOptions saveOptions = new PdfSaveOptions { DisplayDocTitle = true };

	doc.Save(dataDir + "WorkingWithPdfSaveOptions.DisplayDocTitleInWindowTitlebar.pdf", saveOptions);
        
```
باتباع هذه الخطوات ، يمكنك بسهولة عرض عنوان المستند في شريط عنوان النافذة عند التحويل إلى PDF باستخدام Aspose.Words for .NET.

