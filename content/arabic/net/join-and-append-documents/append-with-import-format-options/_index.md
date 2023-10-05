---
title: إلحاق مع خيارات تنسيق الاستيراد
linktitle: إلحاق مع خيارات تنسيق الاستيراد
second_title: Aspose.Words واجهة برمجة تطبيقات معالجة المستندات
description: تعرف على كيفية إلحاق مستند بخيارات تنسيق الاستيراد باستخدام Aspose.Words لـ .NET.
type: docs
weight: 10
url: /ar/net/join-and-append-documents/append-with-import-format-options/
---

يشرح هذا البرنامج التعليمي كيفية استخدام Aspose.Words for .NET لإلحاق محتويات مستند بآخر مع خيارات تنسيق الاستيراد. يوضح كود المصدر المقدم كيفية فتح المستندات المصدر والوجهة، وتحديد خيارات تنسيق الاستيراد، وإلحاق المستند المصدر بالمستند الوجهة.

## الخطوة 1: إعداد المشروع

تأكد من أن لديك المتطلبات الأساسية التالية:

-  تم تثبيت Aspose.Words لمكتبة .NET. يمكنك تنزيله من[Aspose.Releases]https://releases.aspose.com/words/net/ أو استخدم مدير الحزم NuGet لتثبيته.
- مسار دليل المستند حيث توجد المستندات المصدر والوجهة.

## الخطوة 2: افتح المستندات المصدر والوجهة

 افتح المستندات المصدر والوجهة باستخدام`Document` منشئ الطبقة. يستبدل`"YOUR DOCUMENT DIRECTORY"` بالمسار الفعلي إلى دليل المستندات الخاص بك.

```csharp
// المسار إلى دليل المستندات الخاص بك
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document srcDoc = new Document(dataDir + "Document source with list.docx");
Document dstDoc = new Document(dataDir + "Document destination with list.docx");
```

## الخطوة 3: تحديد خيارات تنسيق الاستيراد

 إنشاء مثيل لـ`ImportFormatOptions` فئة لتحديد خيارات تنسيق الاستيراد. في هذا المثال نستخدم`KeepSourceNumbering` الخاصية للتأكد من استخدام الترقيم من المستند المصدر في حالة وجود تعارضات مع المستند الوجهة.

```csharp
ImportFormatOptions options = new ImportFormatOptions { KeepSourceNumbering = true };
```

## الخطوة 4: إلحاق المستند المصدر بالمستند الوجهة

 استخدم ال`AppendDocument` طريقة المستند الوجهة لإلحاق المستند المصدر. يمر`ImportFormatMode.UseDestinationStyles` كمعلمة ثانية لاستخدام أنماط وتنسيقات المستند الوجهة.

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.UseDestinationStyles, options);
```

## الخطوة 5: احفظ مستند الوجهة

 وأخيرًا، احفظ مستند الوجهة المعدل باستخدام الملف`Save` طريقة`Document` هدف.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.AppendWithImportFormatOptions.docx");
```

يكمل هذا تنفيذ إلحاق مستند بخيارات تنسيق الاستيراد باستخدام Aspose.Words لـ .NET.

### مثال على التعليمات البرمجية المصدر لـ Append With Import Format Options باستخدام Aspose.Words لـ .NET 

```csharp
	// المسار إلى دليل المستندات الخاص بك
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source with list.docx");
	Document dstDoc = new Document(dataDir + "Document destination with list.docx");
	// حدد أنه في حالة تعارض الترقيم في مستندات المصدر والوجهة،
	//ثم سيتم استخدام الترقيم من المستند المصدر.
	ImportFormatOptions options = new ImportFormatOptions { KeepSourceNumbering = true };
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.UseDestinationStyles, options);

```