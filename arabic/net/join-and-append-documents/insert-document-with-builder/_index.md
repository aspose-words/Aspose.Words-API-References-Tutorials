---
title: قم بإدراج مستند باستخدام Builder
linktitle: قم بإدراج مستند باستخدام Builder
second_title: واجهة برمجة تطبيقات معالجة المستندات Aspose.Words
description: تعرف على كيفية إدراج مستند في نهاية مستند آخر باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /ar/net/join-and-append-documents/insert-document-with-builder/
---

 يشرح هذا البرنامج التعليمي كيفية استخدام Aspose.Words for .NET لإدراج مستند في مستند آخر باستخدام`DocumentBuilder` فصل. يوضح كود المصدر المقدم كيفية إدراج مستند في نهاية مستند آخر مع الحفاظ على تنسيق المصدر.

## الخطوة 1: قم بإعداد المشروع

تأكد من أن لديك المتطلبات الأساسية التالية:

- تثبيت Aspose.Words لمكتبة .NET. يمكنك تنزيله من[Aspose.Releases] https://releases.aspose.com/words/net/ أو استخدم مدير حزمة NuGet لتثبيته.
- مسار دليل المستند حيث توجد المستندات المصدر والوجهة.

## الخطوة 2: افتح مستندات المصدر والوجهة

 افتح مستندات المصدر والوجهة باستخدام ملف`Document` منشئ الطبقة. يستبدل`"YOUR DOCUMENT DIRECTORY"` مع المسار الفعلي إلى دليل المستند الخاص بك.

```csharp
// المسار إلى دليل المستند الخاص بك
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document srcDoc = new Document(dataDir + "Document source.docx");
Document dstDoc = new Document(dataDir + "Northwind traders.docx");
```

## الخطوة 3: تهيئة DocumentBuilder

 قم بإنشاء مثيل جديد لملف`DocumentBuilder` فئة وتمرير المستند الوجهة كمعامل.

```csharp
DocumentBuilder builder = new DocumentBuilder(dstDoc);
```

## الخطوة 4: ضع مُنشئ المستند

حرك ال`DocumentBuilder` إلى نهاية المستند باستخدام امتداد`MoveToDocumentEnd` طريقة. أدخل فاصل صفحات لفصل المحتوى الموجود عن المستند المدرج.

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

 أخيرًا ، احفظ مستند الوجهة المعدل باستخدام امتداد`Save` طريقة`Document` هدف.

```csharp
builder.Document.Save(dataDir + "JoinAndAppendDocuments.InsertDocumentWithBuilder.docx");
```

هذا يكمل تنفيذ إدراج مستند في مستند آخر باستخدام Aspose.Words for .NET.

### مثال على شفرة المصدر لـ Insert Document With Builder باستخدام Aspose.Words for .NET 

```csharp
	//المسار إلى دليل المستند الخاص بك
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Northwind traders.docx");
	DocumentBuilder builder = new DocumentBuilder(dstDoc);
	builder.MoveToDocumentEnd();
	builder.InsertBreak(BreakType.PageBreak);
	builder.InsertDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
	builder.Document.Save(dataDir + "JoinAndAppendDocuments.InsertDocumentWithBuilder.docx");
```