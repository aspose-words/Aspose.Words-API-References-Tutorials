---
title: المسافة بين النص الآسيوي واللاتيني
linktitle: المسافة بين النص الآسيوي واللاتيني
second_title: Aspose.Words لمراجع .NET API
description: تعرف على كيفية ضبط المسافة تلقائيًا بين النص الآسيوي واللاتيني في مستندك باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /tr/net/document-formatting/space-between-asian-and-latin-text/
---

في هذا البرنامج التعليمي ، سوف نوضح لك كيفية استخدام ميزة المسافة بين النص الآسيوي واللاتيني باستخدام Aspose.Words for .NET. اتبع الخطوات أدناه لفهم شفرة المصدر وتطبيق التغييرات.

## الخطوة 1: إنشاء وتكوين المستند

للبدء ، قم بإنشاء مستند جديد وكائن DocumentBuilder المرتبط به. إليك الطريقة:

```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## الخطوة 2: إعداد المسافة بين النص الآسيوي واللاتيني

سنقوم الآن بتكوين المسافة بين النص الآسيوي واللاتيني باستخدام خصائص الكائن ParagraphFormat. إليك الطريقة:

```csharp
ParagraphFormat paragraphFormat = builder.ParagraphFormat;
paragraphFormat.AddSpaceBetweenFarEastAndAlpha = true;
paragraphFormat.AddSpaceBetweenFarEastAndDigit = true;

builder.Writeln("Auto adjust space between Asian and Latin text");
builder.Writeln("Auto adjust space between Asian text and numbers");
```

## الخطوة 3: حفظ المستند

 بعد إدخال حقل نموذج إدخال النص ، احفظ المستند في الموقع المطلوب باستخدام ملف`Save` طريقة. تأكد من توفير مسار الملف المناسب:

```csharp
doc.Save(dataDir + "DocumentFormatting.SpaceBetweenAsianAndLatinText.docx");
```

### مثال على شفرة المصدر للمسافة بين النص الآسيوي واللاتيني باستخدام Aspose.Words for .NET

فيما يلي شفرة المصدر الكاملة لميزة المسافة بين النص الآسيوي واللاتيني مع Aspose.Words for .NET:


```csharp

	// المسار إلى دليل المستندات.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	ParagraphFormat paragraphFormat = builder.ParagraphFormat;
	paragraphFormat.AddSpaceBetweenFarEastAndAlpha = true;
	paragraphFormat.AddSpaceBetweenFarEastAndDigit = true;

	builder.Writeln("Automatically adjust space between Asian and Latin text");
	builder.Writeln("Automatically adjust space between Asian text and numbers");

	doc.Save(dataDir + "DocumentFormatting.SpaceBetweenAsianAndLatinText.docx");
        
```

باستخدام هذا الرمز ، ستتمكن من ضبط المسافة تلقائيًا بين النص الآسيوي واللاتيني في المستند باستخدام Aspose.Words for .NET.



