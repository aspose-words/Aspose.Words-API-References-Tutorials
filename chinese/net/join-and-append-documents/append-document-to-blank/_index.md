---
title: إلحاق مستند فارغ
linktitle: إلحاق مستند فارغ
second_title: Aspose.Words لمراجع .NET API
description: تعرف على كيفية إلحاق مستند إلى مستند وجهة فارغ في Aspose.Words for .NET.
type: docs
weight: 10
url: /zh/net/join-and-append-documents/append-document-to-blank/
---

يشرح هذا البرنامج التعليمي كيفية استخدام Aspose.Words for .NET لإلحاق محتويات مستند واحد بمستند وجهة فارغ. يوضح كود المصدر المقدم كيفية إنشاء مستند جديد وإزالة محتواه ثم إلحاق المستند المصدر به.

## الخطوة 1: قم بإعداد المشروع

تأكد من أن لديك المتطلبات الأساسية التالية:

- تثبيت Aspose.Words لمكتبة .NET. يمكنك تنزيله من موقع Aspose الرسمي أو استخدام مدير حزمة NuGet لتثبيته.
- مسار دليل المستند حيث توجد المستندات المصدر والوجهة.

## الخطوة 2: قم بإنشاء مستند وجهة جديد

 إنشاء ملف`Document` كائن للمستند الوجهة.

```csharp
// المسار إلى دليل المستند الخاص بك
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document srcDoc = new Document(dataDir + "Document source.docx");
Document dstDoc = new Document();
```

## الخطوة 3: إزالة المحتوى الموجود من المستند الوجهة

لضمان وجود مستند وجهة نظيف ، قم بإزالة كل المحتوى الموجود من المستند باستخدام امتداد`RemoveAllChildren` طريقة.

```csharp
dstDoc.RemoveAllChildren();
```

## الخطوة 4: قم بإلحاق المستند المصدر بالمستند الوجهة

 قم بإلحاق محتويات المستند المصدر بالمستند الوجهة باستخدام ملف`AppendDocument` طريقة مع`ImportFormatMode.KeepSourceFormatting` خيار.

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## الخطوة 5: احفظ المستند الوجهة

 أخيرًا ، احفظ مستند الوجهة المعدل باستخدام امتداد`Save` طريقة`Document` هدف.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.AppendDocumentToBlank.docx");
```

هذا يكمل تنفيذ إلحاق مستند إلى مستند وجهة فارغ باستخدام Aspose.Words for .NET.

### مثال على الكود المصدري لإلحاق مستند فارغ باستخدام Aspose.Words for .NET 

```csharp
	// المسار إلى دليل المستند الخاص بك
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document();
	// المستند الوجهة ليس فارغًا ، وغالبًا ما يتسبب في ظهور صفحة فارغة قبل المستند الملحق.
	// ويرجع ذلك إلى وجود قسم فارغ في المستند الأساسي وبدء تشغيل المستند الجديد في الصفحة التالية.
	// قم بإزالة كل المحتوى من المستند الوجهة قبل الإلحاق.
	dstDoc.RemoveAllChildren();
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.AppendDocumentToBlank.docx");

```