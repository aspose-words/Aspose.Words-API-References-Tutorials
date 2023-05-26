---
title: إلحاق مستند
linktitle: إلحاق مستند
second_title: Aspose.Words لمراجع .NET API
description: تعرف على كيفية إلحاق محتويات مستند بآخر باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /sv/net/join-and-append-documents/append-document/
---

يشرح هذا البرنامج التعليمي كيفية استخدام Aspose.Words for .NET لإلحاق محتويات مستند بآخر. يوضح كود المصدر المقدم كيفية فتح مستندات المصدر والوجهة واستيراد وإلحاق أقسام من المستند المصدر إلى المستند الوجهة.

## الخطوة 1: قم بإعداد المشروع

تأكد من أن لديك المتطلبات الأساسية التالية:

- تثبيت Aspose.Words لمكتبة .NET. يمكنك تنزيله من موقع Aspose الرسمي أو استخدام مدير حزمة NuGet لتثبيته.
- مسار دليل المستند حيث توجد المستندات المصدر والوجهة.

## الخطوة 2: افتح مستندات المصدر والوجهة

 افتح مستندات المصدر والوجهة باستخدام ملف`Document` منشئ الطبقة. يستبدل`"YOUR DOCUMENT DIRECTORY"` مع المسار الفعلي إلى دليل المستند الخاص بك.

```csharp
// المسار إلى دليل المستند الخاص بك
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document srcDoc = new Document(dataDir + "Document source.docx");
Document dstDoc = new Document(dataDir + "Northwind traders.docx");
```

## الخطوة 3: إلحاق أقسام من المستند المصدر بالمستند الوجهة

 قم بالتكرار خلال جميع الأقسام في المستند المصدر واستورد كل قسم في المستند الوجهة باستخدام ملف`ImportNode` طريقة. ثم قم بإلحاق القسم الذي تم استيراده بالمستند الوجهة.

```csharp
foreach (Section srcSection in srcDoc)
{
    Node dstSection = dstDoc.ImportNode(srcSection, true, ImportFormatMode.KeepSourceFormatting);
    dstDoc.AppendChild(dstSection);
}
```

## الخطوة 4: احفظ المستند الوجهة

 أخيرًا ، احفظ مستند الوجهة المعدل باستخدام امتداد`Save` طريقة`Document` هدف.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.AppendDocument.docx");
```

هذا يكمل تنفيذ إلحاق مستند باستخدام Aspose.Words لـ .NET.

### مثال على الكود المصدري لإلحاق المستند باستخدام Aspose.Words for .NET 

```csharp
	// المسار إلى دليل المستند الخاص بك
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Northwind traders.docx");
	// تكرار خلال جميع الأقسام في المستند المصدر.
	// عُقد الأقسام هي عناصر فرعية مباشرة لعقدة المستند حتى نتمكن من تعداد المستند.
	foreach (Section srcSection in srcDoc)
	{
		//لأننا نقوم بنسخ قسم من مستند إلى آخر ،
		// مطلوب لاستيراد عقدة القسم في المستند الوجهة.
		// يعمل هذا على ضبط أي مراجع خاصة بالمستند للأنماط والقوائم وما إلى ذلك.
		//
		// يؤدي استيراد عقدة إلى إنشاء نسخة من العقدة الأصلية ، ولكن النسخة
		// ss جاهزة لإدراجها في المستند الوجهة.
		Node dstSection = dstDoc.ImportNode(srcSection, true, ImportFormatMode.KeepSourceFormatting);
		// يمكن الآن إلحاق عقدة القسم الجديدة بالمستند الوجهة.
		dstDoc.AppendChild(dstSection);
	}
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.AppendDocument.docx");
```