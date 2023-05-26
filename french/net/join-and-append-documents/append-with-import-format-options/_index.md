---
title: إلحاق بخيارات تنسيق الاستيراد
linktitle: إلحاق بخيارات تنسيق الاستيراد
second_title: Aspose.Words لمراجع .NET API
description: تعرف على كيفية إلحاق مستند بخيارات تنسيق الاستيراد باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /fr/net/join-and-append-documents/append-with-import-format-options/
---

يشرح هذا البرنامج التعليمي كيفية استخدام Aspose.Words for .NET لإلحاق محتويات مستند بآخر بخيارات تنسيق الاستيراد. يوضح كود المصدر المقدم كيفية فتح المستندات المصدر والوجهة ، وتحديد خيارات تنسيق الاستيراد ، وإلحاق المستند المصدر بالمستند الوجهة.

## الخطوة 1: قم بإعداد المشروع

تأكد من أن لديك المتطلبات الأساسية التالية:

- تثبيت Aspose.Words لمكتبة .NET. يمكنك تنزيله من موقع Aspose الرسمي أو استخدام مدير حزمة NuGet لتثبيته.
- مسار دليل المستند حيث توجد المستندات المصدر والوجهة.

## الخطوة 2: افتح مستندات المصدر والوجهة

 افتح مستندات المصدر والوجهة باستخدام ملف`Document` منشئ الطبقة. يستبدل`"YOUR DOCUMENT DIRECTORY"` مع المسار الفعلي إلى دليل المستند الخاص بك.

```csharp
// المسار إلى دليل المستند الخاص بك
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document srcDoc = new Document(dataDir + "Document source with list.docx");
Document dstDoc = new Document(dataDir + "Document destination with list.docx");
```

## الخطوة 3: حدد خيارات تنسيق الاستيراد

 قم بإنشاء مثيل لـ`ImportFormatOptions` فئة لتحديد خيارات تنسيق الاستيراد. في هذا المثال ، نستخدم الامتداد`KeepSourceNumbering` للتأكد من استخدام الترقيم من المستند المصدر في حالة وجود تعارضات مع المستند الوجهة.

```csharp
ImportFormatOptions options = new ImportFormatOptions { KeepSourceNumbering = true };
```

## الخطوة 4: قم بإلحاق المستند المصدر بالمستند الوجهة

 استخدم ال`AppendDocument` طريقة المستند الوجهة لإلحاق المستند المصدر. يمر`ImportFormatMode.UseDestinationStyles` كمعامل ثاني لاستخدام أنماط وتنسيق المستند الوجهة.

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.UseDestinationStyles, options);
```

## الخطوة 5: احفظ المستند الوجهة

 أخيرًا ، احفظ مستند الوجهة المعدل باستخدام امتداد`Save` طريقة`Document` هدف.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.AppendWithImportFormatOptions.docx");
```

هذا يكمل تنفيذ إلحاق مستند بخيارات تنسيق الاستيراد باستخدام Aspose.Words for .NET.

### مثال على الكود المصدري للإلحاق بخيارات تنسيق الاستيراد باستخدام Aspose.Words for .NET 

```csharp
	// المسار إلى دليل المستند الخاص بك
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source with list.docx");
	Document dstDoc = new Document(dataDir + "Document destination with list.docx");
	//حدد أنه في حالة تعارض الترقيم في المستندات المصدر والوجهة ،
	// ثم سيتم استخدام الترقيم من المستند المصدر.
	ImportFormatOptions options = new ImportFormatOptions { KeepSourceNumbering = true };
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.UseDestinationStyles, options);

```