---
title: حافظ على ترقيم المصدر
linktitle: حافظ على ترقيم المصدر
second_title: واجهة برمجة تطبيقات معالجة المستندات Aspose.Words
description: تعرف على كيفية إلحاق مستند مع الاحتفاظ بتنسيق ترقيم المصدر في Aspose.Words for .NET.
type: docs
weight: 10
url: /ar/net/join-and-append-documents/keep-source-numbering/
---

يشرح هذا البرنامج التعليمي كيفية إلحاق مستند مصدر بمستند وجهة مع الحفاظ على تنسيق الترقيم الأصلي للفقرات المرقمة باستخدام Aspose.Words for .NET.

## الخطوة 1: قم بإعداد المشروع

تأكد من توفر لديك المتطلبات الأساسية التالية:

- تثبيت Aspose.Words لمكتبة .NET. يمكنك تنزيله من[Aspose.Releases] https://releases.aspose.com/words/net/ أو استخدم مدير حزمة NuGet لتثبيته.
- مسار دليل المستند حيث سيتم حفظ مستندات المصدر والوجهة.

## الخطوة 2: قم بإنشاء الوجهة والمستندات المصدر

 إنشاء مثيلات من`Document` للوجهة والمستندات المصدر.

```csharp
// المسار إلى دليل المستند الخاص بك
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document srcDoc = new Document(dataDir + "Document source.docx");
Document dstDoc = new Document(dataDir + "Northwind traders.docx");
```

## الخطوة 3: احتفظ بترقيم المصدر عند الاستيراد

 للاحتفاظ بتنسيق ترقيم الفقرات المرقمة من المستند المصدر ، قم بإنشاء مثيل لـ`ImportFormatOptions` وحدد`KeepSourceNumbering` ل`true` . إستخدم`NodeImporter` لاستيراد العقد من المستند المصدر إلى المستند الوجهة ، مع تحديد`ImportFormatMode.KeepSourceFormatting` و ال`importFormatOptions`.

```csharp
ImportFormatOptions importFormatOptions = new ImportFormatOptions { KeepSourceNumbering = true };
NodeImporter importer = new NodeImporter(srcDoc, dstDoc, ImportFormatMode.KeepSourceFormatting, importFormatOptions);
```

## الخطوة 4: استيراد وإلحاق الفقرات

 كرر خلال الفقرات في المستند المصدر واستورد كل فقرة في المستند الوجهة باستخدام ملف`importer`. قم بإلحاق العقد التي تم استيرادها بجسم المستند الوجهة.

```csharp
ParagraphCollection srcParas = srcDoc.FirstSection.Body.Paragraphs;
foreach (Paragraph srcPara in srcParas)
{
    Node importedNode = importer.ImportNode(srcPara, false);
    dstDoc.FirstSection.Body.AppendChild(importedNode);
}
```

## الخطوة 5: احفظ المستند المعدل

 احفظ المستند المعدل باستخدام ملف`Save` طريقة`Document` هدف.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.KeepSourceNumbering.docx");
```

هذا يكمل تنفيذ إلحاق مستند مصدر بمستند الوجهة مع الاحتفاظ بتنسيق الترقيم الأصلي باستخدام Aspose.Words for .NET.

### مثال على شفرة المصدر لـ Keep Source Numbering باستخدام Aspose.Words for .NET 

```csharp
	//المسار إلى دليل المستند الخاص بك
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Northwind traders.docx");
	// احتفظ بتنسيق قائمة المصادر عند استيراد فقرات مرقمة.
	ImportFormatOptions importFormatOptions = new ImportFormatOptions { KeepSourceNumbering = true };
	NodeImporter importer = new NodeImporter(srcDoc, dstDoc, ImportFormatMode.KeepSourceFormatting,
		importFormatOptions);
	ParagraphCollection srcParas = srcDoc.FirstSection.Body.Paragraphs;
	foreach (Paragraph srcPara in srcParas)
	{
		Node importedNode = importer.ImportNode(srcPara, false);
		dstDoc.FirstSection.Body.AppendChild(importedNode);
	}
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.KeepSourceNumbering.docx");
```