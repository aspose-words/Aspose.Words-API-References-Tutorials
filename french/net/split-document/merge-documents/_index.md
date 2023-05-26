---
title: دمج المستندات
linktitle: دمج المستندات
second_title: Aspose.Words لمراجع .NET API
description: دليل خطوة بخطوة لشرح كود مصدر C # لميزة دمج المستندات في Aspose.Words for .NET
type: docs
weight: 10
url: /fr/net/split-document/merge-documents/
---

في هذا البرنامج التعليمي ، سنرشدك إلى كيفية دمج مستندات Word متعددة باستخدام ميزة دمج المستندات في Aspose.Words for .NET. اتبع الخطوات أدناه لفهم التعليمات البرمجية المصدر والحصول على مستند مدمج يحتوي على كافة المستندات المصدر.

## الخطوة 1: ابحث عن المستندات المراد دمجها

قبل دمج المستندات ، نحتاج إلى تحديد موقع المستندات المصدر المراد دمجها. إليك الطريقة:

```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
// ابحث عن المستندات المراد دمجها.
FileSystemInfo[] documentPaths = new DirectoryInfo(dataDir)
.GetFileSystemInfos("SplitDocument.PageParPage_*.docx").OrderBy(f => f.CreationTime).ToArray();
string sourceDocumentPath =
Directory.GetFiles(dataDir, "SplitDocument.PageParPage_1.docx", SearchOption.TopDirectoryOnly)[0];
```

## الخطوة 2: دمج المستندات

سنقوم الآن بدمج المستندات واحدة تلو الأخرى لإنشاء مستند مدمج نهائي. إليك الطريقة:

```csharp
// افتح الجزء الأول من المستند الناتج.
Document sourceDoc = new Document(sourceDocumentPath);

// قم بإنشاء مستند ناتج جديد.
Document mergedDoc = new Document();
DocumentBuilder mergedDocBuilder = new DocumentBuilder(mergedDoc);

// دمج المستندات واحدة تلو الأخرى.
foreach(FileSystemInfo documentPath in documentPaths)
{
if (documentPath.FullName == sourceDocumentPath)
keep on going;

mergedDocBuilder.MoveToDocumentEnd();
mergedDocBuilder.InsertDocument(sourceDoc, ImportFormatMode.KeepSourceFormatting);
sourceDoc = new Document(documentPath.FullName);
}

mergedDoc.Save(dataDir + "SplitDocument.MergeDocuments.docx");
```

### مثال على شفرة المصدر لدمج المستندات باستخدام Aspose.Words for .NET

فيما يلي رمز المصدر الكامل لميزة دمج المستندات في Aspose.Words for .NET:

```csharp

	// المسار إلى دليل المستندات.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// البحث عن المستندات باستخدام الدمج.
	FileSystemInfo[] documentPaths = new DirectoryInfo(dataDir)
		.GetFileSystemInfos("SplitDocument.PageByPage_*.docx").OrderBy(f => f.CreationTime).ToArray();
	string sourceDocumentPath =
		Directory.GetFiles(dataDir, "SplitDocument.PageByPage_1.docx", SearchOption.TopDirectoryOnly)[0];

	// افتح الجزء الأول من المستند الناتج.
	Document sourceDoc = new Document(sourceDocumentPath);

	// قم بإنشاء مستند ناتج جديد.
	Document mergedDoc = new Document();
	DocumentBuilder mergedDocBuilder = new DocumentBuilder(mergedDoc);

	// دمج أجزاء المستند واحدًا تلو الآخر.
	foreach (FileSystemInfo documentPath in documentPaths)
	{
		if (documentPath.FullName == sourceDocumentPath)
			continue;

		mergedDocBuilder.MoveToDocumentEnd();
		mergedDocBuilder.InsertDocument(sourceDoc, ImportFormatMode.KeepSourceFormatting);
		sourceDoc = new Document(documentPath.FullName);
	}

	mergedDoc.Save(dataDir + "SplitDocument.MergeDocuments.docx");

```
