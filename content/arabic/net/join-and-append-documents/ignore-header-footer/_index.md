---
title: تجاهل رأس التذييل
linktitle: تجاهل رأس التذييل
second_title: Aspose.Words واجهة برمجة تطبيقات معالجة المستندات
description: تعرف على كيفية إلحاق مستند مع تجاهل محتوى الرأس والتذييل باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /ar/net/join-and-append-documents/ignore-header-footer/
---

يشرح هذا البرنامج التعليمي كيفية استخدام Aspose.Words for .NET لإلحاق مستند مع تجاهل محتوى الرأس والتذييل. يوضح كود المصدر المقدم كيفية إعداد خيارات تنسيق الاستيراد لاستبعاد الرأس والتذييل أثناء عملية الإلحاق.

## الخطوة 1: إعداد المشروع

تأكد من أن لديك المتطلبات الأساسية التالية:

-  تم تثبيت Aspose.Words لمكتبة .NET. يمكنك تنزيله من[Aspose.Releases]https://releases.aspose.com/words/net/ أو استخدم مدير الحزم NuGet لتثبيته.
- مسار دليل المستند حيث توجد المستندات المصدر والوجهة.

## الخطوة 2: افتح المستندات المصدر والوجهة

 افتح المستندات المصدر والوجهة باستخدام`Document` منشئ الطبقة. يستبدل`"YOUR DOCUMENT DIRECTORY"` بالمسار الفعلي إلى دليل المستندات الخاص بك.

```csharp
// المسار إلى دليل المستندات الخاص بك
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document srcDocument = new Document(dataDir + "Document source.docx");
Document dstDocument = new Document(dataDir + "Northwind traders.docx");
```

## الخطوة 3: إعداد خيارات تنسيق الاستيراد

 إنشاء مثيل لـ`ImportFormatOptions` فئة وتعيين`IgnoreHeaderFooter`الملكية ل`false`. وهذا يضمن تضمين محتوى الرأس والتذييل أثناء عملية الإلحاق.

```csharp
ImportFormatOptions importFormatOptions = new ImportFormatOptions { IgnoreHeaderFooter = false };
```

## الخطوة 4: إلحاق المستند المصدر بالمستند الوجهة

 استخدم ال`AppendDocument` طريقة المستند الوجهة لإلحاق المستند المصدر. يمر`ImportFormatMode.KeepSourceFormatting`كمعلمة ثانية وخيارات تنسيق الاستيراد كمعلمة ثالثة.

```csharp
dstDocument.AppendDocument(srcDocument, ImportFormatMode.KeepSourceFormatting, importFormatOptions);
```

## الخطوة 5: احفظ مستند الوجهة

وأخيرًا، احفظ مستند الوجهة المعدل باستخدام الملف`Save` طريقة`Document` هدف.

```csharp
dstDocument.Save(dataDir + "JoinAndAppendDocuments.IgnoreHeaderFooter.docx");
```

يؤدي هذا إلى إكمال تنفيذ إلحاق مستند مع تجاهل محتوى الرأس والتذييل باستخدام Aspose.Words for .NET.

### مثال على التعليمات البرمجية المصدر لتجاهل تذييل الرأس باستخدام Aspose.Words لـ .NET 

```csharp
	// المسار إلى دليل المستندات الخاص بك
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDocument = new Document(dataDir + "Document source.docx");
	Document dstDocument = new Document(dataDir + "Northwind traders.docx");
	ImportFormatOptions importFormatOptions = new ImportFormatOptions { IgnoreHeaderFooter = false };
	dstDocument.AppendDocument(srcDocument, ImportFormatMode.KeepSourceFormatting, importFormatOptions);
	dstDocument.Save(dataDir + "JoinAndAppendDocuments.IgnoreHeaderFooter.docx");
```