---
title: تجاهل مربعات النص
linktitle: تجاهل مربعات النص
second_title: Aspose.Words واجهة برمجة تطبيقات معالجة المستندات
description: تعرف على كيفية إلحاق مستند مع تجاهل تنسيق مربع النص باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /ar/net/join-and-append-documents/ignore-text-boxes/
---

يشرح هذا البرنامج التعليمي كيفية استخدام Aspose.Words for .NET لإلحاق مستند مع الحفاظ على تنسيق مربعات النص. يوضح كود المصدر المقدم كيفية إعداد خيارات تنسيق الاستيراد لتضمين مربعات النص أثناء عملية الإلحاق.

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

## الخطوة 3: إعداد خيارات تنسيق الاستيراد

 إنشاء مثيل لـ`ImportFormatOptions` فئة وتعيين`IgnoreTextBoxes` الملكية ل`false`. وهذا يضمن تضمين مربعات النص أثناء عملية الإلحاق مع الحفاظ على تنسيقها.

```csharp
ImportFormatOptions importFormatOptions = new ImportFormatOptions { IgnoreTextBoxes = false };
```

## الخطوة 4: إلحاق محتوى مربع النص

 إنشاء`NodeImporter` الكائن واستخدامه لاستيراد عقد مربع النص من المستند المصدر إلى المستند الوجهة. قم بالتكرار خلال كل فقرة في المستند المصدر وقم باستيرادها إلى المستند الوجهة.

```csharp
NodeImporter importer = new NodeImporter(srcDoc, dstDoc, ImportFormatMode.KeepSourceFormatting, importFormatOptions);
ParagraphCollection srcParas = srcDoc.FirstSection.Body.Paragraphs;
foreach (Paragraph srcPara in srcParas)
{
    Node importedNode = importer.ImportNode(srcPara, true);
    dstDoc.FirstSection.Body.AppendChild(importedNode);
}
```

## الخطوة 5: احفظ مستند الوجهة

 وأخيرًا، احفظ مستند الوجهة المعدل باستخدام الملف`Save` طريقة`Document` هدف.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.IgnoreTextBoxes.docx");
```

يكمل هذا تنفيذ إلحاق مستند مع الحفاظ على تنسيق مربع النص باستخدام Aspose.Words لـ .NET.

### مثال على التعليمات البرمجية المصدر لتجاهل مربعات النص باستخدام Aspose.Words لـ .NET 

```csharp
	// المسار إلى دليل المستندات الخاص بك
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Northwind traders.docx");
	// احتفظ بتنسيق مربعات النص المصدر عند الاستيراد.
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