---
title: الانضمام إلى صفحة جديدة
linktitle: الانضمام إلى صفحة جديدة
second_title: Aspose.Words لمراجع .NET API
description: تعرف على كيفية ضم وثيقتين في صفحة جديدة مع الحفاظ على التنسيق باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /de/net/join-and-append-documents/join-new-page/
---

يشرح هذا البرنامج التعليمي كيفية ضم وثيقتين على صفحة جديدة باستخدام Aspose.Words for .NET. يوضح كود المصدر المقدم كيفية إلحاق مستند بنهاية مستند آخر أثناء بدء المستند الملحق في صفحة جديدة.

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

## الخطوة 3: بدء إعداد قسم صفحة جديدة

 لبدء المستند المُلحق على صفحة جديدة ، قم بتعيين`SectionStart` من القسم الأول في المستند المصدر إلى`SectionStart.NewPage`.

```csharp
srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.NewPage;
```

## الخطوة 4: قم بإلحاق المستند المصدر

 قم بإلحاق المستند المصدر بالمستند الوجهة باستخدام ملف`AppendDocument` طريقة`Document` فصل. اضبط وضع تنسيق الاستيراد على`ImportFormatMode.KeepSourceFormatting`للاحتفاظ بالأنماط الأصلية من المستند المصدر.

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## الخطوة 5: احفظ المستند المعدل

 أخيرًا ، احفظ مستند الوجهة المعدل باستخدام امتداد`Save` طريقة`Document` هدف.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.JoinNewPage.docx");
```

هذا يكمل تنفيذ ضم وثيقتين على صفحة جديدة باستخدام Aspose.Words for .NET.

### مثال على شفرة المصدر لـ Join New Page باستخدام Aspose.Words for .NET 

```csharp
	// المسار إلى دليل المستند الخاص بك
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Northwind traders.docx");
	// قم بتعيين المستند الملحق للبدء في صفحة جديدة.
	srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.NewPage;
	// قم بإلحاق المستند المصدر باستخدام الأنماط الأصلية الموجودة في المستند المصدر.
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.JoinNewPage.docx");
```