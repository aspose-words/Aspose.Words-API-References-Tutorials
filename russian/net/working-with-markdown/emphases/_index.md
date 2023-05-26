---
title: تأكيدات
linktitle: تأكيدات
second_title: Aspose.Words لمراجع .NET API
description: تعرف على كيفية استخدام التأكيدات (بالخط العريض والمائل) باستخدام دليل Aspose.Words for .NET خطوة بخطوة.
type: docs
weight: 10
url: /ru/net/working-with-markdown/emphases/
---

في هذا المثال ، سنشرح كيفية استخدام التأكيدات مع Aspose.Words for .NET. يتم استخدام التأكيدات للتأكيد على أجزاء معينة من النص ، مثل الخط الغامق والمائل.

## الخطوة 1: تهيئة المستند

 أولاً ، سنهيئ المستند عن طريق إنشاء مثيل لـ`Document` فصل.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
```

## الخطوة 2: استخدام منشئ المستندات

بعد ذلك ، سنستخدم منشئ المستندات لإضافة محتوى إلى وثيقتنا.

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
```

## الخطوة 3: إضافة نص مع التوكيدات

يمكننا إضافة نص تأكيدات عن طريق تغيير خصائص خط منشئ المستند. في هذا المثال ، نستخدم الخط الغامق والمائل للتأكيد على أجزاء مختلفة من النص.

```csharp
builder.Writeln("Markdown treats asterisks (*) and underscores (_) as emphases indicators.");
builder.Write("You can write");

builder.Font.Bold = true;
builder.Write("bold");

builder.Font.Bold = false;
builder.Write(" or ");

builder.Font.Italic = true;
builder.Write("italic");

builder.Font.Italic = false;
builder.Writeln(".");

builder.Write("You can also write ");
builder.Font.Bold = true;

builder.Font.Italic = true;
builder.Write("bold and italic");

builder.Font.Bold = false;
builder.Font.Italic = false;
builder. Write(".");

```

## الخطوة 4: حفظ المستند

 أخيرًا ، يمكننا حفظ المستند بالتنسيق المطلوب. في هذا المثال ، نستخدم الامتداد`.md` التمديد لتنسيق Markdown.

```csharp
builder.Document.Save(dataDir + "WorkingWithMarkdown.Emphases.md");
```

تهنئة ! لقد تعلمت الآن كيفية استخدام التأكيدات مع Aspose.Words for .NET.

### مثال على شفرة المصدر للتأكيد باستخدام Aspose.Words for .NET


```csharp
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	builder.Writeln("Markdown treats asterisks (*) and underscores (_) as indicators of emphases.");
	builder.Write("You can write ");

	builder.Font.Bold = true;
	builder.Write("bold");

	builder.Font.Bold = false;
	builder.Write(" or ");

	builder.Font.Italic = true;
	builder.Write("italic");

	builder.Font.Italic = false;
	builder.Writeln(" text. ");

	builder.Write("You can also write ");
	builder.Font.Bold = true;

	builder.Font.Italic = true;
	builder.Write("BoldItalic");

	builder.Font.Bold = false;
	builder.Font.Italic = false;
	builder.Write("text.");

	builder.Document.Save(dataDir + "WorkingWithMarkdown.Emphases.md");
            
```
