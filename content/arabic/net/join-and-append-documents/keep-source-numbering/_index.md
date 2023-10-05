---
title: احتفظ بترقيم المصدر
linktitle: احتفظ بترقيم المصدر
second_title: Aspose.Words واجهة برمجة تطبيقات معالجة المستندات
description: تعرف على كيفية إلحاق مستند مع الحفاظ على تنسيق ترقيم المصدر في Aspose.Words لـ .NET.
type: docs
weight: 10
url: /ar/net/join-and-append-documents/keep-source-numbering/
---

يشرح هذا البرنامج التعليمي كيفية إلحاق مستند مصدر بالمستند الوجهة مع الحفاظ على تنسيق الترقيم الأصلي للفقرات المرقمة باستخدام Aspose.Words for .NET.

## الخطوة 1: إعداد المشروع

تأكد من أن لديك المتطلبات الأساسية التالية:

-  تم تثبيت Aspose.Words لمكتبة .NET. يمكنك تنزيله من[Aspose.Releases]https://releases.aspose.com/words/net/ أو استخدم مدير الحزم NuGet لتثبيته.
- مسار دليل المستند حيث سيتم حفظ المستندات المصدر والوجهة.

## الخطوة 2: إنشاء الوجهة والمستندات المصدر

 إنشاء مثيلات`Document` للوجهة والوثائق المصدر.

```csharp
// المسار إلى دليل المستندات الخاص بك
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document srcDoc = new Document(dataDir + "Document source.docx");
Document dstDoc = new Document(dataDir + "Northwind traders.docx");
```

## الخطوة 3: احتفظ بترقيم المصدر عند الاستيراد

 للحفاظ على تنسيق الترقيم للفقرات المرقمة من المستند المصدر، قم بإنشاء مثيل لـ`ImportFormatOptions` وحدد`KeepSourceNumbering` ل`true` . إستخدم`NodeImporter` لاستيراد العقد من المستند المصدر إلى المستند الوجهة، مع تحديد`ImportFormatMode.KeepSourceFormatting` و ال`importFormatOptions`.

```csharp
ImportFormatOptions importFormatOptions = new ImportFormatOptions { KeepSourceNumbering = true };
NodeImporter importer = new NodeImporter(srcDoc, dstDoc, ImportFormatMode.KeepSourceFormatting, importFormatOptions);
```

## الخطوة 4: استيراد وإلحاق الفقرات

قم بالتكرار عبر الفقرات الموجودة في المستند المصدر وقم باستيراد كل فقرة إلى المستند الوجهة باستخدام الملف`importer`. قم بإلحاق العقد المستوردة بالنص الأساسي للمستند الوجهة.

```csharp
ParagraphCollection srcParas = srcDoc.FirstSection.Body.Paragraphs;
foreach (Paragraph srcPara in srcParas)
{
    Node importedNode = importer.ImportNode(srcPara, false);
    dstDoc.FirstSection.Body.AppendChild(importedNode);
}
```

## الخطوة 5: احفظ المستند المعدل

 احفظ المستند المعدل باستخدام`Save` طريقة`Document` هدف.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.KeepSourceNumbering.docx");
```

يؤدي هذا إلى إكمال تنفيذ إلحاق مستند مصدر بالمستند الوجهة مع الاحتفاظ بتنسيق الترقيم الأصلي باستخدام Aspose.Words for .NET.

### مثال على التعليمات البرمجية المصدر للاحتفاظ بترقيم المصدر باستخدام Aspose.Words لـ .NET 

```csharp
	// المسار إلى دليل المستندات الخاص بك
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Northwind traders.docx");
	// احتفظ بتنسيق قائمة المصدر عند استيراد فقرات مرقمة.
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