---
title: صفحة بالصفحة
linktitle: صفحة بالصفحة
second_title: Aspose.Words لمراجع .NET API
description: دليل تفصيلي خطوة بخطوة لشرح شفرة المصدر C # لميزة Aspose.Words صفحة بصفحة لـ .NET
type: docs
weight: 10
url: /tr/net/split-document/page-by-page/
---

في هذا البرنامج التعليمي ، سنرشدك إلى كيفية تقسيم مستند Word إلى صفحات فردية باستخدام ميزة صفحة بصفحة في Aspose.Words for .NET. اتبع الخطوات أدناه لفهم شفرة المصدر والحصول على مستندات منفصلة لكل صفحة.

## الخطوة 1: تحميل المستند

للبدء ، حدد الدليل للمستند الخاص بك وقم بتحميل المستند في كائن المستند. إليك الطريقة:

```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(MyDir + "Large document.docx");
```

## الخطوة 2: قسّم المستند على الصفحة

سنقوم الآن بالتكرار خلال كل صفحة من المستند ونقسم المستند إلى صفحات فردية. إليك الطريقة:

```csharp
int pageCount = doc. PageCount;

for (int page = 0; page < pageCount; page++)
{
// احفظ كل صفحة كمستند منفصل.
Document extractedPage = doc.ExtractPages(page, 1);
extractedPage.Save(dataDir + $"SplitDocument.PageParPage_{page + 1}.docx");
}
```

## الخطوة 3: دمج المستندات

بمجرد أن يكون لديك مستندات منفصلة لكل صفحة ، يمكنك دمجها إذا لزم الأمر. إليك الطريقة:

```csharp
MergeDocuments();
```

### مثال على شفرة المصدر لـ Page By Page باستخدام Aspose.Words for .NET

فيما يلي شفرة المصدر الكاملة لميزة صفحة بصفحة في Aspose.Words for .NET:

```csharp

	// المسار إلى دليل المستندات.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(MyDir + "Big document.docx");

	int pageCount = doc.PageCount;

	for (int page = 0; page < pageCount; page++)
	{
		// احفظ كل صفحة كمستند منفصل.
		Document extractedPage = doc.ExtractPages(page, 1);
		extractedPage.Save(dataDir + $"SplitDocument.PageByPage_{page + 1}.docx");
	}
	

	MergeDocuments();

```

باستخدام هذا الرمز ، ستتمكن من تقسيم مستند Word إلى صفحات فردية باستخدام Aspose.Words for .NET. يمكنك أيضًا دمج مستندات منفصلة إذا لزم الأمر.

