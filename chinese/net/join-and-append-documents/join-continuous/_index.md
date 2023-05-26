---
title: الانضمام المستمر
linktitle: الانضمام المستمر
second_title: Aspose.Words لمراجع .NET API
description: تعرف على كيفية ربط وثيقتين بشكل مستمر مع الحفاظ على التنسيق باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /zh/net/join-and-append-documents/join-continuous/
---

يشرح هذا البرنامج التعليمي كيفية الانضمام إلى وثيقتين بشكل مستمر باستخدام Aspose.Words for .NET. يوضح كود المصدر المقدم كيفية إلحاق مستند بنهاية مستند آخر مع الحفاظ على التنسيق الأصلي.

## الخطوة 1: قم بإعداد المشروع

تأكد من أن لديك المتطلبات الأساسية التالية:

- تثبيت Aspose.Words لمكتبة .NET. يمكنك تنزيله من موقع Aspose الرسمي أو استخدام مدير حزمة NuGet لتثبيته.
- مسار دليل المستند حيث توجد المستندات المصدر والوجهة.

## الخطوة 2: افتح مستندات المصدر والوجهة

 افتح مستندات المصدر والوجهة باستخدام ملف`Document` منشئ الطبقة. يستبدل`"YOUR DOCUMENT DIRECTORY"` مع المسار الفعلي إلى دليل المستند الخاص بك.

```csharp
// المسار إلى دليل المستند الخاص بك
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document srcDoc = new Document(dataDir + "Document source.docx");
Document dstDoc = new Document(dataDir + "Northwind traders.docx");
```

## الخطوة 3: إعداد بداية القسم المستمر

 لجعل المستند المصدر يظهر مباشرة بعد محتوى المستند الوجهة ، قم بتعيين`SectionStart` من القسم الأول في المستند المصدر إلى`SectionStart.Continuous`.

```csharp
srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.Continuous;
```

## الخطوة 4: قم بإلحاق المستند المصدر

 قم بإلحاق المستند المصدر بالمستند الوجهة باستخدام ملف`AppendDocument` طريقة`Document` فصل. اضبط وضع تنسيق الاستيراد على`ImportFormatMode.KeepSourceFormatting`للاحتفاظ بالأنماط الأصلية من المستند المصدر.

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## الخطوة 5: احفظ المستند المعدل

 أخيرًا ، احفظ مستند الوجهة المعدل باستخدام امتداد`Save` طريقة`Document` هدف.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.JoinContinuous.docx");
```

هذا يكمل تنفيذ الانضمام إلى وثيقتين بشكل مستمر باستخدام Aspose.Words لـ .NET.

### مثال على شفرة المصدر لـ Join Continuous using Aspose.Words for .NET 

```csharp
	// المسار إلى دليل المستند الخاص بك
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Northwind traders.docx");
	// اجعل المستند يظهر مباشرة بعد محتوى المستندات الوجهة.
	srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.Continuous;
	// قم بإلحاق المستند المصدر باستخدام الأنماط الأصلية الموجودة في المستند المصدر.
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.JoinContinuous.docx");
```