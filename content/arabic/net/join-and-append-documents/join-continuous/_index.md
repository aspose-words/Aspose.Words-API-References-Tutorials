---
title: الانضمام المستمر
linktitle: الانضمام المستمر
second_title: Aspose.Words واجهة برمجة تطبيقات معالجة المستندات
description: تعرف على كيفية ضم مستندين بشكل مستمر مع الحفاظ على التنسيق باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /ar/net/join-and-append-documents/join-continuous/
---

يشرح هذا البرنامج التعليمي كيفية ضم مستندين بشكل مستمر باستخدام Aspose.Words لـ .NET. يوضح كود المصدر المقدم كيفية إلحاق مستند بنهاية مستند آخر مع الحفاظ على التنسيق الأصلي.

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

## الخطوة 3: إعداد بداية القسم المستمر

 لجعل المستند المصدر يظهر مباشرة بعد محتوى المستند الوجهة، قم بتعيين الإعداد`SectionStart` خاصية القسم الأول في الوثيقة المصدر ل`SectionStart.Continuous`.

```csharp
srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.Continuous;
```

## الخطوة 4: إلحاق المستند المصدر

قم بإلحاق المستند المصدر بالمستند الوجهة باستخدام`AppendDocument` طريقة`Document` فصل. اضبط وضع تنسيق الاستيراد على`ImportFormatMode.KeepSourceFormatting` للحفاظ على الأنماط الأصلية من المستند المصدر.

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## الخطوة 5: احفظ المستند المعدل

 وأخيرًا، احفظ مستند الوجهة المعدل باستخدام الملف`Save` طريقة`Document` هدف.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.JoinContinuous.docx");
```

وبذلك يكتمل تنفيذ ربط وثيقتين بشكل مستمر باستخدام Aspose.Words for .NET.

### مثال على التعليمات البرمجية المصدر للانضمام المستمر باستخدام Aspose.Words لـ .NET 

```csharp
	// المسار إلى دليل المستندات الخاص بك
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Northwind traders.docx");
	// اجعل المستند يظهر مباشرة بعد محتوى المستندات الوجهة.
	srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.Continuous;
	// قم بإلحاق المستند المصدر باستخدام الأنماط الأصلية الموجودة في المستند المصدر.
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.JoinContinuous.docx");
```