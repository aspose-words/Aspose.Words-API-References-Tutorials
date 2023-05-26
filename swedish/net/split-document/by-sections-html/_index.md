---
title: حسب أقسام Html
linktitle: حسب أقسام Html
second_title: Aspose.Words لمراجع .NET API
description: تعرف على كيفية تقسيم مستند Word إلى أقسام Html باستخدام Aspose.Words for .NET مع مثال رمز كامل.
type: docs
weight: 10
url: /sv/net/split-document/by-sections-html/
---

في هذا المثال ، سنوضح لك كيفية تقسيم مستند Word إلى أقسام منفصلة بتنسيق HTML باستخدام ميزة By HTML Sections في Aspose.Words for .NET. اتبع الخطوات أدناه لفهم كود المصدر وإنشاء مستندات HTML منفصلة لكل قسم.

## الخطوة 1: تحميل المستند

للبدء ، حدد الدليل للمستند الخاص بك وقم بتحميل المستند في كائن المستند. إليك الطريقة:

```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(MyDir + "Rendering.docx");
```

## الخطوة الثانية: تقسيم المستند إلى أقسام بتنسيق HTML

سنقوم الآن بتعيين خيارات الحفظ لتقسيم المستند إلى أقسام بتنسيق HTML. هيريس كيفية القيام بذلك:

```csharp
HtmlSaveOptions options = new HtmlSaveOptions { DocumentSplitCriteria = DocumentSplitCriteria.SectionBreak };

doc.Save(dataDir + "SplitDocument.ParSectionsHtml.html", options);
```

### مثال على شفرة المصدر لـ By Sections HTML باستخدام Aspose.Words for .NET

فيما يلي شفرة المصدر الكاملة لميزة By HTML Sections في Aspose.Words for .NET:

```csharp

	// المسار إلى دليل المستندات.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(MyDir + "Rendering.docx");

	
	HtmlSaveOptions options = new HtmlSaveOptions { DocumentSplitCriteria = DocumentSplitCriteria.SectionBreak };
	
	
	doc.Save(dataDir + "SplitDocument.BySectionsHtml.html", options);

```

باستخدام هذا الرمز ، ستتمكن من تقسيم مستند Word إلى أقسام منفصلة بتنسيق HTML باستخدام Aspose.Words for .NET.

يمكنك الآن إنشاء مستندات HTML منفصلة لكل قسم من المستند الأولي.



