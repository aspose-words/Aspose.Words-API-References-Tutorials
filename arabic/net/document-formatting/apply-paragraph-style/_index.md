---
title: تطبيق نمط الفقرة
linktitle: تطبيق نمط الفقرة
second_title: واجهة برمجة تطبيقات معالجة المستندات Aspose.Words
description: تعرف على كيفية تطبيق نمط فقرة باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /ar/net/document-formatting/apply-paragraph-style/
---

في هذا البرنامج التعليمي ، سنرشدك إلى كيفية تطبيق نمط فقرة باستخدام Aspose.Words for .NET. اتبع الخطوات أدناه لفهم الكود المصدري وتطبيق نمط الفقرة.

## الخطوة 1: إنشاء وتكوين المستند

للبدء ، قم بإنشاء مستند جديد وكائن DocumentBuilder المرتبط به. إليك الطريقة:

```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## الخطوة 2: تكوين نمط الفقرة

سنقوم الآن بتكوين نمط الفقرة باستخدام معرف النمط المدمج. إليك الطريقة:

```csharp
builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Title;
```

## الخطوة 3: أضف محتوى

سنقوم بإضافة محتوى إلى الفقرة. إليك الطريقة:

```csharp
builder.Write("Hello");
doc.Save(dataDir + "DocumentFormatting.ApplyParagraphStyle.docx");
```

### مثال على شفرة المصدر لتطبيق Paragraph Style باستخدام Aspose.Words for .NET

فيما يلي رمز المصدر الكامل لميزة "تطبيق نمط الفقرة" مع Aspose.Words for .NET:

```csharp

	// المسار إلى دليل المستندات.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Title;
	builder.Write("Hello");
	
	doc.Save(dataDir + "DocumentFormatting.ApplyParagraphStyle.docx");
	
```

باستخدام هذا الرمز ، ستتمكن من تطبيق نمط فقرة باستخدام Aspose.Words for .NET.

