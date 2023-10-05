---
title: إدراج مستند مع منشئ
linktitle: إدراج مستند مع منشئ
second_title: Aspose.Words واجهة برمجة تطبيقات معالجة المستندات
description: تعرف على كيفية إدراج مستند في نهاية مستند آخر باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /ar/net/join-and-append-documents/insert-document-with-builder/
---

 يشرح هذا البرنامج التعليمي كيفية استخدام Aspose.Words لـ .NET لإدراج مستند في مستند آخر باستخدام`DocumentBuilder` فصل. يوضح كود المصدر المقدم كيفية إدراج مستند في نهاية مستند آخر مع الحفاظ على تنسيق المصدر.

## الخطوة 1: إعداد المشروع

تأكد من أن لديك المتطلبات الأساسية التالية:

-  تم تثبيت Aspose.Words لمكتبة .NET. يمكنك تنزيله من[Aspose.Releases]https://releases.aspose.com/words/net/ أو استخدم مدير الحزم NuGet لتثبيته.
- مسار دليل المستند حيث توجد المستندات المصدر والوجهة.

## الخطوة 2: افتح المستندات المصدر والوجهة

 افتح المستندات المصدر والوجهة باستخدام`Document` منشئ الطبقة. يستبدل`"YOUR DOCUMENT DIRECTORY"` بالمسار الفعلي إلى دليل المستندات الخاص بك.

```csharp
// المسار إلى دليل المستندات الخاص بك
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document srcDoc = new Document(dataDir + "Document source.docx");
Document dstDoc = new Document(dataDir + "Northwind traders.docx");
```

## الخطوة 3: تهيئة DocumentBuilder

 إنشاء مثيل جديد لـ`DocumentBuilder` فئة وتمرير المستند الوجهة كمعلمة.

```csharp
DocumentBuilder builder = new DocumentBuilder(dstDoc);
```

## الخطوة 4: ضع DocumentBuilder

 حرك ال`DocumentBuilder` إلى نهاية المستند باستخدام`MoveToDocumentEnd` طريقة. قم بإدراج فاصل صفحات لفصل المحتوى الموجود عن المستند المدرج.

```csharp
builder.MoveToDocumentEnd();
builder.InsertBreak(BreakType.PageBreak);
```

## الخطوة 5: أدخل المستند المصدر

 استخدم ال`InsertDocument` طريقة`DocumentBuilder` فئة لإدراج المستند المصدر في المستند الوجهة. اضبط وضع تنسيق الاستيراد على`ImportFormatMode.KeepSourceFormatting` للحفاظ على تنسيق المصدر.

```csharp
builder.InsertDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## الخطوة 6: احفظ المستند المعدل

 وأخيرًا، احفظ مستند الوجهة المعدل باستخدام الملف`Save` طريقة`Document` هدف.

```csharp
builder.Document.Save(dataDir + "JoinAndAppendDocuments.InsertDocumentWithBuilder.docx");
```

يكمل هذا تنفيذ إدراج مستند في مستند آخر باستخدام Aspose.Words لـ .NET.

### مثال على التعليمات البرمجية المصدر لـ Insert Document With Builder باستخدام Aspose.Words لـ .NET 

```csharp
	// المسار إلى دليل المستندات الخاص بك
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Northwind traders.docx");
	DocumentBuilder builder = new DocumentBuilder(dstDoc);
	builder.MoveToDocumentEnd();
	builder.InsertBreak(BreakType.PageBreak);
	builder.InsertDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
	builder.Document.Save(dataDir + "JoinAndAppendDocuments.InsertDocumentWithBuilder.docx");
```