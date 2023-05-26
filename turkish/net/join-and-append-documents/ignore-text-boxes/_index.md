---
title: تجاهل مربعات النص
linktitle: تجاهل مربعات النص
second_title: Aspose.Words لمراجع .NET API
description: تعرف على كيفية إلحاق مستند أثناء تجاهل تنسيق مربع النص باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /tr/net/join-and-append-documents/ignore-text-boxes/
---

يشرح هذا البرنامج التعليمي كيفية استخدام Aspose.Words for .NET لإلحاق مستند مع الحفاظ على تنسيق مربعات النص. يوضح كود المصدر المقدم كيفية إعداد خيارات تنسيق الاستيراد لتضمين مربعات النص أثناء عملية الإلحاق.

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

## الخطوة 3: إعداد خيارات تنسيق الاستيراد

 قم بإنشاء مثيل لـ`ImportFormatOptions` فئة وضبط`IgnoreTextBoxes` ملكية ل`false`. يضمن ذلك تضمين مربعات النص أثناء عملية الإلحاق مع الحفاظ على تنسيقها.

```csharp
ImportFormatOptions importFormatOptions = new ImportFormatOptions { IgnoreTextBoxes = false };
```

## الخطوة 4: إلحاق محتوى مربع نص

 إنشاء`NodeImporter` كائن واستخدمه لاستيراد عقد مربع نص من المستند المصدر إلى المستند الوجهة. كرر خلال كل فقرة في المستند المصدر واستوردها إلى المستند الوجهة.

```csharp
NodeImporter importer = new NodeImporter(srcDoc, dstDoc, ImportFormatMode.KeepSourceFormatting, importFormatOptions);
ParagraphCollection srcParas = srcDoc.FirstSection.Body.Paragraphs;
foreach (Paragraph srcPara in srcParas)
{
    Node importedNode = importer.ImportNode(srcPara, true);
    dstDoc.FirstSection.Body.AppendChild(importedNode);
}
```

## الخطوة 5: احفظ المستند الوجهة

 أخيرًا ، احفظ مستند الوجهة المعدل باستخدام امتداد`Save` طريقة`Document` هدف.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.IgnoreTextBoxes.docx");
```

هذا يكمل تنفيذ إلحاق مستند مع الحفاظ على تنسيق مربع النص باستخدام Aspose.Words for .NET.

### مثال على شفرة المصدر لـ Ignore Text Boxes باستخدام Aspose.Words for .NET 

```csharp
	// المسار إلى دليل المستند الخاص بك
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Northwind traders.docx");
	//احتفظ بتنسيق مربعات النص المصدر عند الاستيراد.
	ImportFormatOptions importFormatOptions = new ImportFormatOptions { IgnoreTextBoxes = false };
	NodeImporter importer = new NodeImporter(srcDoc, dstDoc, ImportFormatMode.KeepSourceFormatting,
		importFormatOptions);
	ParagraphCollection srcParas = srcDoc.FirstSection.Body.Paragraphs;
	foreach (Paragraph srcPara in srcParas)
	{
		Node importedNode = importer.ImportNode(srcPara, true);
		dstDoc.FirstSection.Body.AppendChild(importedNode);
	}
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.IgnoreTextBoxes.docx");
```