---
title: الاحتفاظ بتنسيق المصدر
linktitle: الاحتفاظ بتنسيق المصدر
second_title: Aspose.Words واجهة برمجة تطبيقات معالجة المستندات
description: تعرف على كيفية إلحاق مستند مصدر بالمستند الوجهة مع الحفاظ على التنسيق الأصلي باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /ar/net/join-and-append-documents/keep-source-formatting/
---

يوضح هذا البرنامج التعليمي كيفية إلحاق مستند مصدر بالمستند الوجهة مع الحفاظ على التنسيق الأصلي للمستند المصدر باستخدام Aspose.Words لـ .NET.

## الخطوة 1: إعداد المشروع

تأكد من أن لديك المتطلبات الأساسية التالية:

-  تم تثبيت Aspose.Words لمكتبة .NET. يمكنك تنزيله من[Aspose.Releases]https://releases.aspose.com/words/net/ أو استخدم مدير الحزم NuGet لتثبيته.
- مسار دليل المستند حيث سيتم حفظ المستندات المصدر والوجهة.

## الخطوة 2: إنشاء الوجهة والمستندات المصدر

 إنشاء مثيلات`Document` للوجهة والوثائق المصدر.

```csharp
// المسار إلى دليل المستندات الخاص بك
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document dstDoc = new Document();
dstDoc.FirstSection.Body.AppendParagraph("Destination document text.");

Document srcDoc = new Document();
srcDoc.FirstSection.Body.AppendParagraph("Source document text.");
```

## الخطوة 3: إلحاق المستند المصدر بالمستند الوجهة

 استخدم ال`AppendDocument` طريقة المستند الوجهة لإلحاق المستند المصدر. يمر`ImportFormatMode.KeepSourceFormatting`كوضع تنسيق الاستيراد للاحتفاظ بالتنسيق الأصلي للمستند المصدر.

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## الخطوة 4: احفظ المستند المعدل

 احفظ المستند المعدل باستخدام`Save` طريقة`Document` هدف.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.KeepSourceFormatting.docx");
```

يؤدي هذا إلى إكمال تنفيذ إلحاق مستند مصدر بالمستند الوجهة مع الاحتفاظ بالتنسيق الأصلي باستخدام Aspose.Words for .NET.

### مثال على التعليمات البرمجية المصدر للاحتفاظ بتنسيق المصدر باستخدام Aspose.Words لـ .NET 

```csharp
	// المسار إلى دليل المستندات الخاص بك
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document dstDoc = new Document();
	dstDoc.FirstSection.Body.AppendParagraph("Destination document text. ");
	Document srcDoc = new Document();
	srcDoc.FirstSection.Body.AppendParagraph("Source document text. ");
	// إلحاق المستند المصدر بالمستند الوجهة.
	// قم بتمرير وضع التنسيق للاحتفاظ بالتنسيق الأصلي للمستند المصدر عند استيراده.
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.KeepSourceFormatting.docx");
```