---
title: إلحاق مستند بالفارغ
linktitle: إلحاق مستند بالفارغ
second_title: Aspose.Words واجهة برمجة تطبيقات معالجة المستندات
description: تعرف على كيفية إلحاق مستند بمستند وجهة فارغ في Aspose.Words لـ .NET.
type: docs
weight: 10
url: /ar/net/join-and-append-documents/append-document-to-blank/
---

يشرح هذا البرنامج التعليمي كيفية استخدام Aspose.Words for .NET لإلحاق محتويات مستند واحد بمستند وجهة فارغ. يوضح رمز المصدر المقدم كيفية إنشاء مستند جديد، وإزالة محتواه، ثم إلحاق المستند المصدر به.

## الخطوة 1: إعداد المشروع

تأكد من أن لديك المتطلبات الأساسية التالية:

- تم تثبيت Aspose.Words لمكتبة .NET. يمكنك تنزيله من[Aspose.Releases]https://releases.aspose.com/words/net/ أو استخدم مدير الحزم NuGet لتثبيته.
- مسار دليل المستند حيث توجد المستندات المصدر والوجهة.

## الخطوة 2: إنشاء مستند وجهة جديد

 إنشاء جديد`Document` كائن للمستند الوجهة.

```csharp
// المسار إلى دليل المستندات الخاص بك
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document srcDoc = new Document(dataDir + "Document source.docx");
Document dstDoc = new Document();
```

## الخطوة 3: قم بإزالة المحتوى الموجود من المستند الوجهة

 لضمان الحصول على مستند وجهة نظيف، قم بإزالة كل المحتوى الموجود من المستند باستخدام`RemoveAllChildren` طريقة.

```csharp
dstDoc.RemoveAllChildren();
```

## الخطوة 4: إلحاق المستند المصدر بالمستند الوجهة

 قم بإلحاق محتويات المستند المصدر بالمستند الوجهة باستخدام`AppendDocument` طريقة مع`ImportFormatMode.KeepSourceFormatting` خيار.

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## الخطوة 5: احفظ مستند الوجهة

 وأخيرًا، احفظ مستند الوجهة المعدل باستخدام الملف`Save` طريقة`Document` هدف.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.AppendDocumentToBlank.docx");
```

يكمل هذا تنفيذ إلحاق مستند بمستند وجهة فارغ باستخدام Aspose.Words لـ .NET.

### مثال على التعليمات البرمجية المصدر لإلحاق مستند بالفارغ باستخدام Aspose.Words لـ .NET 

```csharp
	//المسار إلى دليل المستندات الخاص بك
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document();
	//المستند الوجهة ليس فارغًا، مما يؤدي غالبًا إلى ظهور صفحة فارغة قبل المستند الملحق.
	// ويرجع ذلك إلى أن المستند الأساسي يحتوي على قسم فارغ وأن المستند الجديد يبدأ في الصفحة التالية.
	// قم بإزالة كل المحتوى من المستند الوجهة قبل الإلحاق.
	dstDoc.RemoveAllChildren();
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.AppendDocumentToBlank.docx");

```