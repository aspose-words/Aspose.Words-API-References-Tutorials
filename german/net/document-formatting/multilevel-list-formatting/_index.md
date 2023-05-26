---
title: تنسيق قائمة متعددة المستويات
linktitle: تنسيق قائمة متعددة المستويات
second_title: Aspose.Words لمراجع .NET API
description: تعرف على كيفية إنشاء قائمة متعددة المستويات وتطبيق تنسيق مخصص باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /de/net/document-formatting/multilevel-list-formatting/
---

في هذا البرنامج التعليمي ، سوف نوضح لك كيفية استخدام ميزة تنسيق القائمة متعددة المستويات مع Aspose.Words for .NET. اتبع الخطوات أدناه لفهم شفرة المصدر وتطبيق التغييرات.

## الخطوة 1: إنشاء وتكوين المستند

للبدء ، قم بإنشاء مستند جديد وكائن DocumentBuilder المرتبط به. إليك الطريقة:

```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## الخطوة 2: تنسيق القائمة متعددة المستويات

سنقوم الآن بتطبيق تنسيق القائمة متعدد المستويات باستخدام الطرق المتاحة في كائن DocumentBuilder. إليك الطريقة:

```csharp
builder.ListFormat.ApplyNumberDefault();
builder. Writen("Element 1");
builder. Writen("Element 2");

builder.ListFormat.ListIndent();
builder.Writeln("Element 2.1");
builder.Writeln("Element 2.2");

builder.ListFormat.ListIndent();
builder.Writeln("Element 2.2.1");
builder.Writeln("Element 2.2.2");

builder.ListFormat.ListOutdent();
builder.Writeln("Element 2.3");

builder.ListFormat.ListOutdent();
builder.Writeln("Element 3");

builder.ListFormat.RemoveNumbers();
```

## الخطوة 3: حفظ المستند

 بعد إدخال حقل نموذج إدخال النص ، احفظ المستند في الموقع المطلوب باستخدام ملف`Save` طريقة. تأكد من توفير مسار الملف المناسب:

```csharp
doc.Save(dataDir + "DocumentFormatting.MultilevelListFormatting.docx");
```

### مثال على شفرة المصدر لتنسيق قائمة متعددة المستويات باستخدام Aspose.Words for .NET

فيما يلي رمز المصدر الكامل لميزة تنسيق القائمة متعددة المستويات باستخدام Aspose.Words for .NET:


```csharp

	// المسار إلى دليل المستندات.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	builder.ListFormat.ApplyNumberDefault();
	builder.Writeln("Item 1");
	builder.Writeln("Item 2");

	builder.ListFormat.ListIndent();
	builder.Writeln("Item 2.1");
	builder.Writeln("Item 2.2");
	
	builder.ListFormat.ListIndent();
	builder.Writeln("Item 2.2.1");
	builder.Writeln("Item 2.2.2");

	builder.ListFormat.ListOutdent();
	builder.Writeln("Item 2.3");

	builder.ListFormat.ListOutdent();
	builder.Writeln("Item 3");

	builder.ListFormat.RemoveNumbers();
	
	doc.Save(dataDir + "DocumentFormatting.MultilevelListFormatting.docx");

```

باستخدام هذا الرمز ، ستتمكن من إنشاء قائمة متعددة المستويات وتطبيق التنسيق المناسب على كل مستوى باستخدام Aspose.Words for .NET.