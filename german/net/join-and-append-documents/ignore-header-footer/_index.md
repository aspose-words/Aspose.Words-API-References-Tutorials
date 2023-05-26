---
title: تجاهل رأس تذييل الصفحة
linktitle: تجاهل رأس تذييل الصفحة
second_title: Aspose.Words لمراجع .NET API
description: تعرف على كيفية إلحاق مستند مع تجاهل محتوى الرأس والتذييل باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /de/net/join-and-append-documents/ignore-header-footer/
---

يشرح هذا البرنامج التعليمي كيفية استخدام Aspose.Words for .NET لإلحاق مستند مع تجاهل محتوى الرأس والتذييل. يوضح كود المصدر المقدم كيفية إعداد خيارات تنسيق الاستيراد لاستبعاد الرأس والتذييل أثناء عملية الإلحاق.

## الخطوة 1: قم بإعداد المشروع

تأكد من أن لديك المتطلبات الأساسية التالية:

- تثبيت Aspose.Words لمكتبة .NET. يمكنك تنزيله من موقع Aspose الرسمي أو استخدام مدير حزمة NuGet لتثبيته.
- مسار دليل المستند حيث توجد المستندات المصدر والوجهة.

## الخطوة 2: افتح مستندات المصدر والوجهة

 افتح مستندات المصدر والوجهة باستخدام ملف`Document` منشئ الطبقة. يستبدل`"YOUR DOCUMENT DIRECTORY"` مع المسار الفعلي إلى دليل المستند الخاص بك.

```csharp
// المسار إلى دليل المستند الخاص بك
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document srcDocument = new Document(dataDir + "Document source.docx");
Document dstDocument = new Document(dataDir + "Northwind traders.docx");
```

## الخطوة 3: إعداد خيارات تنسيق الاستيراد

 قم بإنشاء مثيل لـ`ImportFormatOptions` فئة وضبط`IgnoreHeaderFooter` ملكية ل`false`. يضمن ذلك تضمين محتوى الرأس والتذييل أثناء عملية الإلحاق.

```csharp
ImportFormatOptions importFormatOptions = new ImportFormatOptions { IgnoreHeaderFooter = false };
```

## الخطوة 4: قم بإلحاق المستند المصدر بالمستند الوجهة

 استخدم ال`AppendDocument` طريقة المستند الوجهة لإلحاق المستند المصدر. يمر`ImportFormatMode.KeepSourceFormatting` كمعامل ثاني وخيارات تنسيق الاستيراد كمعامل ثالث.

```csharp
dstDocument.AppendDocument(srcDocument, ImportFormatMode.KeepSourceFormatting, importFormatOptions);
```

## الخطوة 5: احفظ المستند الوجهة

 أخيرًا ، احفظ مستند الوجهة المعدل باستخدام امتداد`Save` طريقة`Document` هدف.

```csharp
dstDocument.Save(dataDir + "JoinAndAppendDocuments.IgnoreHeaderFooter.docx");
```

هذا يكمل تنفيذ إلحاق مستند مع تجاهل محتوى الرأس والتذييل باستخدام Aspose.Words for .NET.

### مثال على شفرة المصدر لـ Ignore Header Footer باستخدام Aspose.Words for .NET 

```csharp
	// المسار إلى دليل المستند الخاص بك
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDocument = new Document(dataDir + "Document source.docx");
	Document dstDocument = new Document(dataDir + "Northwind traders.docx");
	ImportFormatOptions importFormatOptions = new ImportFormatOptions { IgnoreHeaderFooter = false };
	dstDocument.AppendDocument(srcDocument, ImportFormatMode.KeepSourceFormatting, importFormatOptions);
	dstDocument.Save(dataDir + "JoinAndAppendDocuments.IgnoreHeaderFooter.docx");
```