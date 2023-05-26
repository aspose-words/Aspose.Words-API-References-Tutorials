---
title: حسب العناوين Html
linktitle: حسب العناوين Html
second_title: Aspose.Words لمراجع .NET API
description: دليل تفصيلي خطوة بخطوة لشرح شفرة المصدر C # لميزة By Heading HTML في Aspose.Words for .NET
type: docs
weight: 10
url: /tr/net/split-document/by-headings-html/
---
في هذا البرنامج التعليمي ، سنرشدك إلى كيفية تقسيم مستند Word إلى أجزاء أصغر باستخدام ميزة By HTML Heading في Aspose.Words for .NET. اتبع الخطوات أدناه لفهم الكود المصدري وإنشاء مستندات HTML منفصلة استنادًا إلى العنوان.

## الخطوة 1: تحميل المستند

للبدء ، حدد الدليل للمستند الخاص بك وقم بتحميل المستند في كائن المستند. إليك الطريقة:

```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(MyDir + "Rendering.docx");
```

## الخطوة 2: تقسيم المستند عن طريق العنوان بتنسيق HTML

سنقوم الآن بتعيين خيارات الحفظ لتقسيم المستند إلى أجزاء أصغر بناءً على العنوان بتنسيق HTML. إليك الطريقة:

```csharp
HtmlSaveOptions options = new HtmlSaveOptions
{
// قسّم المستند إلى أجزاء أصغر ، في هذه الحالة افصله حسب العنوان.
DocumentSplitCriteria = DocumentSplitCriteria.HeadingParagraph
};

doc.Save(dataDir + "SplitDocument.ParTitresHtml.html", options);
```

### مثال على شفرة المصدر لـ By Headings HTML باستخدام Aspose.Words for .NET

فيما يلي شفرة المصدر الكاملة لميزة By HTML Heading في Aspose.Words for .NET:

```csharp

	// المسار إلى دليل المستندات.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(MyDir + "Rendering.docx");

	HtmlSaveOptions options = new HtmlSaveOptions
	{
		// قسّم مستندًا إلى أجزاء أصغر ، في هذه الحالة ، قسم حسب العنوان.
		DocumentSplitCriteria = DocumentSplitCriteria.HeadingParagraph
	};
	

	doc.Save(dataDir + "SplitDocument.ByHeadingsHtml.html", options);
	

```

باستخدام هذا الرمز ، ستتمكن من تقسيم مستند Word إلى أجزاء أصغر باستخدام Aspose.Words for .NET ، بناءً على العناوين. يمكنك بعد ذلك إنشاء مستندات HTML منفصلة لكل جزء.

