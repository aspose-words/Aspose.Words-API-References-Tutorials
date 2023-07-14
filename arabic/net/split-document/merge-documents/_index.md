---
title: دمج مستندات Word
linktitle: دمج المستندات
second_title: واجهة برمجة تطبيقات معالجة المستندات Aspose.Words
description: تعرف على كيفية دمج مستندات Word متعددة باستخدام Aspose.Words for .NET. تعمل واجهة برمجة التطبيقات القوية هذه على تبسيط عملية دمج المستندات ، مما يجعلها فعالة ومباشرة.
type: docs
weight: 10
url: /ar/net/split-document/merge-documents/
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

## خاتمة

تهانينا! لقد تعلمت كيفية دمج مستندات Word متعددة باستخدام ميزة دمج المستندات في Aspose.Words for .NET. باتباع التعليمات البرمجية المصدر المتوفرة ، يمكنك دمج مستندات منفصلة في مستند واحد مدمج مع الحفاظ على تنسيق كل مستند مصدر.

يمكن أن يكون دمج المستندات مفيدًا عندما تريد دمج المعلومات من مصادر متعددة أو إنشاء مستند موحد من أجزاء فردية. يوفر Aspose.Words for .NET واجهة برمجة تطبيقات قوية تبسط عملية دمج المستندات ، مما يجعلها فعالة ومباشرة.

لا تتردد في استكشاف الميزات الأخرى التي تقدمها Aspose.Words for .NET لتحسين إمكانيات معالجة المستندات وتسهيل سير عملك.

### أسئلة وأجوبة

#### كيف يمكنني دمج المستندات بتنسيق مختلف؟

 عند دمج المستندات ، يوفر Aspose.Words for .NET خيارًا للاحتفاظ بتنسيق كل مستند مصدر. باستخدام ملف`ImportFormatMode.KeepSourceFormatting` الخيار ، سيحتفظ المستند المدمج بتنسيق المستندات الأصلية. إذا كنت ترغب في تطبيق تنسيق متسق في جميع أنحاء المستند المدمج ، يمكنك تعديل التنسيق باستخدام Aspose.Words API بعد دمج المستندات.

#### هل يمكنني دمج المستندات بتنسيقات مختلفة؟

نعم ، يدعم Aspose.Words for .NET دمج المستندات بتنسيقات مختلفة ، بما في ذلك DOCX و DOC و RTF والمزيد. يمكنك تحميل مستندات بتنسيقات مختلفة في Aspose.Words API ودمجها في مستند واحد بغض النظر عن تنسيقاتها الأصلية.

#### هل يمكنني دمج المستندات ذات الهياكل المعقدة ، مثل الجداول والصور؟

قطعاً! Aspose.Words for .NET قادر على دمج المستندات مع الهياكل المعقدة ، بما في ذلك الجداول والصور والرؤوس والتذييلات والمزيد. تتعامل واجهة برمجة التطبيقات مع عملية الدمج مع الحفاظ على تكامل المحتوى وتخطيطه في كل مستند.

#### هل من الممكن دمج المستندات ذات الاتجاهات أو الأحجام المختلفة للصفحة؟

نعم ، يتعامل Aspose.Words for .NET مع المستندات ذات التوجهات وأحجام الصفحات المختلفة أثناء عملية الدمج. سوف يلائم المستند المدمج الناتج اتجاهات الصفحة وأحجام المستندات المصدر المختلفة.