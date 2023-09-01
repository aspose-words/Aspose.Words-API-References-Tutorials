---
title: إلحاق المستند
linktitle: إلحاق المستند
second_title: Aspose.Words واجهة برمجة تطبيقات معالجة المستندات
description: تعرف على كيفية إلحاق محتويات مستند بآخر باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /ar/net/join-and-append-documents/append-document/
---

يشرح هذا البرنامج التعليمي كيفية استخدام Aspose.Words for .NET لإلحاق محتويات مستند بآخر. يوضح كود المصدر المقدم كيفية فتح المستندات المصدر والوجهة، واستيراد الأقسام وإلحاقها من المستند المصدر إلى المستند الوجهة.

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

## الخطوة 3: إلحاق أقسام من المستند المصدر بالمستند الوجهة

 قم بالمرور عبر كافة الأقسام في المستند المصدر وقم باستيراد كل قسم إلى المستند الوجهة باستخدام الملف`ImportNode` طريقة. ثم قم بإلحاق القسم المستورد بالمستند الوجهة.

```csharp
foreach (Section srcSection in srcDoc)
{
    Node dstSection = dstDoc.ImportNode(srcSection, true, ImportFormatMode.KeepSourceFormatting);
    dstDoc.AppendChild(dstSection);
}
```

## الخطوة 4: احفظ المستند الوجهة

 وأخيرًا، احفظ مستند الوجهة المعدل باستخدام الملف`Save` طريقة`Document` هدف.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.AppendDocument.docx");
```

يكمل هذا تنفيذ إلحاق مستند باستخدام Aspose.Words لـ .NET.

### مثال على التعليمات البرمجية المصدر لإلحاق المستند باستخدام Aspose.Words لـ .NET 

```csharp
	// المسار إلى دليل المستندات الخاص بك
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Northwind traders.docx");
	// قم بالمراجعة عبر كافة الأقسام في المستند المصدر.
	//عقد القسم هي أبناء مباشرون لعقدة المستند حتى نتمكن من تعداد المستند فقط.
	foreach (Section srcSection in srcDoc)
	{
		// لأننا نقوم بنسخ قسم من مستند إلى آخر،
		// مطلوب استيراد عقدة القسم إلى المستند الوجهة.
		// يؤدي هذا إلى ضبط أي مراجع خاصة بالمستند إلى الأنماط والقوائم وما إلى ذلك.
		//
		// يؤدي استيراد عقدة إلى إنشاء نسخة من العقدة الأصلية، ولكن النسخة
		// جاهز لإدراجه في المستند الوجهة.
		Node dstSection = dstDoc.ImportNode(srcSection, true, ImportFormatMode.KeepSourceFormatting);
		// يمكن الآن إلحاق عقدة القسم الجديدة بالمستند الوجهة.
		dstDoc.AppendChild(dstSection);
	}
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.AppendDocument.docx");
```