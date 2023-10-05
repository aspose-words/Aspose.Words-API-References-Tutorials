---
title: الانضمام إلى صفحة جديدة
linktitle: الانضمام إلى صفحة جديدة
second_title: Aspose.Words واجهة برمجة تطبيقات معالجة المستندات
description: تعرف على كيفية ضم مستندين في صفحة جديدة مع الحفاظ على التنسيق باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /ar/net/join-and-append-documents/join-new-page/
---

يشرح هذا البرنامج التعليمي كيفية ضم مستندين في صفحة جديدة باستخدام Aspose.Words for .NET. يوضح كود المصدر المقدم كيفية إلحاق مستند بنهاية مستند آخر أثناء بدء المستند الملحق على صفحة جديدة.

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

## الخطوة 3: إعداد بداية قسم الصفحة الجديدة

 لبدء المستند الملحق على صفحة جديدة، قم بتعيين`SectionStart` خاصية القسم الأول في الوثيقة المصدر ل`SectionStart.NewPage`.

```csharp
srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.NewPage;
```

## الخطوة 4: إلحاق المستند المصدر

 قم بإلحاق المستند المصدر بالمستند الوجهة باستخدام`AppendDocument` طريقة`Document` فصل. اضبط وضع تنسيق الاستيراد على`ImportFormatMode.KeepSourceFormatting` للحفاظ على الأنماط الأصلية من المستند المصدر.

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## الخطوة 5: احفظ المستند المعدل

 وأخيرًا، احفظ مستند الوجهة المعدل باستخدام الملف`Save` طريقة`Document` هدف.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.JoinNewPage.docx");
```

وبذلك يكتمل تنفيذ ضم وثيقتين في صفحة جديدة باستخدام Aspose.Words for .NET.

### مثال على التعليمات البرمجية المصدر للانضمام إلى صفحة جديدة باستخدام Aspose.Words لـ .NET 

```csharp
	// المسار إلى دليل المستندات الخاص بك
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Northwind traders.docx");
	//قم بتعيين المستند الملحق للبدء في صفحة جديدة.
	srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.NewPage;
	// قم بإلحاق المستند المصدر باستخدام الأنماط الأصلية الموجودة في المستند المصدر.
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.JoinNewPage.docx");
```