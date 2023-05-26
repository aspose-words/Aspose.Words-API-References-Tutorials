---
title: بحث بسيط استبدال
linktitle: بحث بسيط استبدال
second_title: Aspose.Words لمراجع .NET API
description: تعرف على كيفية إجراء استبدال بحث بسيط في مستند Word باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /sv/net/find-and-replace-text/simple-find-replace/
---

في هذه المقالة ، سوف نستكشف الكود المصدري C # أعلاه لفهم كيفية استخدام وظيفة Simple Find Replace في Aspose.Words مكتبة .NET. تتيح لك هذه الميزة إجراء استبدال بسيط للنص من خلال البحث عن سلسلة محددة من الأحرف واستبدالها بسلسلة أخرى من الأحرف في مستند Word.

## المتطلبات الأساسية

- المعرفة الأساسية للغة C #.
- بيئة تطوير .NET مع تثبيت مكتبة Aspose.Words.

## الخطوة الأولى: إنشاء مستند جديد

 قبل أن نبدأ في استخدام ميزة البحث والاستبدال البسيطة ، نحتاج إلى إنشاء مستند جديد باستخدام Aspose.Words for .NET. يمكن القيام بذلك عن طريق إنشاء مثيل لملف`Document` هدف:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
```

## الخطوة 2: أدخل النص في المستند

 بمجرد أن نحصل على مستند ، يمكننا إدراج نص باستخدام ملف`DocumentBuilder` هدف. في مثالنا ، نستخدم الامتداد`Writeln` طريقة لإدراج عبارة "Hello_CustomerName_، ":

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("Hello _CustomerName_,");
```

## الخطوة 3: استبدال النص البسيط

 نحن نستخدم ال`Range.Replace` طريقة لإجراء استبدال نص بسيط. في مثالنا ، نستبدل جميع تكرارات السلسلة "_ClientName_ "مع" جيمس بوند "باستخدام`FindReplaceOptions` الخيار مع`FindReplaceDirection.Forward` اتجاه البحث:

```csharp
doc.Range.Replace("_CustomerName_", "James Bond", new FindReplaceOptions(FindReplaceDirection.Forward));
```

## الخطوة 4: حفظ المستند المحرر

 أخيرًا ، نحفظ المستند المعدل في دليل محدد باستخدام امتداد`Save` طريقة:

```csharp
doc.Save(dataDir + "FindAndReplace.SimpleFindReplace.docx");
```

### مثال على شفرة المصدر لـ Simple Find Replace باستخدام Aspose.Words for .NET

فيما يلي المثال الكامل لشفرة المصدر لتوضيح استخدام البحث البسيط والاستبدال بـ Aspose.Words for .NET:

```csharp

	// المسار إلى دليل المستندات.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	builder.Writeln("Hello _CustomerName_,");
	Console.WriteLine("Original document text: " + doc.Range.Text);

	doc.Range.Replace("_CustomerName_", "James Bond", new FindReplaceOptions(FindReplaceDirection.Forward));

	Console.WriteLine("Document text after replace: " + doc.Range.Text);

	// احفظ المستند المعدل
	doc.Save(dataDir + "FindAndReplace.SimpleFindReplace.docx");

```

## خاتمة

في هذه المقالة ، استكشفنا الكود المصدري C # لفهم كيفية استخدام وظيفة Simple Find Replace الخاصة بـ Aspose.Words for .NET. لقد اتبعنا دليلًا تفصيليًا لإنشاء مستند وإدراج نص وإجراء استبدال بسيط للنص وحفظ المستند الذي تم تحريره.
