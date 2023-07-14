---
title: الاحتفاظ بتنسيق المصدر
linktitle: الاحتفاظ بتنسيق المصدر
second_title: واجهة برمجة تطبيقات معالجة المستندات Aspose.Words
description: تعرف على كيفية إلحاق مستند مصدر بمستند وجهة مع الحفاظ على التنسيق الأصلي باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /ar/net/join-and-append-documents/keep-source-formatting/
---

يوضح هذا البرنامج التعليمي كيفية إلحاق مستند مصدر بمستند وجهة مع الحفاظ على التنسيق الأصلي للمستند المصدر باستخدام Aspose.Words for .NET.

## الخطوة 1: قم بإعداد المشروع

تأكد من أن لديك المتطلبات الأساسية التالية:

- تثبيت Aspose.Words لمكتبة .NET. يمكنك تنزيله من موقع Aspose الرسمي أو استخدام مدير حزمة NuGet لتثبيته.
- مسار دليل المستند حيث سيتم حفظ مستندات المصدر والوجهة.

## الخطوة 2: قم بإنشاء الوجهة والمستندات المصدر

 إنشاء مثيلات من`Document` للوجهة والمستندات المصدر.

```csharp
// المسار إلى دليل المستند الخاص بك
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document dstDoc = new Document();
dstDoc.FirstSection.Body.AppendParagraph("Destination document text.");

Document srcDoc = new Document();
srcDoc.FirstSection.Body.AppendParagraph("Source document text.");
```

## الخطوة 3: قم بإلحاق المستند المصدر بالمستند الوجهة

 استخدم ال`AppendDocument`طريقة المستند الوجهة لإلحاق المستند المصدر. يمر`ImportFormatMode.KeepSourceFormatting` كوضع تنسيق الاستيراد للاحتفاظ بالتنسيق الأصلي للمستند المصدر.

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## الخطوة 4: احفظ المستند المعدل

 احفظ المستند المعدل باستخدام ملف`Save` طريقة`Document` هدف.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.KeepSourceFormatting.docx");
```

هذا يكمل تنفيذ إلحاق مستند مصدر بمستند الوجهة مع الاحتفاظ بالتنسيق الأصلي باستخدام Aspose.Words for .NET.

### مثال على شفرة المصدر لـ Keep Source Formatting باستخدام Aspose.Words for .NET 

```csharp
	//المسار إلى دليل المستند الخاص بك
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document dstDoc = new Document();
	dstDoc.FirstSection.Body.AppendParagraph("Destination document text. ");
	Document srcDoc = new Document();
	srcDoc.FirstSection.Body.AppendParagraph("Source document text. ");
	// قم بإلحاق المستند المصدر بالمستند الوجهة.
	// قم بتمرير وضع التنسيق للاحتفاظ بالتنسيق الأصلي للمستند المصدر عند استيراده.
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.KeepSourceFormatting.docx");
```